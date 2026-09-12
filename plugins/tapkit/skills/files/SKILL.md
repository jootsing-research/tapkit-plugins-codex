---
name: files
description: Layout and navigation of the Files iPhone app — its screens, modes, and where every control is located. Use when operating Files and you cannot find a control or a screen.
---

# Files app UI map

Positions describe equal thirds of the screen in a 3×3 grid: upper left, upper center, upper right; middle left, center, middle right; lower left, lower center, lower right. Elements under **Fixed** — bars, popups, sheets — sit in the listed region whenever the mode is shown. Locate the described control visually within that region before tapping. Elements under **Variable position** move with scrolling content; scroll to reveal them.

## Recents

### Normal mode

The Recents root shows a searchable grid of recently used files with a More menu and the Recents, Shared, and Browse tab bar.

**Fixed:**
- **more button — open view, sort, selection, scanning, and server options** (upper right) → `recents.more-menu`
- **search field — enter Recents search mode** (upper center) → `recents.search`
- **dictation button — begin voice input for Recents search; safety-blocked because it records audio** (upper right) — *mutates data*
- **recents tab — show recently used files** (lower left) → `recents.normal`
- **shared tab — show shared files and collaboration activity** (lower center) → `shared.normal`
- **browse tab — show storage locations and favorites** (lower right) → `browse.normal`

**Variable position:**
- **file thumbnail — opens the selected user file; safety-blocked because opening may download or change recency metadata** (any file thumbnail; moves with the grid) — *mutates data* — *one of many*
- **cloud download button — downloads the file to the device; safety-blocked** (cloud download icon beside an offloaded file; moves with the grid) — *mutates data* — *one of many*

### More menu mode

The Recents More popover offers selection, document scanning, server connection, icon or list layout, and sort choices.

**Fixed:**
- **select button — enter file selection mode** (upper center) → `recents.select`
- **scan documents button — open the document scanner** (upper right) → `document-scanner.normal`
- **connect to server button — open the server connection form** (upper right) → `connect-server.normal`
- **icons layout button — show files as an icon grid and close the menu** (upper center) → `recents.normal`
- **list layout button — show files as a list** (upper center) → `recents.list`
- **sort by name button — sort files by name and close the menu** (center) → `recents.normal`
- **sort by kind button — sort files by kind and close the menu** (center) → `recents.normal`
- **sort by date button — sort files by date and close the menu** (center) → `recents.normal`
- **sort by size button — sort files by size and close the menu** (center) → `recents.normal`
- **sort by tags button — sort files by tag and close the menu** (center) → `recents.normal`
- **background — dismiss the More popover** (middle left) → `recents.normal`

### Select mode

Recents selection mode shows selection circles on each file, Select All and Done controls, and disabled share, move, delete, and More actions until a file is selected.

**Fixed:**
- **select all button — select every visible file** (upper left) → `recents.selected`
- **done button — leave selection mode** (upper right) → `recents.normal`
- **share button — share selected files; disabled with no selection and safety-blocked** (lower left) — *mutates data*
- **move button — move selected files; disabled with no selection and safety-blocked** (lower left) — *mutates data*
- **delete button — delete selected files; disabled with no selection and safety-blocked** (lower center) — *mutates data*
- **more actions button — disabled until a file is selected** (lower right)

**Variable position:**
- **file selection circle — select a file without opening it** (selection circle on any file thumbnail; moves with the grid) → `recents.selected` — *one of many*

### Selected mode

Recents selection mode with one or more files selected enables selection actions; all data-changing actions remain safety-blocked.

**Fixed:**
- **select all button — select every visible file** (upper left) → `recents.selected`
- **done button — clear the selection and leave selection mode** (upper right) → `recents.normal`
- **share button — share selected files; safety-blocked** (lower left) — *mutates data*
- **move button — move selected files; safety-blocked** (lower left) — *mutates data*
- **delete button — delete selected files; safety-blocked** (lower center) — *mutates data*
- **more actions button — open actions for selected files; safety-blocked because its actions can alter or disclose user data** (lower right) — *mutates data*

**Variable position:**
- **file selection circle — toggle that file's selection** (selection circle on any file thumbnail; moves with the grid) → `recents.selected` — *one of many*

### List mode

Recents in list layout shows each recent file as a row with its date and size, while retaining search, More, and the root tab bar.

**Fixed:**
- **more button — open view, sort, selection, scanning, and server options** (upper right) → `recents.more-menu`
- **search field — enter Recents search mode** (upper center) → `recents.search`
- **dictation button — begin voice input for Recents search; safety-blocked because it records audio** (upper right) — *mutates data*
- **recents tab — show recently used files** (lower left) → `recents.list`
- **shared tab — show shared files and collaboration activity** (lower center) → `shared.normal`
- **browse tab — show storage locations and favorites** (lower right) → `browse.normal`

