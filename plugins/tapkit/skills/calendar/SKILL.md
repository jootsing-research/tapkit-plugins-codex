---
name: calendar
description: Layout and navigation of the Calendar iPhone app — its screens, modes, and where every control is located. Use when operating Calendar and you cannot find a control or a screen.
---

# Calendar app UI map

Positions describe equal thirds of the screen in a 3×3 grid: upper left, upper center, upper right; middle left, center, middle right; lower left, lower center, lower right. Elements under **Fixed** — bars, popups, sheets — sit in the listed region whenever the mode is shown. Locate the described control visually within that region before tapping. Elements under **Variable position** move with scrolling content; scroll to reveal them.

## Day

The day schedule shows a week strip above an hourly timeline, with navigation and calendar controls around it.

**Fixed:**
- **month button — open the current month grid** (upper left) → `month.normal`
- **view options button — change the day presentation** (upper center)
- **search button — enter calendar search** (upper right)
- **add button — open a new item form** (upper right)
- **today button — return the calendar to today** (lower left)
- **calendars button — open calendar visibility controls** (lower center) → `calendars.normal`
- **inbox button — open calendar invitations** (lower right) → `inbox.normal`

**Variable position:**
- **week-strip date — show that date in the day schedule** (any date in the week strip near the top) — *one of many*
- **hourly timeline — scroll to earlier or later hours** (the hourly timeline; moves as the schedule scrolls)
- **empty time slot — open a new event at that time** (the hourly timeline background)

## Calendars

The Calendars sheet groups available calendars, controls visibility, and offers calendar information and management actions.

**Fixed:**
- **done button — return to the presenting calendar view** (upper right)
- **on my iphone disclosure — expand or collapse local calendars** (upper right)
- **other disclosure — expand or collapse subscribed and system calendars** (upper right)
- **show completed reminders toggle — show or hide completed reminders** (middle right) — *mutates data*
- **add calendar button — open calendar creation options** (lower left) — *mutates data*
- **hide all button — hide every calendar** (lower right) — *mutates data*

**Variable position:**
- **calendar visibility checkmark — show or hide that calendar** (any calendar visibility checkmark) — *mutates data* — *one of many*
- **calendar information button — open calendar settings** (any calendar information button) → `calendar-edit.normal` — *one of many*

## Calendar edit

Edit Calendar shows the calendar name, color, and Event Alerts setting, with Cancel and Done controls.

**Fixed:**
- **cancel button — discard unsaved calendar setting changes** (upper left)
- **done button — save calendar setting changes** (upper right) — *mutates data*
- **calendar name field — edit the unsaved calendar name** (upper center)
- **color row — choose a calendar color** (upper center) → `calendar-color.normal`
- **event alerts toggle — enable or disable alerts for this calendar** (middle right) — *mutates data*

## Calendar color

### Normal mode

Calendar Color lists the standard colors and a Custom option for the unsaved calendar settings.

**Fixed:**
- **back button — return to the presenting screen** (upper left)
- **custom row — open the system color picker** (center) → `calendar-color.custom`

**Variable position:**
- **standard color row — choose that unsaved calendar color** (any standard calendar color row) — *one of many*

### Custom mode

The system Colors sheet overlays Calendar Color with Grid, Spectrum, and Sliders tabs plus palettes and an eyedropper.

**Fixed:**
- **eyedropper button — sample a color from the screen** (middle left)
- **close button — dismiss the system color picker** (middle right) → `calendar-color.normal`
- **grid tab — show the color grid** (middle left)
- **spectrum tab — show the color spectrum** (center)
- **sliders tab — show numeric color sliders** (middle right)
- **add color button — add the current color to saved swatches** (lower center) — *mutates data*

**Variable position:**
- **color grid cell — choose that unsaved color** (any color cell in the color grid) — *one of many*
- **saved color swatch — choose that unsaved color** (any saved color swatch near the bottom) — *one of many*

## Inbox

The Inbox sheet switches between New and Replied calendar invitations; this account currently has no invitations.

**Fixed:**
- **new segment — show unanswered invitations** (upper center)
- **replied segment — show invitations already answered** (upper center)
- **done button — return to the presenting calendar view** (upper right)

## Year

### Normal mode

