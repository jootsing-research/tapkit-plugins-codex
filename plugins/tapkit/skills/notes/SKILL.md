---
name: notes
description: Layout and navigation of the Notes iPhone app — its screens, modes, and where every control is located. Use when operating Notes and you cannot find a control or a screen.
---

# Notes app UI map

Positions describe equal thirds of the screen in a 3×3 grid: upper left, upper center, upper right; middle left, center, middle right; lower left, lower center, lower right. Elements under **Fixed** — bars, popups, sheets — sit in the listed region whenever the mode is shown. Locate the described control visually within that region before tapping. Elements under **Variable position** move with scrolling content; scroll to reveal them.

## Folders

The folder browser, listing local Notes and Recently Deleted beneath controls for folder creation, editing, search, and composition.

**Fixed:**
- **new folder button — creates a folder** (upper right) — *mutates data*
- **edit button — toggle folder editing; system folders and bottom controls become disabled** (upper right)
- **Notes folder row — open the Notes folder** (upper center) → `notes-list.normal`
- **Recently Deleted row — open deleted notes** (center) → `deleted-list.normal`
- **search field — open Notes search** (lower center) → `search.normal`
- **dictation button — open search and request voice dictation** (lower right) → `search.dictation-prompt`
- **compose button — creates a new note** (lower right) — *mutates data*

## Notes list

### Normal mode

The Notes folder's note list, with folder navigation and actions above, one repeating note row, and search and compose controls below.

**Fixed:**
- **back button — return to the presenting screen** (upper left)
- **more button — open note-list view and selection actions** (upper right) → `notes-list.more-menu`
- **search field — open Notes search** (lower center) → `search.normal`
- **dictation button — open search and request voice dictation** (lower right) → `search.dictation-prompt`
- **compose button — creates a new note** (lower right) — *mutates data*

**Variable position:**
- **note row — open the note** (any note row; moves as the list scrolls) → `note.normal` — *one of many*

### More menu mode

The note list with its view, selection, sorting, grouping, and attachment actions menu open.

**Fixed:**
- **View as Gallery button — show notes as preview cards** (upper center) → `notes-list.gallery`
- **Select Notes button — enter note selection mode** (upper center) → `notes-list.select`
- **Sort By button — open note sort choices** (upper center) → `notes-list.sort-menu`
- **Group By Date button — open date-grouping choices** (upper center) → `notes-list.group-menu`
- **View Attachments button — open the folder's attachment browser** (center) → `attachments.normal`

### Group menu mode

The note-list actions menu with date grouping expanded to choose default, on, or off.

**Fixed:**
- **Group By Date button — collapse the date-grouping choices** (upper center) → `notes-list.more-menu`
- **Default option — restore default date grouping** (center) → `notes-list.normal`
- **On option — group notes into date sections** (center) → `notes-list.normal`
- **Off option — show an ungrouped note list** (center) → `notes-list.normal`

### Sort menu mode

The note-list actions menu with sorting expanded to choose a key and direction.

**Fixed:**
- **Sort By button — collapse the sort choices** (upper center) → `notes-list.more-menu`
- **Default option — restore the default Date Edited sort key** (upper center) → `notes-list.normal`
- **Date Edited option — sort notes by last edit date** (center) → `notes-list.normal`
- **Date Created option — sort notes by creation date** (center) → `notes-list.normal`
- **Title option — sort notes alphabetically by title** (center) → `notes-list.normal`
- **Newest First or Ascending option — use the primary direction for the selected sort key** (center) → `notes-list.normal`
- **Oldest First or Descending option — use the reverse direction for the selected sort key** (center) → `notes-list.normal`

### Select mode

The note list in selection mode, with note selection circles, Done, and bulk move and delete actions.

**Fixed:**
- **done button — leave note selection mode** (upper right) → `notes-list.normal`
- **Move All button — moves all notes** (lower left) — *mutates data*
- **Delete All button — deletes all notes** (lower right) — *mutates data*

**Variable position:**
- **note selection circle — toggle that note's selection** (any note row selection circle) — *one of many*

### Gallery mode

The Notes folder displayed as gallery preview cards instead of list rows.

**Fixed:**
- **back button — return to the presenting screen** (upper left)
- **more button — open gallery view and selection actions** (upper right) → `notes-list.gallery-more-menu`
- **search field — open Notes search** (lower center) → `search.normal`
- **dictation button — open search and request voice dictation** (lower right) → `search.dictation-prompt`
- **compose button — creates a new note** (lower right) — *mutates data*

