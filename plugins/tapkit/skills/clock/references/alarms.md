# Alarm UI and settings

Read this reference only when the request needs detailed alarm controls, settings, editing, deletion, or Sleep/Wake Up behavior.

## Contents

- [Non-negotiable confirmation gate](#non-negotiable-confirmation-gate)
- [Alarm list map](#alarm-list-map)
- [Add and edit screens](#add-and-edit-screens)
- [Existing alarm operations](#existing-alarm-operations)
- [Sleep | Wake Up](#sleep--wake-up)

## Non-negotiable confirmation gate

Before deleting or materially changing an existing alarm or schedule:

1. Take a current screenshot of the list.
2. Read the target's visible time, AM/PM, label, repeat days, and enabled state.
3. Do not guess attributes that are hidden, clipped, or ambiguous.
4. Present the visible identity and exact proposed change to the user.
5. Ask for confirmation and wait, even when the original request already asked for the change.
6. After confirmation, screenshot again and verify the same target and state.
7. If the screen changed or duplicate alarms cannot be distinguished, stop and clarify.
8. Make only the confirmed change and verify the result with a screenshot.

Apply this gate to deletion, enabled state, time, AM/PM, repeat days, label, sound, haptics, snooze, snooze duration, and Sleep/Wake Up schedule changes.

## Alarm list map

Locate all controls from the current screenshot rather than remembered placement.

- **Alarms** identifies the selected section.
- The add control creates a regular alarm.
- **Edit** may appear when regular alarms exist.
- **Sleep | Wake Up** appears separately from regular alarms and may link to Health.
- A regular alarm row can show its time, AM/PM, label, repeat summary, and enabled toggle.
- An enabled toggle is visually active; a disabled alarm is visually dimmed.

Treat clipped text as unknown. Scroll or open the alarm read-only to gather a clearer view, but do not edit until the target is confirmed.

## Add and edit screens

The add and edit screens generally contain:

- A time picker.
- **Repeat**.
- **Label**.
- **Sound** and haptics.
- **Snooze**.
- **Snooze Duration** when available and enabled.
- A cancel control.
- A save checkmark or equivalent control.
- On an existing alarm, a destructive **Delete Alarm** control may appear.

Do not assume a control is present or has the same label across iOS versions. Confirm it visually.

### Time picker

The standard picker has wheels for:

- Hours from 1 through 12.
- Minutes from 00 through 59.
- AM or PM.

The selected values occupy the highlighted center row. Adjust one wheel at a time with a vertical drag, screenshot, and verify its selected value before adjusting another. Before saving, verify the complete time including AM or PM.

### Repeat

Open **Repeat** and inspect all seven day rows. Selected days have a visible checkmark. More than one day may be selected.

The alarm summary may render selections as:

- **Never** for a one-time alarm.
- **Every Day**.
- **Weekdays**.
- **Weekends**.
- A list of specific abbreviated days.

For an existing alarm, changing any selected day requires the confirmation gate. After returning to the alarm screen, verify the rendered repeat summary before saving.

### Label

The default **Alarm** value is editable text, not a placeholder. To replace it:

1. Tap the visible label value and screenshot to verify the field is focused.
2. Select the full existing value using the visible iOS selection menu.
3. Call `type_text(phone_id, "requested label")`.
4. Screenshot and verify the complete rendered label in the correct field.
5. Stop before the keyboard checkmark, **Done**, **Save**, or any equivalent confirmation.
6. Confirm or save only as a separate, explicitly authorized action.

To clear a label, select all and use the visible **Cut** action, then screenshot and verify that the field is empty. An empty value may return to the default **Alarm** label after saving.

Avoid long-pressing adjacent settings rows or repeatedly tapping small clear controls when the target is uncertain.

### Sound and haptics

The sound screen can include:

- **Haptics** with **Synchronized (Default)**, standard patterns, custom vibration creation, and **None**.
- Store actions such as **Tone Store** and downloading purchased tones.
- A song picker connected to the Music library.
- Built-in ringtones.
- A **Classic** ringtone category.
- **None** for a silent alarm sound.

Standard haptic patterns can include **Accent**, **Alert**, **Heartbeat**, **Quick**, **Rapid**, **S.O.S.**, **Staccato**, and **Symphony**.

Built-in ringtones can include **Radial**, **Arpeggio**, **Breaking**, **Canopy**, **Chalet**, **Chirp**, **Daybreak**, **Departure**, **Dollop**, **Journey**, **Kettle**, **Little Bird**, **Mercury**, **Milky Way**, **Quad**, **Reflection**, **Scavenger**, **Seedling**, **Shelter**, **Sprinkles**, **Steps**, **Storytime**, **Tease**, **Tilt**, **Unfold**, and **Valley**.

Availability and defaults vary by iOS version and device. Read the current labels; do not infer that a listed option exists. Tapping a sound may play a preview immediately. For an existing alarm, selecting a sound or haptic requires the confirmation gate.

### Snooze and snooze duration

**Snooze** is a toggle. **Snooze Duration** may appear only while Snooze is enabled. When available, its inline picker can offer one-minute increments from 1 through 15 minutes; 9 minutes is a common default.

Do not rely on the default. Read the current value. For an existing alarm, changing either control requires the confirmation gate.

## Existing alarm operations

### Open for inspection

From a current screenshot, identify the row by all visible attributes. Tap the visible row or use the visible edit affordance. Opening it without modifying controls is allowed for inspection.

### Enable or disable

Treat toggling as a material schedule change:

1. Identify the exact row from a current screenshot.
2. Present the full visible identity and proposed enabled-state change.
3. Require confirmation.
4. Screenshot again, re-identify the target, tap its currently observed toggle, and verify the new state.

### Edit and save

After the target is identified, opening its edit screen does not itself change the alarm. Before changing a setting, complete the confirmation gate. After applying the confirmed edits, verify every proposed value on screen. Saving is a separate authorized action; verify the resulting list row afterward.

### Delete

iOS may expose deletion through a row swipe, edit mode, or a destructive control inside the edit screen. Choose only a deletion control visible in the current UI.

Always complete the confirmation gate before revealing or activating deletion. After confirmation, take a fresh screenshot and re-identify the target. Delete only that alarm, then verify it is absent without interacting with neighboring rows.

## Sleep | Wake Up

The **Sleep | Wake Up** section integrates with Health:

- An unconfigured state may show **No Alarm** and **Set Up**.
- Setup may explain that Sleep schedules are managed in Health and offer **Set Up in Health**.
- Once configured, Clock may show the next wake-up time and an entry point for changes.

Do not assume that Clock can edit every schedule attribute. If the flow opens Health, screenshot and reassess the visible context.

Before changing or deleting an existing Sleep/Wake Up alarm or schedule, capture a current view, identify every visible schedule attribute, present the exact change, and require confirmation. Do not continue when the current schedule cannot be distinguished confidently.