**Variable position:**
- **file row — opens the selected user file; safety-blocked because opening may download or change recency metadata** (any file row; moves with the list) — *mutates data* — *one of many*
- **cloud download button — downloads the file to the device; safety-blocked** (cloud download icon beside an offloaded file row; moves with the list) — *mutates data* — *one of many*

### Search mode

Recents search mode focuses a live search field above the current files, shows a layout toggle and cancel button, and raises the keyboard.

**Fixed:**
- **search field — enter text to filter recent files live** (upper center)
- **dictation button — begin voice input for search; safety-blocked because it records audio** (upper center) — *mutates data*
- **layout toggle — switch search results between list and icon layouts** (upper right) → `recents.search`
- **cancel search button — close the keyboard and return to Recents** (upper right) → `recents.list`

**Variable position:**
- **matching file result — opens the selected user file; safety-blocked because opening may download or change recency metadata** (any matching file row or thumbnail; moves with results) — *mutates data* — *one of many*
- **cloud download button — downloads the file to the device; safety-blocked** (cloud download icon beside an offloaded result; moves with results) — *mutates data* — *one of many*

### Search query mode

Recents live search with text entered replaces dictation with a clear button and offers a Name Contains suggestion above the keyboard.

**Fixed:**
- **search field — edit the live search query** (upper center)
- **clear search button — erase the query and return to empty search** (upper center) → `recents.search`
- **layout toggle — switch search results between list and icon layouts** (upper right) → `recents.search-query`
- **cancel search button — discard the query, close the keyboard, and return to Recents** (upper right) → `recents.list`
- **name contains suggestion — constrain search to file names containing the query** (upper left) → `recents.search-query`

**Variable position:**
- **matching file result — opens the selected user file; safety-blocked because opening may download or change recency metadata** (any matching file result; moves with results) — *mutates data* — *one of many*

## Document scanner

### Normal mode

The live document scanner shows the camera preview with close, flash, filter, automatic-shutter, and capture controls.

**Fixed:**
- **close button — cancel scanning and return to Recents** (upper left) → `recents.normal`
- **flash button — open flash mode choices** (lower center) → `document-scanner.flash-menu`
- **filters button — open document filter choices** (lower center) → `document-scanner.filter-menu`
- **automatic shutter toggle — switch between automatic edge-detection capture and manual capture** (lower center)
- **capture button — capture a document page; safety-blocked because it creates scan data** (lower center) — *mutates data*

### Flash menu mode

A Flash Mode popover overlays the scanner with Auto, On, and Off choices.

**Fixed:**
- **auto flash button — use automatic flash and close the popover** (lower center) → `document-scanner.normal`
- **flash on button — force the flash on and close the popover** (lower center) → `document-scanner.normal`
- **flash off button — disable flash and close the popover** (lower center) → `document-scanner.normal`
- **camera preview background — dismiss the flash popover** (middle right) → `document-scanner.normal`

### Filter menu mode

A Filter Mode popover overlays the scanner with Color, Grayscale, Black & White, and Photo choices.

**Fixed:**
- **color filter button — use the Color scan filter and close the popover** (center) → `document-scanner.normal`
- **grayscale filter button — use the Grayscale scan filter and close the popover** (lower center) → `document-scanner.normal`
- **black and white filter button — use the Black & White scan filter and close the popover** (lower center) → `document-scanner.normal`
- **photo filter button — use the Photo scan filter and close the popover** (lower center) → `document-scanner.normal`
- **camera preview background — dismiss the filter popover** (middle right) → `document-scanner.normal`

## Connect server

A Connect to Server sheet has a focused server-address field, a cancel button, and a disabled confirmation button until an address is entered.

**Fixed:**
- **close button — cancel server connection and return to Recents** (upper left) → `recents.normal`
- **server address field — focus the field for entering a hostname or network address** (upper center)
- **connect confirmation button — connect to the entered server; safety-blocked** (upper right) — *mutates data*

## Shared

### Normal mode

The Shared root is empty on this phone and shows search, More, an empty-state message, and the Recents, Shared, and Browse tab bar.

**Fixed:**
- **more button — open view, sort, scanning, and server options** (upper right) → `shared.more-menu`
- **search field — enter Shared search mode** (upper center) → `shared.search`
- **dictation button — begin voice input for Shared search; safety-blocked because it records audio** (upper right) — *mutates data*
- **recents tab — show recently used files** (lower left) → `recents.list`
- **shared tab — show shared files and collaboration activity** (lower center) → `shared.normal`
- **browse tab — show storage locations and favorites** (lower right) → `browse.normal`

