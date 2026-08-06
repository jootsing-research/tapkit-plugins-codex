# Timers and stopwatch UI

Read this reference only when the request needs detailed timer options, running-timer controls, stopwatch laps, reset behavior, or display variants.

## Timers

Locate controls by current labels and state. A timer setup screen can include:

- Picker wheels for hours, minutes, and seconds.
- A label field.
- **When Timer Ends** for the alert sound.
- A start control.
- Recent timers or more than one active timer on newer iOS versions.

### Set a duration

Adjust one visible picker wheel at a time with a vertical drag. Screenshot and verify the selected hours, minutes, and seconds after every adjustment. Do not start a zero-duration timer accidentally.

### Set a label

1. Focus the visible label field and screenshot to verify focus.
2. Select the full existing value when replacing it.
3. Call `type_text(phone_id, "requested label")`.
4. Screenshot and verify the complete rendered label in the correct field.
5. Stop before **Done**, Return, **Start**, or any equivalent submission.
6. Confirm the label or start the timer only as a separate, explicitly authorized action.

### Choose an end sound

Open **When Timer Ends** and read the currently available choices. Sound names and categories vary. A selection can play a preview. Verify the selected option and return to the timer screen before starting.

### Start and manage timers

Before starting, screenshot and verify the duration, label, and end sound as visible. After an authorized start, verify that the countdown advances.

For an active or recent timer:

- Identify it by its visible label and remaining or configured duration.
- **Pause** stops the countdown without discarding it.
- **Resume** continues a paused timer.
- **Cancel** stops and dismisses an active timer.
- A repeated recent timer may have a restart control.

When multiple timers are visible, do not act until the intended timer is unambiguous. Verify the state after every action.

## Stopwatch

The stopwatch can show:

- A digital elapsed-time display.
- **Start** while stopped.
- **Stop** while running.
- **Lap** while running.
- **Reset** after stopping.
- A lap list after laps are recorded.
- Digital and analog display variants, often switched by swiping the stopwatch display.

### Control-state workflow

1. Screenshot and read the visible elapsed time and controls.
2. Use **Start** to begin; verify the display advances and **Stop** appears.
3. Use **Lap** only when requested; verify a new lap row and its time.
4. Use **Stop** to pause; verify the elapsed time stops changing and **Reset** appears.
5. Use **Reset** only when requested; verify elapsed time and lap history clear.

Reset is destructive to the recorded stopwatch state. If the user did not explicitly request it, ask before resetting.

### Switch display variants

Swipe across the stopwatch display only when the request needs another view. Screenshot after the swipe and verify the digital or analog display changed. Do not treat page-indicator placement as stable.