The year overview shows all twelve miniature month grids, with global search, add, and bottom navigation controls.

**Fixed:**
- **search button — enter calendar search** (upper right) → `year.search`
- **add button — open a new item form** (upper right) → `new-item.event`
- **today button — return the calendar to today** (lower left)
- **calendars button — open calendar visibility controls** (lower center) → `calendars.normal`
- **inbox button — open calendar invitations** (lower right) → `inbox.normal`

**Variable position:**
- **miniature month grid — open that month** (any miniature month grid) — *one of many*
- **year overview — swipe vertically to move between years** (the year overview; swipe vertically to move between years)

### Search mode

Calendar search overlays and dims the year overview, with a focused search field, dictation control, cancel button, and Today shortcut.

**Fixed:**
- **search field — enter a calendar query** (upper center) → `year.search-query`
- **dictation button — request voice input** (upper right) → `year.dictation-prompt`
- **cancel button — close calendar search** (upper right) → `year.normal`
- **today button — keep the current year centered while search is open** (lower left)

### Search query mode

Calendar search shows an entered query and its results area; this query has no results, and a clear button replaces the dictation control.

**Fixed:**
- **search field — edit the calendar query** (upper center)
- **clear button — remove the search query** (upper right) → `year.search`
- **cancel button — close calendar search** (upper right)
- **today button — return the calendar to today** (lower left)

### Dictation prompt mode

A system alert over Calendar asks whether to enable Dictation and offers a dismissal or privacy information.

**Fixed:**
- **enable dictation button — enable the system Dictation feature** (center) — *mutates data*
- **not now button — dismiss the Dictation prompt** (center) → `year.search`
- **privacy information link — show Siri and Dictation privacy details** (center) → `dictation-privacy.normal`

## Dictation privacy

### Normal mode

A system privacy sheet explains Siri and Dictation data handling in scrollable text.

**Fixed:**
- **done button — return to the presenting prompt** (upper right)

**Variable position:**
- **apple.com privacy link — open Apple's legal page outside Calendar** (the apple.com privacy URL in the explanatory text)
- **privacy text — scroll through the details** (the privacy text; swipe vertically to read more) → `dictation-privacy.scrolled`

### Scrolled mode

The privacy sheet is scrolled away from the top, with a compact sticky title above the explanatory text.

**Fixed:**
- **done button — return to the presenting prompt** (upper right)

**Variable position:**
- **privacy text — continue scrolling through the details** (the privacy text; swipe vertically to continue reading)

## New item

### Event mode

The New Event form edits an unsaved calendar event, with Event selected and scheduling, recurrence, calendar, alert, and attachment controls visible.

**Fixed:**
- **cancel button — discard the unsaved item and return** (upper left)
- **add button — save the new event** (upper right) — *mutates data*
- **event segment — keep the new item form configured for an event** (upper left)
- **reminder segment — switch the new item form to a reminder** (upper right) → `new-item.reminder`
- **title field — enter the event title** (upper center)
- **location or video call field — edit event location details** (upper center)
- **all-day toggle — switch between all-day and timed event** (middle right)
- **date button — edit the visible event date** (center)
- **time button — edit the visible event time** (middle right)
- **date button — edit the visible event date** (center)
- **time button — edit the visible event time** (middle right)
- **travel time row — choose travel time** (center)
- **repeat row — choose event recurrence** (center)
- **calendar row — choose the destination calendar** (lower center)
- **alert row — choose an event alert** (lower center)
- **add attachment row — open attachment selection** (lower left)

**Variable position:**
- **form content — scroll to reveal additional controls** (the New Event form; swipe vertically to reveal more fields)

### Reminder mode

The New Reminder form edits an unsaved reminder with title, notes, date and time, repeat, list, details, and quick metadata controls.