### More menu mode

The Shared More popover offers disabled selection on the empty view, document scanning, server connection, icon or list layout, and sort choices.

**Fixed:**
- **select button — disabled because there are no shared files** (upper center)
- **scan documents button — open the document scanner** (upper right) → `document-scanner.normal`
- **connect to server button — open the server connection form** (upper right) → `connect-server.normal`
- **icons layout button — show shared files as an icon grid and close the menu** (upper center) → `shared.normal`
- **list layout button — show shared files as a list and close the menu** (upper center) → `shared.normal`
- **sort by name button — sort shared files by name and close the menu** (center) → `shared.normal`
- **sort by kind button — sort shared files by kind and close the menu** (center) → `shared.normal`
- **sort by date button — sort shared files by date and close the menu** (center) → `shared.normal`
- **sort by size button — sort shared files by size and close the menu** (center) → `shared.normal`
- **sort by tags button — sort shared files by tag and close the menu** (center) → `shared.normal`
- **background — dismiss the More popover** (middle left) → `shared.normal`

### Search mode

Shared search mode focuses an empty live search field, shows a layout toggle and cancel button, and raises the keyboard over the empty shared-files state.

**Fixed:**
- **search field — enter text to filter shared files live** (upper center)
- **dictation button — begin voice input for search; safety-blocked because it records audio** (upper center) — *mutates data*
- **layout toggle — switch Shared between list and icon layouts** (upper right) → `shared.search`
- **cancel search button — close the keyboard and return to Shared** (upper right) → `shared.normal`

## Icloud drive

### Normal mode

The iCloud Drive location shows a searchable icon grid of cloud-backed folders, a More menu, a back button, sync status, and the root tab bar.

**Fixed:**
- **back button — return to the presenting screen** (upper left)
- **more button — open selection, creation, scanning, server, view, and sort options** (upper right) → `icloud-drive.more-menu`
- **search field — enter iCloud Drive search mode** (upper center) → `icloud-drive.search`
- **dictation button — begin voice input for iCloud Drive search; safety-blocked because it records audio** (upper right) — *mutates data*
- **recents tab — show recently used files** (lower left) → `recents.list`
- **shared tab — show shared files and collaboration activity** (lower center) → `shared.normal`
- **browse tab — remain in the current Browse hierarchy** (lower right) → `icloud-drive.normal`

**Variable position:**
- **folder tile — open the folder** (any folder tile; moves with the grid) → `folder.normal` — *one of many*
- **cloud download button — downloads the folder contents to the device; safety-blocked** (cloud download icon beside an offloaded folder; moves with the grid) — *mutates data* — *one of many*

### More menu mode

The iCloud Drive More popover offers selection, New Folder, document scanning, server connection, icon or list layout, and sort choices.

**Fixed:**
- **select button — enter folder and file selection mode** (upper center) → `icloud-drive.select`
- **new folder button — create a folder in iCloud Drive; safety-blocked** (upper right) — *mutates data*
- **scan documents button — open the document scanner** (upper right) → `document-scanner.normal`
- **connect to server button — open the server connection form** (upper right) → `connect-server.normal`
- **icons layout button — show iCloud Drive as an icon grid and close the menu** (upper center) → `icloud-drive.normal`
- **list layout button — show iCloud Drive as a list and close the menu** (center) → `icloud-drive.list`
- **sort by name button — sort items by name and close the menu** (center) → `icloud-drive.normal`
- **sort by kind button — sort items by kind and close the menu** (center) → `icloud-drive.normal`
- **sort by date button — sort items by date and close the menu** (center) → `icloud-drive.normal`
- **sort by size button — sort items by size and close the menu** (center) → `icloud-drive.normal`
- **sort by tags button — sort items by tag and close the menu** (center) → `icloud-drive.normal`
- **background — dismiss the More popover** (middle left) → `icloud-drive.normal`

### Select mode

iCloud Drive selection mode shows selection circles on every folder, Select All and Done controls, and disabled file-operation buttons until an item is selected.

**Fixed:**
- **select all button — select every visible folder** (upper left) → `icloud-drive.selected`
- **done button — leave selection mode** (upper right) → `icloud-drive.normal`
- **share button — share selected items; disabled with no selection and safety-blocked** (lower left) — *mutates data*
- **duplicate button — duplicate selected items; disabled with no selection and safety-blocked** (lower left) — *mutates data*
- **move button — move selected items; disabled with no selection and safety-blocked** (lower center) — *mutates data*
- **delete button — delete selected items; disabled with no selection and safety-blocked** (lower center) — *mutates data*
- **more actions button — disabled until an item is selected** (lower right)

