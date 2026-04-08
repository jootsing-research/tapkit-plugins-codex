---
name: clock
description: This skill should be used when the user wants to use the Clock app, set alarms, use the stopwatch, set timers, view world clocks, manage alarm schedules, or interact with the Clock app on their iPhone.
---

# iOS Clock App — Usage Manual

## Opening the Clock App

The Clock app may not be on the main home screen. To open it reliably:

1. Open the **App Library** by swiping left past the last home screen page
2. Tap the **App Library** search bar at the top
3. Scroll to find **Clock** alphabetically (between Camera and Compass)
4. Tap **Clock** to open it

Alternatively, use `open_app("Clock")` — though on some devices this may not work reliably, in which case fall back to the App Library method above.

**Bundle ID:** `com.apple.mobiletimer`

**Always take a screenshot after each action to verify what's on screen.** Use visual landmarks (text labels, icons, positions like "top-left") rather than memorized coordinates.

---

## Navigation Layout

The Clock app has a **bottom tab bar** with four tabs. Tap a tab icon to switch between features.

| Tab | Icon | Position (approx.) | Description |
|-----|------|-------------------|-------------|
| **World Clock** | Globe | Bottom-left (~113, 1280) | View current time in different cities |
| **Alarms** | Alarm bell | Center-left (~245, 1280) | Set and manage alarms |
| **Stopwatch** | Stopwatch | Center-right (~375, 1280) | Time events with lap tracking |
| **Timers** | Circular arrow | Bottom-right (~507, 1280) | Set countdown timers |

The currently selected tab is highlighted in **orange text** with its icon filled.

---

## World Clock

**Purpose:** Display the current time in multiple cities around the world.

### Screen Layout
- **Title:** "World Clock" (top-left, large bold text)
- **Edit button:** Top-left — reorder or delete cities
- **+ button:** Top-right — add a new city
- **City list:** Each entry shows:
  - Time offset relative to your current timezone (e.g., "Today, -3HRS")
  - City name (e.g., "Cupertino")
  - Current time in that city (e.g., "7:30 PM")

### How to Add a City
1. Tap the **+** button (top-right, ~559, 98)
2. A search screen appears — type the city name
3. Tap the matching city from the results
4. The city is added to the World Clock list

### How to Remove/Reorder Cities
1. Tap **Edit** (top-left, ~75, 98)
2. Use the red minus icons to delete cities
3. Use the drag handles on the right to reorder
4. Tap **Done** when finished

---

## Alarms

**Purpose:** Set recurring or one-time alarms, including a Sleep | Wake Up schedule.

### Screen Layout
- **Title:** "Alarms" (top-left, large bold text)
- **Edit button:** Top-left (~75, 98) — enter edit mode (only visible when at least one alarm exists)
- **+ button:** Top-right (~559, 98) — add a new alarm
- **Sleep | Wake Up section:** At the top of the alarm list, with a bed icon
  - Shows "No Alarm" with an orange **"SET UP"** button if not configured
  - This integrates with the Health app's sleep schedule (see below)
- **"Other" section header:** Separates regular alarms from the Sleep | Wake Up section
- **Alarm list:** Each alarm entry shows:
  - **Time** in large text (e.g., "10:39 PM") on the left
  - **Label** in smaller gray text below the time (e.g., "Alarm")
  - **Toggle switch** on the right side — green when enabled, gray when disabled
  - When an alarm is **disabled**, the time and label text become dimmed/gray
  - If the alarm repeats, the repeat days appear below the label (e.g., "Mon Wed Fri")

### How to Add an Alarm
1. Tap the **+** button (top-right, ~559, 98)
2. The **"Add Alarm"** screen appears as a modal sheet with:
   - **X button** (top-left) — cancel without saving
   - **Orange checkmark button** (top-right) — save the alarm
   - **Time picker** — three scrollable wheels for hours, minutes, and AM/PM

3. Configure options (in a grouped settings list below the time picker):

#### Repeat
- Tap **Repeat** (shows "Never" by default) to open the Repeat screen
- Lists all 7 days: Every Sunday, Every Monday, Every Tuesday, Every Wednesday, Every Thursday, Every Friday, Every Saturday
- Tap a day to select it — an **orange checkmark** appears on the right
- Multiple days can be selected simultaneously
- Tap the **back arrow** (top-left) to return to the Add Alarm screen
- If no days are selected, the alarm fires once (shown as "Never")
- Common patterns shown on the Add Alarm screen: "Never", "Every Day", "Weekdays", "Weekends", or specific days like "Mon Wed Fri"

#### Label
- Tap the **Label** value text (right side of the row, shows "Alarm" by default) to activate editing
- A text cursor appears **after the existing text** and the keyboard slides up
- The default text "Alarm" is **real editable text**, not placeholder — you must clear it before typing a new label

**How to set a custom label (Select All + Paste):**

The default text "Alarm" is real editable text, so you need to replace it rather than just typing over it. Use the Select All + Paste flow:

1. `copy_text_to_phone("Your Label")` to load the new label onto the clipboard
2. Tap the Label value text (right side) to activate the field — cursor appears after existing text
3. `double_tap` on the word "Alarm" in the field to select it
4. Tap on an unhighlighted part of the Label row (a different spot from the selected word) — this shows the menu with **Select All**
5. Tap **Select All** to highlight everything
6. Tap **Paste** to replace the selected text with the clipboard contents
7. Tap the **blue checkmark button (✓)** on the keyboard to confirm the label and dismiss the keyboard

**To clear the Label field entirely**, follow the same flow but tap **Cut** instead of **Paste** in step 6.

**Important warnings:**
- **Do NOT use long-press** on the Label area — it may accidentally navigate to the Repeat screen or other adjacent rows
- **Do NOT use triple-tap** to try to select all text — it may deselect or defocus the field. Use the double-tap + tap-on-unhighlighted-text pattern instead.
- A small gray **(x) clear button** appears to the right of the label text during editing, but it is very small and difficult to tap precisely — **use Select All + Cut instead**
- If you save with an empty label field, the alarm defaults to the label "Alarm"
- The label appears below the time in the alarm list

#### Sound
- Tap **Sound** (shows "Radial" by default) to open the Sound screen
- The Sound screen has these sections (from top to bottom):

  **Haptics** (top of screen)
  - Tap to open the Haptics sub-screen with options:
    - **Synchronized (Default)** — selected by default (orange checkmark)
    - **Standard** section: Accent, Alert, Heartbeat, Quick, Rapid, S.O.S., Staccato, Symphony
    - **Custom** section: "Create New Vibration" (opens vibration creator)
    - **None** — disable haptics entirely

  **Store** section
  - **Tone Store** — opens the iTunes Store to purchase ringtones (orange link text)
  - **Download All Purchased Tones** — re-downloads previously purchased tones (orange link text)

  **Songs** section
  - **Pick a song** — opens the Music library to select a song as the alarm sound

  **Ringtones** section (scrollable list, alphabetical)
  - The currently selected ringtone shows an **orange checkmark** on the left
  - Tapping a ringtone plays a preview and selects it
  - Available built-in ringtones: Radial (Default), Arpeggio, Breaking, Canopy, Chalet, Chirp, Daybreak, Departure, Dollop, Journey, Kettle, Little Bird, Mercury, Milky Way, Quad, Reflection, Scavenger, Seedling, Shelter, Sprinkles, Steps, Storytime, Tease, Tilt, Unfold, Valley
  - **Classic** — a sub-category (with chevron) containing legacy ringtones from older iOS versions

  **None** (bottom of list)
  - Select to have no sound (vibration/haptics only)

- Tap the **back arrow** (top-left) to return to the Add Alarm screen

#### Snooze
- **Toggle switch** — enabled (green) by default
- When snooze is **ON**, the alarm will offer a snooze option when it fires

#### Snooze Duration
- Only visible when the **Snooze** toggle is ON — hidden when snooze is OFF
- Tap to open an **inline scroll picker** that appears below the row
- Range: **1 min to 15 min** (in 1-minute increments)
- Default: **9 min**
- The currently selected value is shown in orange text on the right

4. Tap the **orange checkmark** (top-right) to save the alarm

### How to Edit an Existing Alarm

There are two ways to open the Edit Alarm screen:

**Method 1 — Tap directly (outside edit mode):**
- Tap on the alarm's **time text** in the alarm list
- The **"Edit Alarm"** screen opens immediately

**Method 2 — Via Edit mode:**
1. Tap **Edit** (top-left, ~75, 98)
2. The screen enters edit mode:
   - The **Edit** button changes to a **checkmark (Done)** button
   - A **red minus (-)** circle appears on the left of each alarm
   - A **chevron (>)** appears on the right of each alarm
   - The toggle switches are hidden
3. Tap the **chevron (>)** next to an alarm to open the Edit Alarm screen

The **Edit Alarm** screen is identical to the Add Alarm screen, with one addition:
- A **"Delete Alarm"** button in red text at the bottom of the screen
- The title says **"Edit Alarm"** instead of "Add Alarm"

### How to Toggle an Alarm On/Off
- Each alarm has a **toggle switch** on the right side (~547, same row as alarm time)
- Tap it to enable (green) or disable (gray)
- When disabled, the alarm time and label text become dimmed/gray
- The alarm remains in the list but will not fire until re-enabled

### How to Delete an Alarm

There are three ways to delete an alarm:

**Method 1 — Swipe to delete (quickest):**
- Swipe **left** on the alarm row to reveal a red **Delete** button (trash can icon) on the right
- Tap the trash can to delete the alarm

**Method 2 — Edit mode delete:**
1. Tap **Edit** (top-left)
2. Tap the **red minus (-)** circle on the left side of the alarm
3. A red **Delete** button (trash can icon) slides in from the right
4. Tap the trash can to confirm deletion

