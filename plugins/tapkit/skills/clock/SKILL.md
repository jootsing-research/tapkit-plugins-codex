---
name: clock
description: Layout and navigation of the Clock iPhone app — its screens, modes, and where every control is located. Use when operating Clock and you cannot find a control or a screen.
---

# Clock app UI map

Positions describe equal thirds of the screen in a 3×3 grid: upper left, upper center, upper right; middle left, center, middle right; lower left, lower center, lower right. Elements under **Fixed** — bars, popups, sheets — sit in the listed region whenever the mode is shown. Locate the described control visually within that region before tapping. Elements under **Variable position** move with scrolling content; scroll to reveal them.

## World clock

### Normal mode

The World Clock tab lists saved cities and their current local times, with editing and add controls above and the four-section Clock tab bar below.

**Fixed:**
- **Edit button — reveal world-clock delete and reorder controls** (upper left) → `world-clock.edit`
- **add city button — open city search without creating a clock** (upper right) → `city-search.normal`
- **World Clock tab — show saved world clocks** (lower left) → `world-clock.normal`
- **Alarms tab — show alarms and sleep schedule** (lower center) → `alarms.normal`
- **Stopwatch tab — show the stopwatch** (lower center) → `stopwatch.normal`
- **Timers tab — show timer controls and recents** (lower right) → `timers.normal`

**Variable position:**
- **saved city row — displays its relative day, UTC offset, city, and current time** (any saved city row; moves with the list) — *one of many*

### Edit mode

World Clock editing mode replaces Edit with a checkmark and adds delete and reorder controls to each saved city. Persistent removal and reordering are safety-blocked.

**Fixed:**
- **done button — leave editing mode without changing clocks** (upper left) → `world-clock.normal`
- **add city button — open city search without creating a clock** (upper right) → `city-search.normal`
- **World Clock tab — remain on World Clock editing mode** (lower left) → `world-clock.edit`
- **Alarms tab — show alarms and sleep schedule** (lower center) → `alarms.normal`
- **Stopwatch tab — show the stopwatch** (lower center) → `stopwatch.normal`
- **Timers tab — show timer controls and recents** (lower right) → `timers.normal`

**Variable position:**
- **delete city button — remove a saved world clock; safety-blocked** (delete button beside any saved city) — *mutates data* — *one of many*
- **city reorder handle — persistently reorder saved world clocks; safety-blocked** (reorder handle beside any saved city) — *mutates data* — *one of many*

## City search

### Normal mode

A modal city chooser with a search field and alphabetical city list. Choosing a city would add a persistent world clock and is safety-blocked.

**Fixed:**
- **close button — dismiss city search without adding a clock** (upper left)
- **search field — focus city-name filtering** (lower center) → `city-search.search`

**Variable position:**
- **city result — add the city to World Clock; safety-blocked** (any city result row; moves with the list) — *mutates data* — *one of many*

### Search mode

City search with the search field focused and keyboard visible; matching city rows remain safety-blocked.

**Fixed:**
- **cancel search button — dismiss the keyboard and clear the query** (middle right) → `city-search.normal`
- **focused search field — filters city results as text is entered** (center)
- **clear search button — remove the query** (middle right) → `city-search.search`

**Variable position:**
- **matching city result — add the city to World Clock; safety-blocked** (any matching city result row; moves with results) — *mutates data* — *one of many*

## Alarms

The Alarms tab shows sleep schedule setup and saved alarms, with edit and add controls and the Clock tab bar.

**Fixed:**
- **add alarm button — open creation of a persistent alarm; safety-blocked** (upper right) — *mutates data*
- **World Clock tab — show saved world clocks** (lower left) → `world-clock.normal`
- **Alarms tab — show alarms and sleep schedule** (lower center) → `alarms.normal`
- **Stopwatch tab — show the stopwatch** (lower center) → `stopwatch.normal`
- **Timers tab — show timer controls and recents** (lower right) → `timers.normal`

**Variable position:**
- **sleep schedule setup — configure a persistent sleep schedule; safety-blocked** (sleep schedule setup row) — *mutates data*
- **alarm enable switch — change an alarm's enabled state; safety-blocked** (any alarm enable switch; moves with the alarm list) — *mutates data* — *one of many*
- **saved alarm row — open persistent alarm editing; safety-blocked** (any saved alarm row; moves with the alarm list) — *mutates data* — *one of many*

## Stopwatch

### Normal mode

The reset stopwatch shows 00:00.00 with inactive Lap and green Start controls and an empty lap table.

**Fixed:**
- **inactive Lap button — unavailable before the stopwatch starts** (middle left)
- **Start button — start the ephemeral stopwatch** (middle right) → `stopwatch.running`
- **World Clock tab — show saved world clocks** (lower left) → `world-clock.normal`
- **Alarms tab — show alarms and sleep schedule** (lower center) → `alarms.normal`
- **Stopwatch tab — show the stopwatch** (lower center) → `stopwatch.normal`
- **Timers tab — show timer controls and recents** (lower right) → `timers.normal`