**Variable position:**
- **note gallery card — open the note** (any note gallery card; moves as the gallery scrolls) → `note.normal` — *one of many*

### Gallery more menu mode

The gallery with its view, selection, sorting, grouping, and attachment actions menu open.

**Fixed:**
- **View as List button — show notes as list rows** (upper center) → `notes-list.normal`
- **Select Notes button — enter note selection mode** (upper center) → `notes-list.select`
- **Sort By button — open note sort choices** (upper center) → `notes-list.sort-menu`
- **Group By Date button — open date-grouping choices** (upper center) → `notes-list.group-menu`
- **View Attachments button — open the folder's attachment browser** (center) → `attachments.normal`

## Note

### Normal mode

An existing note in read mode, with its scrollable body and navigation and action controls around the edges.

**Fixed:**
- **back button — return to the presenting screen** (upper left)
- **undo button — reverses the last edit to the note** (upper center) — *mutates data*
- **share button — open the system share sheet** (upper right) → `note.share-sheet`
- **more button — open note actions** (upper right) → `note.more-menu`
- **checklist button — inserts a checklist into the note** (lower left) — *mutates data*
- **attachment button — open the attachment menu** (lower left) → `note.attachment-menu`
- **markup button — enter markup mode** (lower center) → `note.markup`
- **compose button — creates a new note** (lower right) — *mutates data*

**Variable position:**
- **note body — enter editing mode and place the insertion point** (note body; content moves as the note scrolls) → `note.editing`
- **note body drag — select text and open the selection menu** (note body; drag across text) → `note.selection`
- **note body swipe — scroll through the note** (note body; swipe vertically to scroll)

### More menu mode

The note in read mode with its actions menu open.

**Fixed:**
- **Scan button — scans and attaches content to the note** (upper center) — *mutates data*
- **Pin Note button — pins the note** (upper center) — *mutates data*
- **Lock button — locks the note** (upper right) — *mutates data*
- **Find in Note button — open in-note search** (upper center) → `note.find`
- **Move Note button — moves the note to another folder** (upper center) — *mutates data*
- **Recent Notes button — open the recent-note submenu** (upper center) → `note.recent-notes-menu`
- **Math Results button — open math-result behavior choices** (center) → `note.math-results-menu`
- **Lines & Grids button — changes the note background layout** (center) — *mutates data*
- **Attachment View button — open attachment sizing choices** (center) → `note.attachment-view-menu`
- **Delete button — deletes the note** (center) — *mutates data*

### Selection mode

The note with text selected and the contextual Add Link and Find Selection menu visible.

**Fixed:**
- **back button — return to the presenting screen** (upper left)
- **share button — open the system share sheet** (upper right) → `note.share-sheet`
- **more button — open note actions** (upper right) → `note.more-menu`
- **Add Link button — adds a link to the selected text** (center) — *mutates data*
- **Find Selection button — search within the note** (center) → `note.find`

### Attachment view menu mode

The note actions menu with Attachment View expanded to choose small or large attachment presentation.

**Fixed:**
- **Attachment View button — collapse attachment sizing choices** (center) → `note.more-menu`
- **Set All to Small option — display all attachments at small size** (center) → `note.normal`
- **Set All to Large option — display all attachments at large size** (center) → `note.normal`

### Math results menu mode

The note actions menu with Math Results expanded to choose automatic insert, suggestions, or off.

**Fixed:**
- **Math Results button — collapse math-result behavior choices** (upper center) → `note.more-menu`
- **Insert Results option — automatically insert calculated math results** (center) → `note.normal`
- **Suggest Results option — show suggested math results without inserting them** (center) → `note.normal`
- **Off option — disable automatic math results** (center) → `note.normal`

### Recent notes menu mode

The note actions menu with Recent Notes expanded into a nested list of recent destinations and menu management.

**Fixed:**
- **Recent Notes button — collapse the recent-note submenu** (upper center) → `note.more-menu`
- **New Note button — creates a new note** (center) — *mutates data*
- **Clear Menu button — clears the recent-note menu** (center) — *mutates data*

**Variable position:**
- **recent note row — switch to that note** (any existing note row in the Recent Notes submenu) → `note.normal` — *one of many*

### Editing mode

The note with an insertion point and keyboard open; the top-right compose control becomes Done and an editing toolbar appears above the keyboard.