**Variable position:**
- **folder selection circle — select a folder without opening it** (selection circle on any folder tile; moves with the grid) → `icloud-drive.selected` — *one of many*

### Selected mode

iCloud Drive selection mode with one or more folders selected enables file operations; all data-changing actions remain safety-blocked.

**Fixed:**
- **select all button — select every visible folder** (upper left) → `icloud-drive.selected`
- **done button — clear the selection and leave selection mode** (upper right) → `icloud-drive.normal`
- **share button — share selected items; safety-blocked** (lower left) — *mutates data*
- **duplicate button — duplicate selected items; safety-blocked** (lower left) — *mutates data*
- **move button — move selected items; safety-blocked** (lower center) — *mutates data*
- **delete button — delete selected items; safety-blocked** (lower center) — *mutates data*
- **more actions button — open additional actions for selected items; safety-blocked** (lower right) — *mutates data*

**Variable position:**
- **folder selection circle — toggle that folder's selection** (selection circle on any folder tile; moves with the grid) → `icloud-drive.selected` — *one of many*

### List mode

iCloud Drive in list layout shows each folder as a dated row with a disclosure chevron and cloud status while retaining back, search, More, sync status, and the root tab bar.

**Fixed:**
- **back button — return to the presenting screen** (upper left)
- **more button — open selection, creation, scanning, server, view, and sort options** (upper right) → `icloud-drive.more-menu`
- **search field — enter iCloud Drive search mode** (upper center) → `icloud-drive.search`
- **dictation button — begin voice input for iCloud Drive search; safety-blocked because it records audio** (upper right) — *mutates data*
- **recents tab — show recently used files** (lower left) → `recents.list`
- **shared tab — show shared files and collaboration activity** (lower center) → `shared.normal`
- **browse tab — remain in the current Browse hierarchy** (lower right) → `icloud-drive.list`

**Variable position:**
- **folder row — open the folder** (any folder row or disclosure chevron; moves with the list) → `folder.normal` — *one of many*
- **cloud download button — downloads the folder contents to the device; safety-blocked** (cloud download icon beside an offloaded folder row; moves with the list) — *mutates data* — *one of many*

### Search mode

iCloud Drive search mode focuses a live search field above the current items, shows a layout toggle and cancel button, and raises the keyboard.

**Fixed:**
- **search field — enter text to filter iCloud Drive items live** (upper center)
- **dictation button — begin voice input for search; safety-blocked because it records audio** (upper center) — *mutates data*
- **layout toggle — switch search results between list and icon layouts** (upper right) → `icloud-drive.search`
- **cancel search button — close the keyboard and return to iCloud Drive** (upper right) → `icloud-drive.list`

**Variable position:**
- **matching folder result — open the folder** (any matching folder or file result; moves with results) → `folder.normal` — *one of many*
- **cloud download button — downloads the item to the device; safety-blocked** (cloud download icon beside an offloaded result; moves with results) — *mutates data* — *one of many*

## Folder

### Normal mode

An iCloud Drive folder shows its title and hierarchy menu, back, search, More, a list of contained files, sync status, and the root tab bar; Desktop is the observed example.

**Fixed:**
- **back button — return to the presenting screen** (upper left)
- **folder title menu button — open hierarchy and folder actions** (upper center) → `folder.title-menu`
- **more button — open folder selection, creation, scanning, server, view, and sort options** (upper right) → `folder.more-menu`
- **search field — enter search within the current folder** (upper center) → `folder.search`
- **dictation button — begin voice input for folder search; safety-blocked because it records audio** (upper right) — *mutates data*
- **recents tab — show recently used files** (lower left) → `recents.list`
- **shared tab — show shared files and collaboration activity** (lower center) → `shared.normal`
- **browse tab — remain in the current Browse hierarchy** (lower right) → `folder.normal`

**Variable position:**
- **file row — opens the selected user file; safety-blocked because opening may download or change recency metadata** (any file row; moves with the list) — *mutates data* — *one of many*
- **cloud download button — downloads the file to the device; safety-blocked** (cloud download icon beside an offloaded file; moves with the list) — *mutates data* — *one of many*

### Title menu mode

The folder-title popover shows the current folder, its iCloud Drive parent, download controls, rename, copy, move, and Get Info.