**Fixed:**
- **cancel button — discard the unsaved item and return** (upper left) → `new-item.reminder-discard`
- **add button — save the new reminder** (upper right) — *mutates data*
- **event segment — switch the new item form to an event** (upper left)
- **reminder segment — keep the new item form configured for a reminder** (upper right)
- **title field — enter the reminder title** (upper center)
- **notes field — enter reminder notes** (center)
- **date row — expand the reminder date picker** (center) → `new-item.reminder-date`
- **time row — expand or collapse the time picker** (center)
- **time toggle — enable or disable a reminder time** (middle right)
- **repeat row — choose a recurrence rule** (center) → `repeat.normal`
- **list row — choose a Reminders list** (lower center) → `reminder-list.normal`
- **details row — open location and priority settings** (lower center) → `reminder-details.normal`
- **reminder metadata button — edit its displayed metadata** (lower left)
- **reminder metadata button — edit its displayed metadata** (lower center)
- **reminder metadata button — edit its displayed metadata** (lower center)
- **reminder metadata button — edit its displayed metadata** (lower right)

### Reminder discard mode

A confirmation sheet asks whether to discard the unsaved reminder changes or return to editing.

**Fixed:**
- **discard changes button — abandon the unsaved reminder and return** (lower center)
- **cancel button — return to editing the unsaved reminder** (lower center)

### Reminder date mode

The New Reminder form has its inline monthly date picker expanded beneath the Date row.

**Fixed:**
- **cancel button — discard the unsaved item and return** (upper left)
- **add button — save the new reminder** (upper right) — *mutates data*
- **event segment — switch the new item form to an event** (upper left)
- **reminder segment — switch the new item form to a reminder** (upper right)
- **title field — edit the unsaved title** (upper center)
- **notes field — edit the unsaved notes** (center)
- **date row — expand or collapse the date picker** (center)
- **month and year heading — open the wheel picker** (middle left) → `new-item.reminder-date-wheel`
- **previous month button — show the preceding month** (middle right)
- **next month button — show the following month** (middle right)
- **time row — expand or collapse the reminder time picker** (lower center)
- **time toggle — enable or disable the reminder time** (lower right)
- **repeat row — choose a recurrence rule** (lower center)

**Variable position:**
- **date cell — choose the visible date** (any date cell in the inline reminder calendar) — *one of many*
- **form content — scroll to reveal additional controls** (the New Reminder form while the date picker is expanded)

### Reminder date wheel mode

The reminder date picker shows separate month and year wheels beneath the expanded month and year heading.

**Fixed:**
- **cancel button — discard the unsaved item and return** (upper left)
- **add button — save the new reminder** (upper right) — *mutates data*
- **event segment — switch the new item form to an event** (upper left)
- **reminder segment — switch the new item form to a reminder** (upper right)
- **title field — edit the unsaved title** (upper center)
- **notes field — edit the unsaved notes** (center)
- **date row — expand or collapse the date picker** (center)
- **month and year heading — switch date picker style** (middle left)
- **time row — expand or collapse the reminder time picker** (lower center)
- **time toggle — enable or disable the reminder time** (lower right)
- **repeat row — choose a recurrence rule** (lower center)

**Variable position:**
- **picker wheel — change the visible unsaved value** (the month wheel in the left half of the inline picker)
- **picker wheel — change the visible unsaved value** (the year wheel in the right half of the inline picker)
- **New Reminder form — scroll while the date wheels are expanded** (the New Reminder form while the date wheel picker is expanded) → `new-item.reminder-date-wheel-scrolled`

### Reminder date wheel scrolled mode

The New Reminder form is scrolled while the month and year wheels remain expanded, revealing Repeat, List, and Details.

**Fixed:**
- **cancel button — discard the unsaved item and return** (upper left)
- **add button — save the new reminder** (upper right) — *mutates data*
- **event segment — switch the new item form to an event** (upper left)
- **reminder segment — switch the new item form to a reminder** (upper right)
- **frequency or date row — open its visible picker** (upper center)
- **month and year heading — return to the monthly calendar** (upper left) → `new-item.reminder-date-scrolled`
- **time row — expand or collapse the reminder time picker** (center)
- **time toggle — enable or disable the reminder time** (middle right)
- **repeat row — choose a recurrence rule** (lower center)
- **list row — choose a Reminders list** (lower center)
- **details row — open reminder details** (lower center)

**Variable position:**
- **month wheel — choose the reminder month** (the month wheel in the left half of the inline picker)
- **year wheel — choose the reminder year** (the year wheel in the right half of the inline picker)
- **picker wheel — change the visible unsaved value** (the New Reminder form while scrolled with date wheels expanded)