**Fixed:**
- **back button — return to the presenting screen** (upper left)
- **undo button — reverses the last edit to the note** (upper center) — *mutates data*
- **share button — open the system share sheet** (upper center) → `note.share-sheet`
- **more button — open note actions** (upper right) → `note.markup-more-menu`
- **done button — saves edits and dismisses the keyboard** (upper right) — *mutates data*
- **format button — open the Format panel** (middle left) → `note.format`
- **checklist button — inserts a checklist into the note** (middle left) — *mutates data*
- **table button — inserts a table into the note** (center) — *mutates data*
- **attachment button — open the attachment menu** (center) → `note.attachment-menu`
- **markup button — enter markup mode** (middle right) → `note.markup`

**Variable position:**
- **editable note body — place the insertion point** (note body; content moves as the note scrolls)

### Share sheet mode

The system share sheet over the note, with destination apps and content actions; sharing destinations are safety-blocked.

**Fixed:**
- **Copy button — copies the note to the clipboard** (middle left) — *mutates data*
- **Export as Markdown button — exports the note as Markdown** (center) — *mutates data*
- **Markup button — creates a marked-up share representation** (center) — *mutates data*
- **View More button — opens more share actions** (middle right) — *mutates data*

**Variable position:**
- **share destination — sends or adds the note through the selected app** (any destination app in the horizontally scrolling share row) — *mutates data* — *one of many*
- **share sheet panel — swipe down to expand the share actions** (share sheet panel; swipe down to dismiss) → `note.share-sheet-expanded`
- **outside area — dismiss the share sheet** (outside the share sheet) → `note.normal`

### Share sheet expanded mode

The expanded system share sheet with the full action list and a close button.

**Fixed:**
- **close button — close the share sheet** (upper right) → `note.normal`
- **Copy button — copies the note to the clipboard** (middle left) — *mutates data*
- **Export as Markdown button — exports the note as Markdown** (center) — *mutates data*
- **Markup button — creates a marked-up share representation** (center) — *mutates data*
- **View Less button — collapse the share actions** (middle right) → `note.share-sheet`
- **Print button — opens printing for the note** (center) — *mutates data*
- **Save to Files button — saves an exported note file** (center) — *mutates data*
- **Edit Actions button — changes the share sheet action list** (center) — *mutates data*

**Variable position:**
- **share destination — sends or adds the note through the selected app** (any destination app in the horizontally scrolling share row) — *mutates data* — *one of many*

### Markup mode

The note in markup mode, with drawing tools along the bottom and Done replacing the editor toolbar.

**Fixed:**
- **back button — return to the presenting screen** (upper left)
- **undo button — reverses the last markup edit** (upper center) — *mutates data*
- **more button — open note actions** (upper right) → `note.markup-more-menu`
- **done button — saves markup and leaves markup mode** (upper right) — *mutates data*
- **pen tool — select the pen for markup** (lower left)
- **pencil tool — select the pencil for markup** (lower left)
- **highlighter tool — select the highlighter for markup** (lower center)
- **eraser tool — select the eraser for markup** (lower center)
- **color button — open the markup color panel** (lower right) → `note.color-grid`
- **add button — open the markup insert menu** (lower right) → `note.markup-add-menu`

**Variable position:**
- **note canvas — draw markup on the note** (note canvas) — *mutates data*

### Color grid mode

Markup's Colors panel on the Grid tab, with color swatches, HDR boost and opacity sliders, presets, and color-view tabs.

**Fixed:**
- **eyedropper button — sample a color from the screen** (upper left) → `note.eyedropper`
- **close button — close the Colors panel** (upper right) → `note.markup`
- **Grid tab — show the color grid** (upper left)
- **Spectrum tab — show the continuous color spectrum** (upper center) → `note.color-spectrum-expanded`
- **Sliders tab — show numeric RGB color controls** (upper right) → `note.color-sliders-expanded`
- **HDR boost slider — adjust extended-range brightness for the drawing color** (lower center)
- **opacity slider — adjust drawing color opacity** (lower center)
- **add preset button — saves the current color as a preset** (lower center) — *mutates data*

**Variable position:**
- **color cell — select the drawing color** (any color cell in the grid) — *one of many*
- **preset color swatch — select a preset drawing color** (any preset color swatch near the bottom of the Colors panel) — *one of many*

### Eyedropper mode

Markup with the movable eyedropper loupe over the note for sampling an on-screen color.