**Fixed:**
- **current folder summary — identifies the current folder and its size** (upper center)
- **iCloud Drive parent button — navigate to the iCloud Drive location** (upper center) → `icloud-drive.list`
- **download now button — download the folder contents to the device; safety-blocked** (upper center) — *mutates data*
- **keep downloaded button — pin the folder for local storage; safety-blocked** (upper center) — *mutates data*
- **rename button — rename the folder; safety-blocked** (center) — *mutates data*
- **copy button — copy the folder for later paste; safety-blocked** (center) — *mutates data*
- **move button — move the folder to another location; safety-blocked** (center) — *mutates data*
- **get info button — show folder metadata** (center) → `item-info.normal`
- **background — dismiss the folder-title popover** (middle right) → `folder.normal`

### More menu mode

The folder More popover offers selection, New Folder, document scanning, server connection, icon or list layout, and sort choices.

**Fixed:**
- **select button — enter file selection mode** (upper center) → `folder.select`
- **new folder button — create a folder here; safety-blocked** (upper right) — *mutates data*
- **scan documents button — open the document scanner** (upper right) → `document-scanner.normal`
- **connect to server button — open the server connection form** (upper right) → `connect-server.normal`
- **icons layout button — show folder contents as an icon grid and close the menu** (upper center) → `folder.icons`
- **list layout button — show folder contents as a list and close the menu** (center) → `folder.normal`
- **sort by name button — sort items by name and close the menu** (center) → `folder.normal`
- **sort by kind button — sort items by kind and close the menu** (center) → `folder.normal`
- **sort by date button — sort items by date and close the menu** (center) → `folder.normal`
- **sort by size button — sort items by size and close the menu** (center) → `folder.normal`
- **sort by tags button — sort items by tag and close the menu** (center) → `folder.normal`
- **background — dismiss the More popover** (middle left) → `folder.normal`

### Select mode

Folder selection mode shows selection circles on each file, Select All and Done, and disabled file-operation buttons until an item is selected.

**Fixed:**
- **select all button — select every visible file** (upper left) → `folder.selected`
- **done button — leave selection mode** (upper right) → `folder.normal`
- **share button — share selected files; disabled with no selection and safety-blocked** (lower left) — *mutates data*
- **duplicate button — duplicate selected files; disabled with no selection and safety-blocked** (lower left) — *mutates data*
- **move button — move selected files; disabled with no selection and safety-blocked** (lower center) — *mutates data*
- **delete button — delete selected files; disabled with no selection and safety-blocked** (lower center) — *mutates data*
- **more actions button — disabled until a file is selected** (lower right)

**Variable position:**
- **file selection circle — select a file without opening it** (selection circle on any file row; moves with the list) → `folder.selected` — *one of many*

### Selected mode

Folder selection mode with one or more files selected enables file operations; all data-changing actions remain safety-blocked.

**Fixed:**
- **select all button — select every visible file** (upper left) → `folder.selected`
- **done button — clear the selection and leave selection mode** (upper right) → `folder.normal`
- **share button — share selected files; safety-blocked** (lower left) — *mutates data*
- **duplicate button — duplicate selected files; safety-blocked** (lower left) — *mutates data*
- **move button — move selected files; safety-blocked** (lower center) — *mutates data*
- **delete button — delete selected files; safety-blocked** (lower center) — *mutates data*
- **more actions button — open additional actions for selected files; safety-blocked** (lower right) — *mutates data*

**Variable position:**
- **file selection circle — toggle that file's selection** (selection circle on any file row; moves with the list) → `folder.selected` — *one of many*

### Icons mode

The current folder in icon layout shows files as thumbnails while retaining title menu, back, search, More, sync status, and the root tab bar.

**Fixed:**
- **back button — return to the presenting screen** (upper left)
- **folder title menu button — open hierarchy and folder actions** (upper center) → `folder.title-menu`
- **more button — open folder selection, creation, scanning, server, view, and sort options** (upper right) → `folder.more-menu`
- **search field — enter search within the current folder** (upper center) → `folder.search`
- **dictation button — begin voice input for folder search; safety-blocked because it records audio** (upper right) — *mutates data*
- **recents tab — show recently used files** (lower left) → `recents.list`
- **shared tab — show shared files and collaboration activity** (lower center) → `shared.normal`
- **browse tab — remain in the current Browse hierarchy** (lower right) → `folder.icons`

**Variable position:**
- **file thumbnail — opens the selected user file; safety-blocked because opening may download or change recency metadata** (any file thumbnail; moves with the grid) — *mutates data* — *one of many*

### Search mode

Folder search mode focuses a live search field above current-folder results, shows a layout toggle and cancel button, and raises the keyboard.

**Fixed:**
- **search field — enter text to filter current-folder items live** (upper center)
- **dictation button — begin voice input for search; safety-blocked because it records audio** (upper center) — *mutates data*
- **layout toggle — switch folder search results between list and icon layouts** (upper right) → `folder.search`
- **cancel search button — close the keyboard and return to the folder** (upper right) → `folder.normal`