### Reminder date scrolled mode

The New Reminder form is scrolled while the monthly date picker is expanded, revealing Time, Repeat, List, and Details beneath it.

**Fixed:**
- **cancel button — discard the unsaved item and return** (upper left)
- **add button — save the new reminder** (upper right) — *mutates data*
- **event segment — switch the new item form to an event** (upper left)
- **reminder segment — switch the new item form to a reminder** (upper right)
- **frequency or date row — open its visible picker** (upper center)
- **month and year heading — switch date picker style** (upper left)
- **previous month button — show the preceding month** (upper right)
- **next month button — show the following month** (upper right)
- **time row — expand the reminder time picker** (center) → `new-item.reminder-time`
- **time toggle — enable or disable the reminder time** (middle right)
- **repeat row — choose a recurrence rule** (lower center)
- **list row — choose a Reminders list** (lower center)
- **details row — open reminder details** (lower center)

**Variable position:**
- **date cell — choose the reminder date** (any date cell in the inline reminder calendar) — *one of many*
- **form content — scroll to reveal additional controls** (the New Reminder form while scrolled with the monthly date picker expanded)

### Reminder time mode

The New Reminder form has its inline hour, minute, and AM/PM time wheels expanded beneath the Time row.

**Fixed:**
- **cancel button — discard the unsaved item and return** (upper left)
- **add button — save the new reminder** (upper right) — *mutates data*
- **event segment — switch the new item form to an event** (upper left)
- **reminder segment — switch the new item form to a reminder** (upper right)
- **title field — edit the unsaved title** (upper center)
- **notes field — edit the unsaved notes** (center)
- **date row — expand or collapse the date picker** (center)
- **time row — collapse the reminder time picker** (center) → `new-item.reminder`
- **time toggle — enable or disable a reminder time** (middle right)
- **repeat row — choose a recurrence rule** (lower center)
- **list row — choose a Reminders list** (lower center)

**Variable position:**
- **hour wheel — choose the reminder hour** (the hour wheel in the left third of the inline time picker)
- **minute wheel — choose the reminder minute** (the minute wheel in the center of the inline time picker)
- **AM/PM wheel — choose morning or evening** (the AM/PM wheel in the right third of the inline time picker)
- **form content — scroll to reveal additional controls** (the New Reminder form while the time picker is expanded)

## Reminder details

### Normal mode

Reminder Details configures location-based notification and priority for the unsaved reminder.

**Fixed:**
- **back button — return to the presenting screen** (upper left)
- **add button — save the new reminder** (upper right) — *mutates data*
- **location toggle — open Reminders notification onboarding outside Calendar** (upper right) → `reminder-details.precise-location-alert`
- **priority row — open the priority menu** (upper center) → `reminder-details.priority-menu`

### Priority menu mode

Reminder Details shows a popup menu with None, Low, Medium, and High priority choices.

**Fixed:**
- **back button — return to the presenting screen** (upper left)
- **add button — save the new reminder** (upper right) — *mutates data*
- **location toggle — configure a location reminder** (upper right)
- **priority row — open the priority menu** (upper center)

**Variable position:**
- **priority option — choose reminder priority** (any priority option in the popup menu) → `reminder-details.normal` — *one of many*

### Precise location alert mode

A system alert over Reminder Details says Precise Location is off and offers dismissal or a Settings shortcut.

**Fixed:**
- **not now button — dismiss the precise location alert** (middle left) → `reminder-details.location-on`
- **go to settings button — open precise location settings outside Calendar** (middle right) — *mutates data*

### Location on mode

Reminder Details has Location enabled, revealing Current, Getting In, Getting Out, Custom, and location-information controls.

**Fixed:**
- **back button — return to the presenting screen** (upper left)
- **add button — save the new reminder** (upper right) — *mutates data*
- **location toggle — disable location-based reminder controls** (upper right) → `reminder-details.normal`
- **current button — use the device's current location** (upper left)
- **getting in button — notify when entering a vehicle** (upper center)
- **getting out button — notify when leaving a vehicle** (upper center)
- **custom button — choose a custom location** (upper right)
- **location field — search for a reminder location** (center)
- **location information button — show location guidance** (middle right)
- **priority row — open the priority menu** (center)