**Variable position:**
- **eyedropper loupe — drag to sample a color and release to return to the expanded Colors panel** (eyedropper loupe; moves over the screen) → `note.color-grid-expanded`

### Color grid expanded mode

Markup's Colors panel expanded upward on the Grid tab, showing the same controls with a taller sheet.

**Fixed:**
- **eyedropper button — sample a color from the screen** (upper left) → `note.eyedropper`
- **close button — close the Colors panel** (upper right) → `note.markup`
- **Grid tab — show the color grid** (upper left)
- **Spectrum tab — show the continuous color spectrum** (upper center) → `note.color-spectrum-expanded`
- **Sliders tab — show numeric RGB color controls** (upper right) → `note.color-sliders-expanded`
- **HDR boost slider — adjust extended-range brightness for the drawing color** (lower center)
- **opacity slider — adjust drawing color opacity** (lower center)
- **add preset button — saves the current color as a preset** (lower center) — *mutates data*

**Variable position:**
- **color cell — select the drawing color** (any color cell in the expanded grid) — *one of many*
- **preset color swatch — select a preset drawing color** (any preset color swatch near the bottom of the expanded Colors panel) — *one of many*
- **Colors panel header — drag to change the sheet height** (Colors panel header; drag vertically to change the sheet height)

### Color sliders expanded mode

The expanded Colors panel on the Sliders tab, with RGB sliders and values, a hex color field, HDR boost, opacity, and presets.

**Fixed:**
- **eyedropper button — sample a color from the screen** (upper left) → `note.eyedropper`
- **close button — close the Colors panel** (upper right) → `note.markup`
- **Grid tab — show the color grid** (upper left) → `note.color-grid-expanded`
- **Spectrum tab — show the continuous color spectrum** (upper center) → `note.color-spectrum-expanded`
- **Sliders tab — show numeric RGB color controls** (upper right)
- **red slider — adjust the red color component** (upper center)
- **red value field — focus numeric entry for the red component** (upper right) → `note.color-sliders-keyboard`
- **green slider — adjust the green color component** (center)
- **green value field — focus numeric entry for the green component** (middle right)
- **blue slider — adjust the blue color component** (center)
- **blue value field — focus numeric entry for the blue component** (middle right)
- **hex color field — focus direct hexadecimal color entry** (middle right)
- **HDR boost slider — adjust extended-range brightness for the drawing color** (lower center)
- **opacity slider — adjust drawing color opacity** (lower center)
- **add preset button — saves the current color as a preset** (lower center) — *mutates data*

**Variable position:**
- **preset color swatch — select a preset drawing color** (any preset color swatch near the bottom of the expanded Colors panel) — *one of many*
- **Colors panel header — drag to change the sheet height** (Colors panel header; drag vertically to change the sheet height)

### Color sliders keyboard mode

The Sliders color panel expanded to full height with the numeric keyboard open for direct component or hex entry.

**Fixed:**
- **eyedropper button — sample a color from the screen** (upper left) → `note.eyedropper`
- **close button — close the Colors panel** (upper right) → `note.markup`
- **Grid tab — show the color grid** (upper left) → `note.color-grid-expanded`
- **Spectrum tab — show the continuous color spectrum** (upper center) → `note.color-spectrum-expanded`
- **Sliders tab — show numeric RGB color controls** (upper right)
- **red slider — adjust the red color component** (upper center)
- **red value field — focus numeric entry for the red component** (upper right)
- **green slider — adjust the green color component** (upper center)
- **green value field — focus numeric entry for the green component** (upper right)
- **blue slider — adjust the blue color component** (center)
- **blue value field — focus numeric entry for the blue component** (middle right)
- **hex color field — focus direct hexadecimal color entry** (middle right)
- **HDR boost slider — adjust extended-range brightness for the drawing color** (center)
- **HDR boost value field — focus numeric entry for HDR boost** (middle right)

### Color spectrum expanded mode

The expanded Colors panel on the Spectrum tab, with a continuous color field plus HDR boost, opacity, and preset controls.

**Fixed:**
- **eyedropper button — sample a color from the screen** (upper left) → `note.eyedropper`
- **close button — close the Colors panel** (upper right) → `note.markup`
- **Grid tab — show the color grid** (upper left) → `note.color-grid-expanded`
- **Spectrum tab — show the continuous color spectrum** (upper center)
- **Sliders tab — show numeric RGB color controls** (upper right) → `note.color-sliders-expanded`
- **HDR boost slider — adjust extended-range brightness for the drawing color** (lower center)
- **opacity slider — adjust drawing color opacity** (lower center)
- **add preset button — saves the current color as a preset** (lower center) — *mutates data*

