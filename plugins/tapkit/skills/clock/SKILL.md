---
name: clock
description: Use this skill when the user wants to use the iPhone Clock app for alarms, timers, stopwatch sessions, or world clocks.
---

# Clock

Use `open_app("Clock")` first when it works. If that fails, fall back to Spotlight. Always verify each step with screenshots.

For any label or search text entry, use the clipboard-and-paste workflow from the `tapkit` skill.

## Main Tabs

- `World Clock`
- `Alarm`
- `Stopwatch`
- `Timer`

## Common Tasks

### Set an Alarm

1. Go to `Alarm`.
2. Tap the `+` button.
3. Adjust the hour and minute wheels with short drags.
4. Set repeat, label, or sound if needed.
5. Tap `Save`.

### Edit or Delete an Alarm

1. Go to `Alarm`.
2. Tap an existing alarm to edit it, or swipe left on a row to delete it.
3. Verify the toggle state or deletion afterward.

### Start a Timer

1. Open `Timer`.
2. Adjust the duration wheel.
3. Tap `Start`.

### Use Stopwatch

1. Open `Stopwatch`.
2. Tap `Start`.
3. Use `Lap`, `Stop`, and `Reset` as needed.

### Add a World Clock City

1. Open `World Clock`.
2. Tap `+`.
3. Search for a city and paste the query if needed.
4. Tap the matching city result.

## Gotchas

- Alarm and timer pickers respond better to short drags than broad swipes.
- The label field often works best with long-press plus `Paste`.
- Some versions of Clock hide edit controls until you tap into a row or perform a swipe gesture.