## Reminder list

The List chooser shows the available Reminders lists for the unsaved reminder.

**Fixed:**
- **back button — return to the presenting screen** (upper left)

**Variable position:**
- **reminder list row — choose the destination list** (any available reminder list row) → `new-item.reminder` — *one of many*

## Repeat

The Repeat chooser lists standard recurrence presets and a Custom option for the unsaved reminder.

**Fixed:**
- **back button — return to the presenting screen** (upper left)
- **custom row — configure a custom recurrence** (lower center) → `repeat-custom.normal`

**Variable position:**
- **recurrence preset row — choose a standard repeat rule** (any standard recurrence preset row) → `new-item.reminder` — *one of many*

## Repeat custom

### Normal mode

The Custom recurrence screen sets a frequency and interval for the unsaved reminder.

**Fixed:**
- **back button — return to the presenting screen** (upper left)
- **frequency row — expand the recurrence frequency picker** (upper center) → `repeat-custom.frequency`
- **every row — edit the recurrence interval** (upper center)

### Frequency mode

The Custom recurrence screen has a Daily, Weekly, Monthly, and Yearly frequency wheel expanded.

**Fixed:**
- **back button — return to the presenting screen** (upper left)
- **frequency or date row — open its visible picker** (upper center)
- **interval row — edit the displayed interval** (center)

**Variable position:**
- **frequency wheel — choose a recurrence frequency** (the recurrence frequency wheel) → `repeat-custom.frequency-weekly`

### Frequency weekly mode

The expanded frequency picker is set to Weekly, adding selectable weekday rows beneath the interval.

**Fixed:**
- **back button — return to the presenting screen** (upper left)
- **frequency row — collapse the recurrence frequency picker** (upper center)
- **every row — edit the weekly recurrence interval** (upper center)

**Variable position:**
- **frequency wheel — choose another recurrence frequency** (the recurrence frequency wheel) → `repeat-custom.frequency-monthly`
- **weekday row — toggle a weekday in the weekly recurrence** (any weekday row below the custom recurrence controls) → `repeat-custom.weekly` — *one of many*

### Frequency monthly mode

The expanded frequency picker is set to Monthly and shows day-of-month and relative-day recurrence choices.

**Fixed:**
- **back button — return to the presenting screen** (upper left)
- **frequency or date row — open its visible picker** (upper center)
- **interval row — edit the displayed interval** (center)
- **each row — use explicit recurrence values** (center)
- **on the row — use a relative recurrence rule** (lower center)

**Variable position:**
- **picker wheel — change the visible unsaved value** (the recurrence frequency wheel)
- **numbered day cell — toggle a day of the month** (any numbered day cell in the monthly recurrence grid) → `repeat-custom.monthly` — *one of many*

### Monthly mode

The collapsed custom recurrence is set to Monthly and shows day-of-month and relative-day choices.

**Fixed:**
- **back button — return to the presenting screen** (upper left)
- **frequency or date row — open its visible picker** (upper center)
- **interval row — edit the recurrence interval** (upper center)
- **each row — use explicit recurrence values** (center)
- **on the row — use a relative weekday rule** (center) → `repeat-custom.monthly-relative`

**Variable position:**
- **numbered day cell — toggle a day of the month** (any numbered day cell in the monthly recurrence grid) — *one of many*

### Monthly relative mode

The Monthly recurrence uses an ordinal and weekday wheel to choose a relative day such as the first Sunday.

**Fixed:**
- **back button — return to the presenting screen** (upper left)
- **frequency row — expand the recurrence frequency picker** (upper center) → `repeat-custom.frequency-monthly-relative`
- **interval row — edit the recurrence interval** (upper center)
- **each row — use explicit recurrence values** (center)
- **on the row — use a relative recurrence rule** (center)

**Variable position:**
- **ordinal wheel — choose which occurrence in the month** (the ordinal wheel in the left half of the relative monthly picker)
- **weekday wheel — choose the weekday for the relative monthly rule** (the weekday wheel in the right half of the relative monthly picker)

### Frequency monthly relative mode

The frequency wheel is expanded for a Monthly relative-day recurrence while the ordinal and weekday wheels remain visible below.

