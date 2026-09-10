---
name: ios-pickers
description: Set values in iOS wheel-style pickers — time, duration, date, and other scrolling column pickers — with deterministic tap-only selection. Use when creating, editing, or testing a picker value on an iPhone; covers circular vs. bounded columns, multi-value hops, verification, and separate authorization before Save or Start.
---

# iOS wheel pickers: tap-only selection

Set picker values from the latest screen returned after each action. Locate controls by visible labels and relationships; never rely on saved coordinates.

Inside any wheel picker, use taps only. Do not use a drag, flick, or hold-and-drag gesture. Tapping visible values is exact and avoids momentum.

## Shared interaction model

Use one visual action per loop:

1. Inspect the latest returned screen.
2. Read the selected values from the bright center row.
3. Identify one visible target by its label and relative row.
4. Use a tap tool on that target.
5. Inspect the returned result before continuing.

An off-center value one, two, or three rows from the center can be selected directly. When the target is farther away, tap the farthest visible value toward it for an exact three-value hop, then re-evaluate the newly visible values. The faint third row is tappable.

If the requested value is already selected, do nothing. Treat the bright center row as state to read, not a target to tap — depending on the picker, tapping a selected center value may open numeric entry or do nothing.

## Two movement models

Determine each column's model before hopping. Do not transfer wraparound, range, carry, or selected-row assumptions between pickers, or between columns of one picker.

### Circular wheels

Values wrap around a fixed cycle (Clock alarm hours `1–12`, minutes `00–59`). Compute both directions and choose the shorter:

- Forward distance: `(target - current + cycle) mod cycle`
- Backward distance: `(current - target + cycle) mod cycle`
- Either direction is acceptable for a tie.

Wrapping can have side effects on other columns: in a time picker, crossing the 11/12 hour boundary may or may not flip AM/PM (observed: `11 PM -> 12 AM` flipped; `12 AM -> 1 AM` did not; reverse multi-row hops vary). Never read elapsed-time semantics into a multi-row hop. Always re-verify dependent columns, such as AM/PM, after the target value is final.

### Bounded columns

Values stop at endpoints (Clock timer: hours `0–23`, minutes and seconds `0–59`). At an endpoint, unavailable rows are blank; tapping blank space does nothing. Values never wrap, and movement in one column never carries into another.

Move upward for a smaller value, downward for a larger one, tapping the farthest visible value in that direction. The farthest visible target is normally three values away, so a linear distance `d` takes at most `ceil(d / 3)` taps. Near an endpoint, use whichever valid rows remain visible; never tap blank space as a movement strategy.

## Authorization boundaries

Picker exploration is not authorization to confirm, save, or start anything.

- Confirmation controls — the orange checkmark in **Add Alarm**, the green **Start** in **Timer**, or their equivalent in other apps — are separate actions. Tap one only after explicit authorization and final verification.
- Before changing an existing item, identify it in the current list by every visible attribute (for an alarm: time, AM/PM, label, repeat summary, enabled state). Present that identity and the exact proposed change, obtain confirmation, then verify the same row again before changing it. Saving remains a separate authorized action.
- For experimentation, use an unsaved creation sheet or an inactive configuration screen. Exit without confirming, then verify that nothing was created or started.

## Worked example: Clock alarm time picker

**Add Alarm** and edit-alarm pickers have hour (left), minute (middle), and AM/PM (right) columns. Up to three values appear above and below the center.

- Hours and minutes are circular wheels, cycles 12 and 60.
- The visible off-center AM or PM label selects that period exactly.
- Tapping an already-selected center value opens whole-time numeric entry.
- Minute wraparound does not alter the hour or period. Observed exact hops: `45 -> 48 -> 51 -> 54 -> 57 -> 00` and the reverse `00 -> 57`.

Procedure — set hour first, minute second, AM/PM last:

1. Read the selected value for the column.
2. If the target is already selected, do nothing.
3. If the target is visible off-center, tap it directly.
4. Otherwise, choose the shorter direction around the wheel and tap the farthest visible value in that direction.
5. Verify the returned center value and repeat until the target is selected.

Ignore temporary AM/PM changes while selecting the hour; set or re-verify the period after hour and minute are final.

**Accidental numeric entry:** if a center-row value is tapped, the time turns orange and a numeric keypad appears. Tap a neutral part of the sheet header, such as the centered title, to dismiss it. Avoid the left `X` and the orange save checkmark. Verify the returned wheel before resuming.

**Completion:** verify hour, minute, AM/PM, and any requested settings. Do not tap the orange checkmark without explicit authorization. For experiments, close the sheet with the left `X` and verify the alarm list did not gain a row.

## Worked example: Clock timer duration picker

The Timer tab's picker has hours (left), minutes (middle), and seconds (right) — three bounded columns, `0–23`, `0–59`, `0–59`. A tap on an already-selected value causes no change.

Procedure:

1. Read all three selected center values.
2. Work on one column at a time.
3. If its target is already selected, do nothing.
4. If the target is visible off-center, tap it directly.
5. Otherwise, move toward the target by tapping the farthest visible value in that direction.
6. Verify the returned center value and repeat until the target is selected.
7. Repeat for the remaining columns without expecting wraparound or carry.
8. Verify the complete duration from the center row.

Observed exact hops: minutes `15 -> 18 -> 21`; seconds `0 -> 3 -> 6`; hours `0 -> 3 -> 6`, then an adjacent tap to `7`. Taps beyond `0`, `23 hours`, `59 min`, or `59 sec` leave the picker unchanged.

**Completion:** **Cancel** and **Start** sit below the picker; **Label** and **When Timer Ends** are separate settings. Changing the displayed duration is not authorization to begin a countdown. Verify the duration and any requested settings, then stop before the green **Start** control unless starting was explicitly authorized. For experiments, leave without tapping **Start** and verify that no countdown appears.