**Variable position:**
- **matching file result — opens the selected user file; safety-blocked because opening may download or change recency metadata** (any matching file result; moves with results) — *mutates data* — *one of many*
- **cloud download button — downloads the file to the device; safety-blocked** (cloud download icon beside an offloaded result; moves with results) — *mutates data* — *one of many*

## Item info

An Info sheet presents an item's preview, name, kind, size, creation and modification dates, containing location, and tags; Desktop folder metadata is the observed example.

**Fixed:**
- **close button — dismiss the Info sheet and return to the folder** (upper left) → `folder.normal`
- **containing location link — open the item's iCloud Drive location** (lower right) → `icloud-drive.list`
- **add tags button — assign tags to the item; safety-blocked** (lower right) — *mutates data*

## Browse

### Normal mode

The Browse root lists storage locations and colored tags beneath search and More, with collapsible Locations and Tags sections and the root tab bar.

**Fixed:**
- **more button — open editing and connection options for Browse** (upper right) → `browse.more-menu`
- **search field — enter Browse search mode** (upper center) → `browse.search`
- **dictation button — begin voice input for Browse search; safety-blocked because it records audio** (upper right) — *mutates data*
- **locations disclosure button — collapse or expand storage locations** (upper right) → `browse.locations-collapsed`
- **iCloud Drive row — open iCloud Drive** (center) → `icloud-drive.list`
- **On My iPhone row — open local device storage** (center) → `local-storage.normal`
- **Recently Deleted row — open recoverable deleted items** (center) → `recently-deleted.normal`
- **tags disclosure button — collapse or expand the tags list** (middle right) → `browse.tags-collapsed`
- **recents tab — show recently used files** (lower left) → `recents.list`
- **shared tab — show shared files and collaboration activity** (lower center) → `shared.normal`
- **browse tab — show storage locations and tags** (lower right) → `browse.normal`

**Variable position:**
- **tag row — show items assigned that tag** (any colored tag row; moves with the scrollable list) → `tag-results.normal` — *one of many*
- **Browse list — scroll to reveal additional tags and sections** (Browse list background; drag vertically) → `browse.scrolled`

### More menu mode

The Browse More popover offers document scanning, server connection, and editing of Browse locations and tags.

**Fixed:**
- **scan documents button — open the document scanner** (upper center) → `document-scanner.normal`
- **connect to server button — open the server connection form** (upper center) → `connect-server.normal`
- **edit button — edit Browse locations, order, and tags; safety-blocked** (upper center) — *mutates data*
- **background — dismiss the Browse More popover** (middle left) → `browse.normal`

### Locations collapsed mode

The Browse root with Locations collapsed shows the full tags list directly beneath the closed Locations header, while retaining search, More, and the root tab bar.

**Fixed:**
- **more button — open editing and connection options for Browse** (upper right) → `browse.more-menu`
- **search field — enter Browse search mode** (upper center) → `browse.search`
- **dictation button — begin voice input for Browse search; safety-blocked because it records audio** (upper right) — *mutates data*
- **locations disclosure button — expand storage locations** (upper right) → `browse.normal`
- **tags disclosure button — collapse the tags list** (middle right) → `browse.both-collapsed`
- **recents tab — show recently used files** (lower left) → `recents.list`
- **shared tab — show shared files and collaboration activity** (lower center) → `shared.normal`
- **browse tab — show storage locations and tags** (lower right) → `browse.locations-collapsed`

**Variable position:**
- **tag row — show items assigned that tag** (any colored tag row; moves with the scrollable list) → `tag-results.normal` — *one of many*
- **Browse list — scroll through the tags list** (Browse list background; drag vertically) → `browse.scrolled`

### Both collapsed mode

The Browse root with both Locations and Tags collapsed shows only the two closed section headers beneath search and More.

**Fixed:**
- **more button — open editing and connection options for Browse** (upper right) → `browse.more-menu`
- **search field — enter Browse search mode** (upper center) → `browse.search`
- **dictation button — begin voice input for Browse search; safety-blocked because it records audio** (upper right) — *mutates data*
- **locations disclosure button — expand storage locations** (upper right) → `browse.tags-collapsed`
- **tags disclosure button — expand the tags list** (middle right) → `browse.locations-collapsed`
- **recents tab — show recently used files** (lower left) → `recents.list`
- **shared tab — show shared files and collaboration activity** (lower center) → `shared.normal`
- **browse tab — show storage locations and tags** (lower right) → `browse.both-collapsed`

### Tags collapsed mode

The Browse root with Tags collapsed shows expanded iCloud Drive, On My iPhone, and Recently Deleted locations above the closed Tags header.