**Fixed:**
- **back button — return to the presenting screen** (upper left)
- **frequency or date row — open its visible picker** (upper center)
- **interval row — edit the displayed interval** (center)
- **each row — use explicit recurrence values** (center)
- **on the row — use a relative recurrence rule** (lower center)

**Variable position:**
- **frequency wheel — choose another recurrence frequency** (the recurrence frequency wheel) → `repeat-custom.frequency-yearly`
- **picker wheel — change the visible unsaved value** (the ordinal wheel in the left half of the relative monthly picker)
- **picker wheel — change the visible unsaved value** (the weekday wheel in the right half of the relative monthly picker)

### Frequency yearly mode

The expanded frequency picker is set to Yearly and shows selectable months plus a Days of Week toggle.

**Fixed:**
- **back button — return to the presenting screen** (upper left)
- **frequency or date row — open its visible picker** (upper center)
- **interval row — edit the displayed interval** (center)
- **days of week toggle — use relative weekdays in selected months** (lower right)

**Variable position:**
- **picker wheel — change the visible unsaved value** (the recurrence frequency wheel)
- **month cell — toggle a month in the yearly recurrence** (any month cell in the yearly recurrence grid) → `repeat-custom.yearly` — *one of many*

### Yearly mode

The collapsed custom recurrence is set to Yearly and shows selectable months plus a Days of Week toggle.

**Fixed:**
- **back button — return to the presenting screen** (upper left)
- **frequency or date row — open its visible picker** (upper center)
- **interval row — edit the recurrence interval** (upper center)
- **days of week toggle — use a relative weekday in each selected month** (middle right) → `repeat-custom.yearly-weekday`

**Variable position:**
- **month cell — choose the visible month** (any month cell in the yearly recurrence grid) — *one of many*

### Yearly weekday mode

The Yearly recurrence has Days of Week enabled, revealing ordinal and weekday wheels beneath the selected months.

**Fixed:**
- **back button — return to the presenting screen** (upper left)
- **frequency or date row — open its visible picker** (upper center)
- **interval row — edit the recurrence interval** (upper center)
- **days of week toggle — enable or disable relative weekdays** (middle right)

**Variable position:**
- **month cell — choose the visible month** (any month cell in the yearly recurrence grid) — *one of many*
- **ordinal wheel — choose which weekday occurrence in each selected month** (the ordinal wheel in the left half of the yearly weekday picker)
- **weekday wheel — choose the weekday for the yearly rule** (the weekday wheel in the right half of the yearly weekday picker)

### Weekly mode

The collapsed custom recurrence is set to Weekly and shows selectable weekday rows.

**Fixed:**
- **back button — return to the presenting screen** (upper left)
- **frequency or date row — open its visible picker** (upper center)
- **every row — expand the recurrence interval picker** (upper center) → `repeat-custom.weekly-interval`

**Variable position:**
- **weekday row — toggle the visible weekday** (any weekday row below the custom recurrence controls) — *one of many*

### Weekly interval mode

The Weekly custom recurrence has its numeric interval wheel expanded above the weekday rows.

**Fixed:**
- **back button — return to the presenting screen** (upper left)
- **frequency row — switch from interval editing to the frequency picker** (upper center) → `repeat-custom.frequency-weekly`
- **interval row — edit the recurrence interval** (upper center)

**Variable position:**
- **interval wheel — choose how many weeks between occurrences** (the numeric recurrence interval wheel)
- **weekday row — toggle the visible weekday** (any weekday row below the custom recurrence controls) — *one of many*

## Month

The month grid shows one month at a time with tappable dates, year navigation, view controls, and the bottom navigation bar.

**Fixed:**
- **year button — open the year overview** (upper left) → `year.normal`
- **view options button — change the month presentation** (upper center)
- **search button — enter calendar search** (upper right)
- **add button — open a new item form** (upper right)
- **today button — return the calendar to today** (lower left)
- **calendars button — open calendar visibility controls** (lower center) → `calendars.normal`
- **inbox button — open calendar invitations** (lower right) → `inbox.normal`

**Variable position:**
- **date cell — choose the visible date** (any date cell in the month grid) — *one of many*
- **month grid — swipe vertically to move between months** (the month grid; swipe vertically to move between months)