**Variable position:**
- **spectrum point — select the drawing color** (any point in the color spectrum)
- **preset color swatch — select a preset drawing color** (any preset color swatch near the bottom of the expanded Colors panel) — *one of many*
- **Colors panel header — drag to change the sheet height** (Colors panel header; drag vertically to change the sheet height)

### Markup add menu mode

Markup mode with the insert menu open above the drawing toolbar.

**Fixed:**
- **Add Sticker button — choose and add a sticker** (center) — *mutates data*
- **Add Text button — add a text box** (center) — *mutates data*
- **Add Signature button — choose and add a signature** (lower center) — *mutates data*
- **Add Shape button — add a shape** (lower center) — *mutates data*
- **Add Loupe button — add a magnifier** (lower center) — *mutates data*
- **add button — close the markup insert menu** (lower right) → `note.markup`

### Markup more menu mode

Markup mode with the note actions menu open, including search, navigation, viewing, layout, and destructive actions.

**Fixed:**
- **Scan button — scans and attaches content to the note** (upper left) — *mutates data*
- **Pin Note button — pins the note** (upper center) — *mutates data*
- **Lock button — locks the note** (upper right) — *mutates data*
- **Find in Note button — open in-note search** (upper center) → `note.find`
- **Move Note button — moves the note to another folder** (upper center) — *mutates data*
- **Recent Notes button — open the recent-note submenu** (upper center) → `note.recent-notes-menu`
- **Math Results button — open math-result behavior choices** (center) → `note.math-results-menu`
- **Lines & Grids button — changes the note background layout** (center) — *mutates data*
- **Attachment View button — open attachment sizing choices** (center) → `note.attachment-view-menu`
- **Delete button — deletes the note** (center) — *mutates data*

### Find mode

The note with in-note search focused above the keyboard, plus previous and next match controls.

**Fixed:**
- **back button — return to the presenting screen** (upper left)
- **undo button — reverses the last edit to the note** (upper center) — *mutates data*
- **share button — open the system share sheet** (upper right) → `note.share-sheet`
- **more button — open note actions** (upper right) → `note.more-menu`
- **close search button — leave in-note search** (middle left) → `note.normal`
- **search field — enter an in-note query** (center) → `note.find-results`
- **previous match button — move to the previous search result** (middle right)
- **next match button — move to the next search result** (middle right)

### Find results mode

In-note search with a query and matching text highlighted; the field shows result position and gains a clear button.

**Fixed:**
- **back button — return to the presenting screen** (upper left)
- **undo button — reverses the last edit to the note** (upper center) — *mutates data*
- **share button — open the system share sheet** (upper right) → `note.share-sheet`
- **more button — open note actions** (upper right) → `note.more-menu`
- **close search button — leave in-note search** (middle left) → `note.normal`
- **search field — edit the in-note query** (center)
- **clear query button — clear the in-note search** (middle right) → `note.find`
- **previous match button — move to the previous search result** (middle right)
- **next match button — move to the next search result** (middle right)

### Attachment menu mode

The note editor with an attachment menu above the keyboard for scanned, captured, chosen, recorded, or filed content.

**Fixed:**
- **Scan Text button — scan and insert recognized text** (upper center) — *mutates data*
- **Scan Documents button — scan and attach documents** (upper center) — *mutates data*
- **Take Photo or Video button — capture and attach a photo or video** (center) — *mutates data*
- **Choose Photo or Video button — choose and attach media** (center) — *mutates data*
- **Record Audio button — record and attach audio** (center) — *mutates data*
- **Attach File button — choose and attach a file** (center) — *mutates data*

**Variable position:**
- **outside area — dismiss the attachment menu** (outside the attachment menu) → `note.editing`

### Format mode

The note editor with a Format panel covering the keyboard, offering paragraph styles, character styling, lists, indentation, and block quotation.