**Fixed:**
- **more button — open editing and connection options for Browse** (upper right) → `browse.more-menu`
- **search field — enter Browse search mode** (upper center) → `browse.search`
- **dictation button — begin voice input for Browse search; safety-blocked because it records audio** (upper right) — *mutates data*
- **locations disclosure button — collapse storage locations** (upper right) → `browse.both-collapsed`
- **iCloud Drive row — open iCloud Drive** (center) → `icloud-drive.list`
- **On My iPhone row — open local device storage** (center) → `local-storage.normal`
- **Recently Deleted row — open recoverable deleted items** (center) → `recently-deleted.normal`
- **tags disclosure button — expand the tags list** (middle right) → `browse.normal`
- **recents tab — show recently used files** (lower left) → `recents.list`
- **shared tab — show shared files and collaboration activity** (lower center) → `shared.normal`
- **browse tab — show storage locations and tags** (lower right) → `browse.tags-collapsed`

### Search mode

Browse search mode focuses a live search field, shows a layout toggle and cancel button, and raises the keyboard over storage and tag results.

**Fixed:**
- **search field — enter text to filter files across Browse locations** (upper center)
- **dictation button — begin voice input for search; safety-blocked because it records audio** (upper center) — *mutates data*
- **layout toggle — switch Browse search results between list and icon layouts** (upper right) → `browse.search`
- **cancel search button — close the keyboard and return to Browse** (upper right) → `browse.normal`

**Variable position:**
- **matching file result — opens the selected user item; safety-blocked because opening may download or change recency metadata** (any matching folder or file result; moves with results) — *mutates data* — *one of many*

### Scrolled mode

The Browse list scrolled down reveals later custom tags while section headers and earlier rows move upward; the root tab bar remains fixed.

**Fixed:**
- **recents tab — show recently used files** (lower left) → `recents.list`
- **shared tab — show shared files and collaboration activity** (lower center) → `shared.normal`
- **browse tab — show storage locations and tags** (lower right) → `browse.scrolled`

**Variable position:**
- **tag row — show items assigned that tag** (any colored tag row; moves with the scrollable list) → `tag-results.normal` — *one of many*
- **Browse list — scroll back toward storage locations and earlier tags** (Browse list background; drag vertically) → `browse.normal`

## Local storage

### Normal mode

The empty On My iPhone location shows back, search, More, an empty-state message, and the root tab bar.

**Fixed:**
- **back button — return to the presenting screen** (upper left)
- **more button — open creation, scanning, server, view, and sort options** (upper right) → `local-storage.more-menu`
- **search field — enter search within local storage** (upper center) → `local-storage.search`
- **dictation button — begin voice input for local search; safety-blocked because it records audio** (upper right) — *mutates data*
- **recents tab — show recently used files** (lower left) → `recents.list`
- **shared tab — show shared files and collaboration activity** (lower center) → `shared.normal`
- **browse tab — remain in local storage** (lower right) → `local-storage.normal`

### More menu mode

The empty local-storage More popover offers disabled selection, New Folder, document scanning, server connection, icon or list layout, and sort choices.

**Fixed:**
- **select button — disabled because local storage is empty** (upper center)
- **new folder button — create a folder in local storage; safety-blocked** (upper right) — *mutates data*
- **scan documents button — open the document scanner** (upper right) → `document-scanner.normal`
- **connect to server button — open the server connection form** (upper right) → `connect-server.normal`
- **icons layout button — use icon layout and close the menu** (upper center) → `local-storage.normal`
- **list layout button — use list layout and close the menu** (center) → `local-storage.normal`
- **sort by name button — sort local items by name and close the menu** (center) → `local-storage.normal`
- **sort by kind button — sort local items by kind and close the menu** (center) → `local-storage.normal`
- **sort by date button — sort local items by date and close the menu** (center) → `local-storage.normal`
- **sort by size button — sort local items by size and close the menu** (center) → `local-storage.normal`
- **sort by tags button — sort local items by tag and close the menu** (center) → `local-storage.normal`
- **background — dismiss the local-storage More popover** (middle left) → `local-storage.normal`

### Search mode

Local-storage search mode focuses an empty live search field, shows a layout toggle and cancel button, and raises the keyboard over the empty state.

**Fixed:**
- **search field — enter text to filter local items live** (upper center)
- **dictation button — begin voice input for search; safety-blocked because it records audio** (upper center) — *mutates data*
- **layout toggle — switch local storage between list and icon layouts** (upper right) → `local-storage.search`
- **cancel search button — close the keyboard and return to local storage** (upper right) → `local-storage.normal`

## Recently deleted

### Normal mode

