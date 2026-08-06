---
name: clock
description: Use the iPhone Clock app through TapKit to create, inspect, edit, enable, disable, or delete alarms and sleep schedules; start or manage timers and the stopwatch; or view and manage World Clock cities.
---

# iOS Clock

## Safety and interaction contract

Start with `list_phones()` -> choose `phone_id` -> `get_phone_status(phone_id)`. Every phone-targeting call must include that `phone_id`.

Use the visual loop for every action:

1. Call `screenshot(phone_id)`.
2. Identify the intended control from its current visible label, icon, and surrounding context.
3. Act on the center of that currently observed control.
4. Call `screenshot(phone_id)` again and verify the result.

Never reuse remembered tap points or assume the interface is unchanged.

For every text entry:

1. Focus the correct field and verify focus with a screenshot.
2. Call `type_text(phone_id, text)`.
3. Take a screenshot and verify the complete rendered text in the intended field.
4. Stop before submission.
5. Use **Search**, **Save**, **Done**, Return, a checkmark, or an equivalent submission control only as a separate step that the user explicitly authorized after the rendered text was verified.

### Existing alarm and schedule confirmation gate

Before deleting or materially changing an existing alarm or schedule:

1. Take a current screenshot of the alarm or schedule list.
2. Identify the exact target from what is visible: time, AM/PM, label, repeat days, and enabled state.
3. Do not infer hidden, clipped, or ambiguous attributes. State which requested identity attribute is not visible and obtain a clearer view or user clarification.
4. Present the full visible identity and the exact proposed change to the user. For example: `7:30 AM — Work — Mon–Fri — enabled; proposed change: disable`.
5. Ask for confirmation and wait. The original request to edit or delete does not replace this confirmation.
6. After confirmation, take another screenshot and ensure the same target and state are still visible. If anything changed or two alarms remain indistinguishable, stop and clarify.
7. Make only the confirmed change, then screenshot and verify it.

Material changes include deletion, time, AM/PM, repeat days, label, sound, haptics, snooze, snooze duration, enabled state, and Sleep/Wake Up schedule changes. Merely opening an alarm to inspect it is not a material change.

## Open Clock

1. Call `press_home(phone_id)` and take a screenshot.
2. If **Clock** is visible, tap that currently observed icon and verify the app opened.
3. Otherwise, navigate visually to App Library, focus its search field, and follow the text-entry contract with `Clock`.
4. After verifying the rendered query and matching **Clock** result, tap that result only when opening Clock is authorized.
5. Verify that Clock opened.

Use the visible bottom-tab labels to navigate among **World Clock**, **Alarms**, **Stopwatch**, and **Timers**. Always locate the tab in the current screenshot.

## Alarm workflow

### Create an alarm

1. Open Clock, select **Alarms**, and verify the alarm list.
2. Tap the visible add control and verify **Add Alarm** opened.
3. Set the requested time and options from the current screen.
4. If entering a label, follow the text-entry contract and stop before confirming or saving it.
5. Review the complete proposed alarm in the current UI.
6. Save only as a separate, authorized action.
7. Verify the new alarm in the list, including time, AM/PM, label, repeat days, and enabled state as visible.

### Inspect or change an existing alarm

1. Screenshot the alarm list and identify the exact target.
2. Open that alarm without changing it, then inspect the requested settings.
3. Return to the alarm list. Before any material change, complete the existing-alarm confirmation gate above from a new list screenshot.
4. Apply only the confirmed edits.
5. Save only as a separate, authorized action after verifying the proposed values.
6. Verify the resulting alarm in the list.

### Enable, disable, or delete an alarm

1. Screenshot the alarm list and identify the exact target.
2. Complete the existing-alarm confirmation gate, naming the exact toggle or deletion.
3. Re-verify the target after confirmation, perform only that action, and verify the result.

Read [Alarm UI and settings](references/alarms.md) when a task involves repeat days, labels, sounds, haptics, snooze, Sleep/Wake Up, picker behavior, editing, toggling, or deletion.

## Timer workflow

1. Open Clock, select **Timers**, and verify the timer screen.
2. Set the requested duration from the currently visible picker.
3. Configure a label or end sound only if requested. Follow the text-entry contract for a label.
4. Verify the duration and visible options.
5. Start the timer only as a separate, authorized action.
6. Screenshot and verify that the countdown is running.

For a running timer, identify it by its visible label and remaining duration before pausing, resuming, or canceling it. Perform only the requested action and verify the new state.

Read [Timers and stopwatch UI](references/timers-and-stopwatch.md) when a task involves timer labels, end sounds, recent or multiple timers, pause/resume/cancel, stopwatch laps, reset, or display variants.

## Stopwatch workflow

1. Open Clock, select **Stopwatch**, and verify the stopwatch screen.
2. Tap the currently visible **Start** control only when authorized, then verify the display is advancing.
3. Use **Lap** only when requested and verify the recorded lap.
4. Use **Stop** only when requested and verify timing paused.
5. Use **Reset** only when requested and verify the cleared display.

Read [Timers and stopwatch UI](references/timers-and-stopwatch.md) for detailed control states, lap behavior, and digital or analog display guidance.

## World Clock workflow

1. Open Clock, select **World Clock**, and verify the city list.
2. For a new city, tap the visible add control, focus the search field, and follow the text-entry contract.
3. After verifying the query and intended result, add the city only as a separate, authorized action.
4. Verify the city appears in the list.

Read [World Clock UI](references/world-clock.md) when adding, removing, or reordering cities, or when interpreting offsets and day relationships.