**Variable position:**
- **stopwatch face page gesture — switch from the digital to analog dial** (stopwatch face; drag left) → `stopwatch.analog-normal`

### Running mode

The stopwatch is counting, with active Lap and red Stop controls. This timing state is ephemeral.

**Fixed:**
- **Lap button — record an ephemeral lap** (middle left) → `stopwatch.running-with-lap`
- **Stop button — pause the stopwatch** (middle right) → `stopwatch.paused`

### Running with lap mode

The stopwatch continues counting and shows one or more lap rows beneath the controls.

**Fixed:**
- **Lap button — record another ephemeral lap** (middle left) → `stopwatch.running-with-lap`
- **Stop button — pause the stopwatch** (middle right) → `stopwatch.paused`

**Variable position:**
- **lap row — display a lap number and elapsed split** (any lap row; grows as laps are recorded) — *one of many*

### Paused mode

The stopwatch is paused, with white Reset and green Start controls and any recorded lap rows retained.

**Fixed:**
- **Reset button — clear ephemeral elapsed time and laps** (middle left) → `stopwatch.normal`
- **Start button — resume the ephemeral stopwatch** (middle right) → `stopwatch.running-with-lap`

**Variable position:**
- **lap row — display a retained lap number and split while paused** (any lap row; present when laps were recorded) — *one of many*

### Analog normal mode

The reset analog stopwatch presents a sixty-second dial with an inset thirty-minute dial, inactive Lap, green Start, and the second page indicator selected.

**Fixed:**
- **inactive Lap button — unavailable before the analog stopwatch starts** (middle left)
- **Start button — start the ephemeral analog stopwatch** (middle right) → `stopwatch.analog-running`

**Variable position:**
- **stopwatch face page gesture — switch back to the digital stopwatch** (analog stopwatch face; drag right) → `stopwatch.normal`

### Analog running mode

The analog stopwatch is running, with moving orange hands, active Lap, and red Stop controls.

**Fixed:**
- **Lap button — mark an ephemeral analog stopwatch lap** (middle left) → `stopwatch.analog-running`
- **Stop button — pause the analog stopwatch** (middle right) → `stopwatch.analog-paused`

### Analog paused mode

The analog stopwatch is paused, retaining its hand positions with Reset and green Start controls.

**Fixed:**
- **Reset button — clear the ephemeral analog stopwatch** (middle left) → `stopwatch.analog-normal`
- **Start button — resume the analog stopwatch** (middle right) → `stopwatch.analog-running`

## Timers

The Timers tab shows duration wheels, a When Timer Ends sound row, a green Start control, and recent timers when available.

**Fixed:**
- **When Timer Ends row — open timer alert-sound selection** (lower center) → `timer-sound.normal`
- **Start timer button — begin a timer using the selected duration; safety-blocked** (middle right) — *mutates data*
- **inactive Cancel button — unavailable until a timer is running** (middle left)
- **timer Label field — edit the prospective timer label; safety-blocked** (lower center) — *mutates data*
- **World Clock tab — show saved world clocks** (lower left) → `world-clock.normal`
- **Alarms tab — show alarms and sleep schedule** (lower center) → `alarms.normal`
- **Stopwatch tab — show the stopwatch** (lower center) → `stopwatch.normal`
- **Timers tab — show timer controls and recents** (lower right) → `timers.normal`

**Variable position:**
- **hours wheel — adjust a prospective timer duration; not exercised** (hours duration wheel) — *mutates data*
- **minutes wheel — adjust a prospective timer duration; not exercised** (minutes duration wheel) — *mutates data*
- **seconds wheel — adjust a prospective timer duration; not exercised** (seconds duration wheel) — *mutates data*
- **recent timer row — display a prior timer duration and label** (any recent timer row; moves with the recent list) — *one of many*
- **recent timer start button — begin that timer; safety-blocked** (any recent timer start button; moves with the recent list) — *mutates data* — *one of many*

## Timer sound

The When Timer Ends chooser lists alert sounds and a Stop Playing option; selecting a value would change the prospective timer setting and is safety-blocked.

**Fixed:**
- **close button — discard sound-picker changes and return to Timers** (upper left) → `timers.normal`
- **Set button — commit the selected timer sound; safety-blocked** (upper right) — *mutates data*

**Variable position:**
- **timer sound row — select the prospective alert sound; safety-blocked** (any sound row; moves with the sound list) — *mutates data* — *one of many*
- **Stop Playing row — select silent timer completion behavior; safety-blocked** (Stop Playing row near the bottom of the sound list) — *mutates data*
- **sound list — scroll through available alerts and reveal Stop Playing** (sound list content; moves while scrolling)
- **Tone Store row — leave Clock to browse purchasable tones; safety-blocked** (Tone Store row near the top of the sound list) — *mutates data*
- **Download All Purchased Tones row — download account purchases; safety-blocked** (Download All Purchased Tones row near the top of the sound list) — *mutates data*
