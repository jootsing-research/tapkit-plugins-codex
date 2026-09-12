---
name: reminders
description: Layout and navigation of the Reminders iPhone app — its screens, modes, and where every control is located. Use when operating Reminders and you cannot find a control or a screen.
---

# Reminders app UI map

Positions describe equal thirds of the screen in a 3×3 grid: upper left, upper center, upper right; middle left, center, middle right; lower left, lower center, lower right. Elements under **Fixed** — bars, popups, sheets — sit in the listed region whenever the mode is shown. Locate the described control visually within that region before tapping. Elements under **Variable position** move with scrolling content; scroll to reveal them.

## Welcome

The first-launch welcome sheet introduces Reminders features above a single Continue button.

**Fixed:**
- **continue button — advance through the UI-only welcome flow** (lower center) → `lists.icloud-prompt`

## Overview

### Normal mode

The Lists overview combines search, smart-list tiles, an iCloud syncing suggestion, the local Reminders list, and creation controls.

**Fixed:**
- **edit button — enter list reordering and management mode** (upper right) → `overview.edit`
- **search field — focus reminder search** (upper center) → `overview.search`
- **dictation button — start voice input for search** (upper right) — *mutates data*
- **today tile — show reminders due today** (upper left) → `today.normal`
- **scheduled tile — show reminders with scheduled dates** (upper right) → `scheduled.normal`
- **all tile — show all reminders** (upper left) → `all.normal`
- **completed tile — show completed reminders** (upper right) → `completed.normal`
- **dismiss iCloud suggestion button — hide the syncing suggestion** (middle right) — *mutates data*
- **go to settings link — leave Reminders for iCloud settings without changing anything** (middle left)
- **new reminder button — begin creating a reminder** (lower left) — *mutates data*
- **add list button — begin creating a list** (lower right) — *mutates data*

**Variable position:**
- **list row — open that reminder list** (any list row under My Lists) → `lists.normal` — *one of many*

### Edit mode

Lists editing mode shows visibility toggles and reorder handles for smart lists, plus deletion, information, and reorder controls for local lists.

**Fixed:**
- **done button — leave Lists editing mode** (upper right) → `overview.normal`
- **add list button — begin creating a list** (lower right) — *mutates data*

**Variable position:**
- **smart-list visibility checkmark — show or hide that smart list** (any smart-list visibility checkmark) — *mutates data* — *one of many*
- **smart-list reorder handle — rearrange the smart lists** (any smart-list reorder handle) — *mutates data* — *one of many*
- **remove list button — begin deleting the local list** (the minus button beside a local list) — *mutates data*
- **list information button — open the list appearance editor** (the information button beside a local list) → `list-info.normal`
- **list reorder handle — rearrange the local list** (the reorder handle beside a local list) — *mutates data*

### Search mode

Search mode focuses the search field over a dimmed Lists overview and adds a Cancel button.

**Fixed:**
- **search field — enter a transient reminder query** (upper center)
- **dictation button — start voice input for search** (upper right) — *mutates data*
- **cancel button — leave search without a query** (upper right) → `overview.normal`

## Lists

### Icloud prompt mode

The empty built-in Reminders list is dimmed beneath an alert asking whether to enable iCloud syncing in Settings.

**Fixed:**
- **back button — return to the presenting screen** (upper left)
- **more button — open list-management options** (upper right)
- **not now button — dismiss the syncing suggestion without changing settings** (middle left) → `lists.normal`
- **go to settings button — leave Reminders for its system settings without changing anything** (middle right)
- **new reminder button — begin creating a reminder** (lower left) — *mutates data*

### Normal mode

The empty built-in Reminders list shows no reminder rows, with back navigation, list options, and a New Reminder action.

**Fixed:**
- **back button — return to the Lists overview** (upper left)
- **more button — open list-management options** (upper right) → `lists.menu`
- **new reminder button — begin creating a reminder** (lower left) — *mutates data*

### Menu mode

A list-management popover overlays the empty list with information, selection, sorting, visibility, printing, and deletion actions.

**Fixed:**
- **show list info row — open unsaved name, icon, and color controls** (upper center) → `list-info.normal`
- **select reminders row — enter multi-selection mode** (upper center) → `lists.select`
- **sort by row — open sort criteria options** (upper center) → `lists.sort-menu`
- **show completed row — change whether completed reminders are visible** (upper center) — *mutates data*
- **print row — open the system print configuration** (upper center) → `print-options.normal`
- **delete list button — permanently delete this list after confirmation** (center) — *mutates data*

### Sort menu mode

The expanded Sort By submenu offers manual, due-date, creation-date, priority, and title ordering.

**Fixed:**
- **sort by row — collapse sort criteria options** (upper center) → `lists.menu`

**Variable position:**
- **sort criterion row — change the list ordering preference** (any sort criterion row) — *mutates data* — *one of many*

### Select mode

Selection mode for the empty list changes the title and exposes disabled bulk date, move, delete, and more actions.

**Fixed:**
- **done button — leave reminder selection mode** (upper right) → `lists.normal`

**Variable position:**
- **bulk action — change or delete selected reminders** (any disabled bulk action along the bottom) — *mutates data* — *one of many*

## List info

List Info presents unsaved appearance controls for the Reminders list, including its icon, name, and color palette.