**Method 3 — From the Edit Alarm screen:**
1. Open the Edit Alarm screen (tap the alarm time, or use Edit > chevron)
2. Scroll to the bottom and tap **"Delete Alarm"** (red text)

### Sleep | Wake Up Section

The Sleep | Wake Up feature at the top of the Alarms screen integrates with the **Health app**:

- When **not configured**: Shows "No Alarm" with an orange **"SET UP"** button
- Tapping **"SET UP"** opens a modal with:
  - A purple bed icon
  - Title: **"Sleep is Now in Health"**
  - Description: "Once you have set up your new Sleep schedule, you can change your alarm in Clock. You can also set a sleep goal, create a wind down routine, and more."
  - **X button** (top-left) to dismiss
  - **"Set Up in Health"** orange button at the bottom — redirects to the Health app's sleep setup
- Once configured in Health, the wake-up alarm time and schedule appear in this section
- The wake-up alarm can be modified from the Clock app after initial Health setup

### Time Picker Details

The time picker on the Add/Edit Alarm screen uses three scrollable wheels:
- **Hours** wheel (left): 1–12
- **Minutes** wheel (center): 00–59
- **AM/PM** wheel (right): AM or PM
- Drag up/down on each wheel to change the value
- The selected value is highlighted in the center row with a gray highlight bar behind it
- Values above and below the selection are shown in progressively smaller/dimmer text

---

## Stopwatch

**Purpose:** Time events with precision, with optional lap tracking.

### Screen Layout
- **Display:** Large digital readout showing **MM:SS.CC** (minutes, seconds, centiseconds) centered on screen
- **Lap button:** Left side (~85, 660) — gray/disabled when stopped
- **Start button:** Right side (~535, 660) — green circle
- **Page dots:** Two dots in the center (~310, 660) indicating two view modes:
  - **Digital view** (default) — numeric display
  - **Analog view** — swipe left to see an analog stopwatch face
- **Lap list:** Appears below the buttons when laps are recorded

### How to Use
1. Tap **Start** (green button, right side) to begin timing
   - Start changes to a red **Stop** button
   - Lap button becomes active (white)
2. Tap **Lap** (left button) to record a lap time
   - Lap times appear in a list below
3. Tap **Stop** (red button) to pause
   - Lap button changes to **Reset** (left side)
4. Tap **Reset** to clear the stopwatch back to 00:00.00

### Switching Views
- Swipe left/right on the stopwatch area to toggle between digital and analog views (indicated by the two page dots)

---

## Timers

**Purpose:** Set countdown timers with customizable duration and end sound.

### Screen Layout
- **Title:** "Timers" (top-left, large bold text)
- **Time picker:** Three scrollable wheels:
  - **Hours** (left column, ~155, 500)
  - **Minutes** (center column, ~310, 500)
  - **Seconds** (right column, ~470, 500)
- **Cancel button:** Left side (~85, 720) — gray circle
- **Start button:** Right side (~535, 720) — green circle
- **Label field:** Below the buttons — defaults to "Timer", tap to rename
- **When Timer Ends:** Below label — tap to choose the alert sound (shows current sound, e.g., "Radial")

### How to Set a Timer
1. Scroll the **hours**, **minutes**, and **seconds** wheels to set the desired duration
   - Drag up to increase, drag down to decrease
2. Optionally tap **Label** to give the timer a custom name
3. Optionally tap **When Timer Ends** to change the alert sound
4. Tap **Start** (green button) to begin the countdown
   - The display switches to show the remaining time counting down
   - **Pause** and **Cancel** buttons replace Start/Cancel

### How to Cancel a Running Timer
1. Tap **Cancel** (left button) to stop and dismiss the timer
   - Or tap **Pause** to temporarily stop without resetting

---

## Key Workflows

### Set an Alarm
```
1. open_app("Clock") → screenshot to verify
2. Tap the Alarms tab (~245, 1280)
3. Tap the + button (top-right, ~559, 98)
4. screenshot → verify Add Alarm screen
5. Drag hours/minutes/AM-PM wheels to set the time
6. Tap the orange checkmark (top-right) to save
7. screenshot → verify alarm appears in list
```

### Start a Timer
```
1. open_app("Clock") → screenshot to verify
2. Tap the Timers tab (~507, 1280)
3. Scroll the hours/minutes/seconds wheels to set duration
4. Tap Start (green button, ~535, 720)
5. screenshot → verify countdown is running
```

### Use the Stopwatch
```
1. open_app("Clock") → screenshot to verify
2. Tap the Stopwatch tab (~375, 1280)
3. Tap Start (green button, ~535, 660)
4. Tap Lap to record lap times
5. Tap Stop to pause
6. screenshot → verify times recorded
```

## Tips and Gotchas

- **The Clock app uses a dark theme** (black background, white text) by default.
- **Time picker wheels** require vertical drag gestures — not taps.
- **Back navigation**: Back arrow (top-left) or swipe right from left edge.
- **Label field quirks**: The Label field in Add/Edit Alarm contains real editable text ("Alarm") by default — use the Select All + Paste flow described above to replace it.