**Fixed:**
- **close button — close the Format panel** (lower right) → `note.editing`
- **Title style button — format the current paragraph as a title** (lower left) — *mutates data*
- **Heading style button — format the current paragraph as a heading** (lower left) — *mutates data*
- **Subheading style button — format the current paragraph as a subheading** (lower center) — *mutates data*
- **Body style button — format the current paragraph as body text** (lower right) — *mutates data*
- **bold button — toggle bold formatting** (lower left) — *mutates data*
- **italic button — toggle italic formatting** (lower left) — *mutates data*
- **underline button — toggle underline formatting** (lower center) — *mutates data*
- **strikethrough button — toggle strikethrough formatting** (lower center) — *mutates data*
- **highlight button — apply highlighting to text** (lower right) — *mutates data*
- **text color button — change the text color** (lower right) — *mutates data*
- **dashed list button — format the current paragraph as a dashed list** (lower left) — *mutates data*
- **bulleted list button — format the current paragraph as a bulleted list** (lower left) — *mutates data*
- **numbered list button — format the current paragraph as a numbered list** (lower center) — *mutates data*
- **decrease indent button — decrease the paragraph indentation** (lower center) — *mutates data*
- **increase indent button — increase the paragraph indentation** (lower right) — *mutates data*
- **block quote button — toggle block quotation formatting** (lower right) — *mutates data*

## Attachments

The folder attachment browser; this folder currently has no attachments.

**Fixed:**
- **close button — return to the presenting note-list view** (upper left)

## Search

### Normal mode

Notes search with the keyboard open and suggested smart filters above an empty query field.

**Fixed:**
- **search field — enter a Notes query** (center) → `search.results`
- **dictation button — request voice dictation for the search field** (middle right) → `search.dictation-prompt`
- **close button — leave Notes search** (middle right)

**Variable position:**
- **suggested smart-filter row — filter notes by that category** (any suggested smart-filter row) → `search.results` — *one of many*

### Dictation prompt mode

A system privacy prompt over Notes search asking whether to enable Dictation.

**Fixed:**
- **Enable Dictation button — enables system Dictation** (center) — *mutates data*
- **Not Now button — leave Dictation disabled and dismiss the prompt** (center) → `search.keyboard-hidden`
- **Dictation privacy link — open Siri and Dictation privacy information** (lower center)

### Keyboard hidden mode

Notes search with suggested smart filters and the keyboard dismissed; the search controls sit at the bottom edge.

**Fixed:**
- **search field — focus Notes search and open the keyboard** (lower center) → `search.normal`
- **dictation button — request voice dictation for the search field** (lower right) → `search.dictation-prompt`
- **close button — leave Notes search** (lower right)

**Variable position:**
- **suggested smart-filter row — filter notes by that category** (any suggested smart-filter row) → `search.results` — *one of many*

### Results mode

Notes search with an active query or smart-filter token and matching notes, or an empty-results message.

**Fixed:**
- **search field — edit the active Notes query** (center)
- **clear query button — clear the search query or filter token** (middle right) → `search.normal`
- **close button — leave Notes search** (middle right)

**Variable position:**
- **active-folder search result — open the matching note** (any search result row from an active folder) → `note.normal` — *one of many*
- **Recently Deleted search result — open the deleted note** (any search result row from Recently Deleted) → `deleted-note.normal` — *one of many*

## Deleted note

A note opened from Recently Deleted, with destructive delete, recovery, and compose actions.

**Fixed:**
- **back button — return to the presenting screen** (upper left)
- **delete button — permanently deletes the note** (lower left) — *mutates data*
- **recover or move button — restores the deleted note to a folder** (lower left) — *mutates data*
- **compose button — creates a new note** (lower right) — *mutates data*

## Deleted list

### Normal mode

The Recently Deleted folder, showing its retention notice and deleted-note rows with edit and search controls.

**Fixed:**
- **back button — return to the folder browser** (upper left)
- **Edit button — enter deleted-note selection mode** (upper right) → `deleted-list.select`
- **search field — open Notes search** (lower center) → `search.normal`
- **dictation button — open search and request voice dictation** (lower right) → `search.dictation-prompt`
- **compose button — creates a new note** (lower right) — *mutates data*

**Variable position:**
- **deleted-note row — open the deleted note** (any deleted-note row; moves as the list scrolls) → `deleted-note.normal` — *one of many*

### Select mode

Recently Deleted in selection mode, with selection circles, Done, and bulk move and permanent-delete actions.

**Fixed:**
- **done button — leave deleted-note selection mode** (upper right) → `deleted-list.normal`
- **Move All button — restores all deleted notes to a folder** (lower left) — *mutates data*
- **Delete All button — permanently deletes all deleted notes** (lower right) — *mutates data*

**Variable position:**
- **deleted-note selection circle — toggle that note's selection** (any deleted-note selection circle) — *one of many*