**Fixed:**
- **cancel button — discard unsaved list appearance changes and return** (upper left)
- **done button — save list appearance changes** (upper right) — *mutates data*
- **current list icon preview — no action** (upper center)
- **list name field — edit the unsaved list name** (upper center) — *mutates data*

**Variable position:**
- **color swatch — choose an unsaved list color** (any color swatch in the palette) — *one of many*

## Today

### Normal mode

Today groups the empty due-today view into Morning, Afternoon, and Tonight sections.

**Fixed:**
- **back button — return to the Lists overview** (upper left)
- **more button — open Today view options** (upper right) → `today.menu`
- **new reminder button — begin creating a reminder due today** (lower left) — *mutates data*

### Menu mode

Today view options provide selection, time grouping, sorting, and printing.

**Fixed:**
- **select reminders row — enter selection mode** (upper center) → `today.select`
- **group by time row — change whether today is split into time-of-day sections** (upper center) — *mutates data*
- **sort by row — open Today sort criteria** (upper center) → `today.sort-menu`
- **print row — open the system print configuration** (upper center) → `print-options.normal`

### Sort menu mode

The expanded Today Sort By submenu offers due-date and other ordering criteria.

**Fixed:**
- **sort by row — collapse Today sort criteria** (upper center) → `today.menu`

**Variable position:**
- **sort criterion row — change Today ordering** (any sort criterion row) — *mutates data* — *one of many*

### Select mode

Today selection mode shows no reminder rows and disabled bulk actions.

**Fixed:**
- **done button — leave reminder selection mode** (upper right) → `today.normal`

**Variable position:**
- **bulk action — change or delete selected reminders** (any disabled bulk action along the bottom) — *mutates data* — *one of many*

## Scheduled

### Normal mode

Scheduled groups the empty view under Today, upcoming dates, later months, and future years.

**Fixed:**
- **back button — return to the Lists overview** (upper left)
- **more button — open Scheduled view options** (upper right) → `scheduled.menu`

**Variable position:**
- **scheduled content — scroll through future date groups** (the chronological scheduled-reminder content)

### Menu mode

Scheduled view options provide selection, completed-item visibility, and printing.

**Fixed:**
- **select reminders row — enter selection mode** (upper center) → `scheduled.select`
- **show completed row — change whether completed scheduled reminders are visible** (upper center) — *mutates data*
- **print row — open the system print configuration** (upper center) → `print-options.normal`

### Select mode

Scheduled selection mode exposes disabled bulk operations because there are no reminder rows.

**Fixed:**
- **done button — leave reminder selection mode** (upper right) → `scheduled.normal`

**Variable position:**
- **bulk action — change or delete selected reminders** (any disabled bulk action along the bottom) — *mutates data* — *one of many*

## All

### Normal mode

All groups every active reminder by source list; the local Reminders group is currently empty.

**Fixed:**
- **back button — return to the Lists overview** (upper left)
- **more button — open All view options** (upper right) → `all.menu`

### Menu mode

All view options provide selection, completed-item visibility, and printing.

**Fixed:**
- **select reminders row — enter selection mode** (upper center) → `all.select`
- **show completed row — change whether completed reminders are visible** (upper center) — *mutates data*
- **print row — open the system print configuration** (upper center) → `print-options.normal`

### Select mode

All selection mode exposes disabled bulk operations because there are no reminder rows.

**Fixed:**
- **done button — leave reminder selection mode** (upper right) → `all.normal`

**Variable position:**
- **bulk action — change or delete selected reminders** (any disabled bulk action along the bottom) — *mutates data* — *one of many*

## Completed

### Normal mode

Completed shows the completed reminder count and an empty completed-reminder area.

**Fixed:**
- **back button — return to the Lists overview** (upper left)
- **more button — open Completed view options** (upper right) → `completed.menu`
- **clear button — permanently clear completed reminders** (upper center) — *mutates data*

### Menu mode

Completed view options provide selection and printing.

**Fixed:**
- **select reminders row — enter selection mode** (upper center) → `completed.select`
- **print row — open the system print configuration** (upper center) → `print-options.normal`

### Select mode

Completed selection mode exposes disabled bulk operations because there are no completed reminder rows.

**Fixed:**
- **done button — leave reminder selection mode** (upper right) → `completed.normal`

**Variable position:**
- **bulk action — change or delete selected reminders** (any disabled bulk action along the bottom) — *mutates data* — *one of many*

## Print options

The system print sheet previews the empty list and offers printer, copies, paper, orientation, scaling, layout, sharing, and printing controls.

**Fixed:**
- **cancel button — dismiss printing and return to the list** (upper left)
- **share button — open destinations for exporting the print document** (upper right) — *mutates data*
- **print button — submit the configured print job** (upper right) — *mutates data*
- **printer row — choose a printer for the prospective job** (upper center) — *mutates data*
- **paper size row — choose paper size for the prospective job** (upper center) — *mutates data*
- **layout row — choose pages per sheet for the prospective job** (center) — *mutates data*

**Variable position:**
- **copies stepper — change the prospective copy count** (copies minus or plus button) — *mutates data* — *one of many*
- **orientation button — change the prospective page orientation** (portrait or landscape orientation button) — *mutates data* — *one of many*
- **scaling stepper — change the prospective print scale** (scaling minus or plus button) — *mutates data* — *one of many*