The empty Recently Deleted location shows back, search, More, a retention warning, and the root tab bar.

**Fixed:**
- **back button — return to the presenting screen** (upper left)
- **more button — open disabled selection, scanning, server, view, and sort options** (upper right) → `recently-deleted.more-menu`
- **search field — enter search within Recently Deleted** (upper center) → `recently-deleted.search`
- **dictation button — begin voice input for deleted-items search; safety-blocked because it records audio** (upper right) — *mutates data*
- **recents tab — show recently used files** (lower left) → `recents.list`
- **shared tab — show shared files and collaboration activity** (lower center) → `shared.normal`
- **browse tab — remain in Recently Deleted** (lower right) → `recently-deleted.normal`

### More menu mode

The empty Recently Deleted More popover offers disabled selection, document scanning, server connection, icon or list layout, and sort choices.

**Fixed:**
- **select button — disabled because Recently Deleted is empty** (upper center)
- **scan documents button — open the document scanner** (upper right) → `document-scanner.normal`
- **connect to server button — open the server connection form** (upper right) → `connect-server.normal`
- **icons layout button — use icon layout and close the menu** (upper center) → `recently-deleted.normal`
- **list layout button — use list layout and close the menu** (upper center) → `recently-deleted.normal`
- **sort by name button — sort deleted items by name and close the menu** (center) → `recently-deleted.normal`
- **sort by kind button — sort deleted items by kind and close the menu** (center) → `recently-deleted.normal`
- **sort by date button — sort deleted items by date and close the menu** (center) → `recently-deleted.normal`
- **sort by size button — sort deleted items by size and close the menu** (center) → `recently-deleted.normal`
- **sort by tags button — sort deleted items by tag and close the menu** (center) → `recently-deleted.normal`
- **background — dismiss the Recently Deleted More popover** (middle left) → `recently-deleted.normal`

### Search mode

Recently Deleted search mode focuses an empty live search field, shows a layout toggle and cancel button, and raises the keyboard over the empty state.

**Fixed:**
- **search field — enter text to filter deleted items live** (upper center)
- **dictation button — begin voice input for search; safety-blocked because it records audio** (upper center) — *mutates data*
- **layout toggle — switch deleted-items search between list and icon layouts** (upper right) → `recently-deleted.search`
- **cancel search button — close the keyboard and return to Recently Deleted** (upper right) → `recently-deleted.normal`

## Tag results

### Normal mode

A colored-tag results screen shows back, search, More, an empty state when no files carry that tag, and the root tab bar; Red is the observed tag.

**Fixed:**
- **back button — return to the presenting screen** (upper left)
- **more button — open disabled selection, scanning, server, view, and sort options** (upper right) → `tag-results.more-menu`
- **search field — enter search within tagged items** (upper center) → `tag-results.search`
- **dictation button — begin voice input for tagged-items search; safety-blocked because it records audio** (upper right) — *mutates data*
- **recents tab — show recently used files** (lower left) → `recents.list`
- **shared tab — show shared files and collaboration activity** (lower center) → `shared.normal`
- **browse tab — remain in tag results** (lower right) → `tag-results.normal`

### More menu mode

The empty tag-results More popover offers disabled selection, document scanning, server connection, icon or list layout, and sort choices.

**Fixed:**
- **select button — disabled because the tag has no files** (upper center)
- **scan documents button — open the document scanner** (upper right) → `document-scanner.normal`
- **connect to server button — open the server connection form** (upper right) → `connect-server.normal`
- **icons layout button — use icon layout and close the menu** (upper center) → `tag-results.normal`
- **list layout button — use list layout and close the menu** (upper center) → `tag-results.normal`
- **sort by name button — sort tagged items by name and close the menu** (center) → `tag-results.normal`
- **sort by kind button — sort tagged items by kind and close the menu** (center) → `tag-results.normal`
- **sort by date button — sort tagged items by date and close the menu** (center) → `tag-results.normal`
- **sort by size button — sort tagged items by size and close the menu** (center) → `tag-results.normal`
- **sort by tags button — sort tagged items by tag and close the menu** (center) → `tag-results.normal`
- **background — dismiss the tag-results More popover** (middle left) → `tag-results.normal`

### Search mode

Tag-results search mode focuses an empty live search field, shows a layout toggle and cancel button, and raises the keyboard over the empty state.

**Fixed:**
- **search field — enter text to filter tagged items live** (upper center)
- **dictation button — begin voice input for search; safety-blocked because it records audio** (upper center) — *mutates data*
- **layout toggle — switch tag-results search between list and icon layouts** (upper right) → `tag-results.search`
- **cancel search button — close the keyboard and return to tag results** (upper right) → `tag-results.normal`
