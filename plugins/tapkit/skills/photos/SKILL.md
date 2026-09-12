---
name: photos
description: Layout and navigation of the Photos iPhone app — its screens, modes, and where every control is located. Use when operating Photos and you cannot find a control or a screen.
---

# Photos app UI map

Positions describe equal thirds of the screen in a 3×3 grid: upper left, upper center, upper right; middle left, center, middle right; lower left, lower center, lower right. Elements under **Fixed** — bars, popups, sheets — sit in the listed region whenever the mode is shown. Locate the described control visually within that region before tapping. Elements under **Variable position** move with scrolling content; scroll to reveal them.

## Library

### Normal mode

The main photo library, showing the newest items in a three-column grid with Library, Collections, and Search navigation.

**Fixed:**
- **sort and filter menu button — open the library sort, filter, and view options menu** (upper center) → `library.sort-menu`
- **Select button — enter multi-item selection mode** (upper right) → `library.select`
- **Library button — open the Library screen** (lower left)
- **Collections button — open the Collections dashboard** (lower center) → `collections.normal`
- **Search button — open Photos search** (lower right)

**Variable position:**
- **photo thumbnail — open the item viewer** (any photo thumbnail in the scrollable grid) → `photo.normal` — *one of many*
- **content area — scroll vertically** (photo grid; drag vertically)

### Select mode

The library in multi-item selection mode, with selection controls above the grid and Share and Delete actions below.

**Fixed:**
- **sort and filter menu button — open view controls while selecting items** (upper center) → `library.select-sort-menu`
- **more button — inactive with no selection, or open selected-item actions when items are selected** (upper right) → `library.select-more-menu`
- **close button — leave selection mode** (upper right) → `library.normal`
- **share button — open sharing options** (lower left)
- **delete button — delete selected items after confirmation** (lower right) — *mutates data*

**Variable position:**
- **photo selection toggle — select or deselect an item without modifying it** (any photo thumbnail in the selection grid) — *one of many*
- **content area — scroll vertically** (selection grid; drag vertically)

### Select more menu mode

The selected-item actions menu, offering slideshow, copy, and several data-changing photo operations.

**Fixed:**
- **slideshow button — start a slideshow of the selected items** (upper left) → `slideshow.music-permission`
- **favorite button — mark the selected items as favorites** (upper center) — *mutates data*
- **delete button — delete the selected items after confirmation** (upper right) — *mutates data*
- **copy command — copy selected items** (upper center)
- **duplicate command — create copies of the selected items** (upper center) — *mutates data*
- **hide command — move the selected items into the Hidden collection** (upper center) — *mutates data*
- **add to album command — add the selected items to an album** (center) — *mutates data*
- **adjust date and time command — change capture metadata for the selected items** (center) — *mutates data*
- **adjust location command — change location metadata for the selected items** (center) — *mutates data*
- **highlighted more button — close the selected-item actions menu** (upper right) → `library.select`
- **close button — leave selection mode** (upper right)
- **share button — open sharing options** (lower left)
- **delete button — delete selected items after confirmation** (lower right) — *mutates data*

**Variable position:**
- **thumbnail — open or choose that item** (any visible photo thumbnail outside the actions popover while selecting) — *one of many*

### Select sort menu mode

Selection mode with the sort, filter, and view-options popover open.

**Fixed:**
- **sort by recently added option — order items by addition time and close the menu** (upper center) → `library.select`
- **sort by date captured option — order items by capture date and close the menu** (upper center) → `library.select`
- **filter submenu — expand item filters while in selection mode** (upper center) → `library.select-filter-menu`
- **view options submenu — expand grid and visibility controls while selecting** (upper center) → `library.select-view-options`
- **highlighted sort menu button — close the popover and return to selection mode** (upper center) → `library.select`
- **close button — leave selection mode** (upper right)
- **share button — open sharing options** (lower left)
- **delete button — delete selected items after confirmation** (lower right) — *mutates data*

**Variable position:**
- **thumbnail — open or choose that item** (any visible photo thumbnail outside the popover while selecting) — *one of many*

### Select view options mode

Expanded View Options during selection mode, offering grid zoom and visibility toggles.

**Fixed:**
- **view options header — collapse the submenu back to selection-mode sort controls** (upper center) → `library.select-sort-menu`
- **zoom in button — enlarge thumbnails and reduce the grid to fewer columns** (center)
- **zoom out button — shrink thumbnails and increase the grid column count** (center)
- **screenshots visibility toggle — show or hide screenshots in the selection grid** (center)
- **shared with you visibility toggle — show or hide items shared through Messages** (center)
- **close button — leave selection mode** (upper right)
- **share button — open sharing options** (lower left)
- **delete button — delete selected items after confirmation** (lower right) — *mutates data*

**Variable position:**
- **thumbnail — open or choose that item** (any visible photo thumbnail outside the view-options popover while selecting) — *one of many*

### Select filter menu mode

The expanded item-filter submenu while the library remains in selection mode.

**Fixed:**
- **all items filter — clear active filters** (upper center)
- **favorites filter — toggle inclusion of favorited items** (center)
- **edited filter — toggle inclusion of edited items** (center)
- **photos filter — toggle inclusion of still photos** (center)
- **videos filter — toggle inclusion of videos** (center)
- **screenshots filter — toggle inclusion of screenshots** (center)
- **shared with you filter — toggle inclusion of items shared through Messages** (center)
- **not in an album filter — toggle inclusion of items outside albums** (center)
- **filter header — collapse the submenu back to selection-mode sort controls** (upper center) → `library.select-sort-menu`
- **close button — leave selection mode** (upper right)
- **share button — open sharing options** (lower left)
- **delete button — delete selected items after confirmation** (lower right) — *mutates data*

**Variable position:**
- **thumbnail — open or choose that item** (any visible photo thumbnail outside the filter popover while selecting) — *one of many*

### Sort menu mode

The library with a popover offering sort order, filtering, and view options.

**Fixed:**
- **sort by recently added option — order the library by when items were added and close the menu** (upper center)
- **sort by date captured option — order the library by capture date and close the menu** (upper center)
- **filter submenu — expand the library item filters** (upper center) → `library.filter-menu`
- **view options submenu — expand grid zoom, aspect ratio, and visibility options** (upper center) → `library.view-options`
- **highlighted sort menu button — close the popover** (upper center) → `library.normal`
- **Select button — enter selection mode** (upper right)
- **Library button — open the Library screen** (lower left)
- **Collections button — open the Collections screen** (lower center)
- **Search button — open Photos search** (lower right)

**Variable position:**
- **thumbnail — open or choose that item** (any visible photo thumbnail outside the popover) — *one of many*

### View options mode

The expanded View Options submenu over the library, with grid sizing, aspect-ratio, and visibility controls; option rows shift downward when a hidden-items status subtitle is present.

**Fixed:**
- **view options header — collapse the submenu back to the sort menu** (upper center) → `library.sort-menu`
- **Select button — enter selection mode** (upper right)
- **Library button — open the Library screen** (lower left)
- **Collections button — open the Collections screen** (lower center)
- **Search button — open Photos search** (lower right)

**Variable position:**
- **zoom in button — enlarge thumbnails and reduce the grid to fewer columns** (Zoom In row in the View Options popover; shifts when a status subtitle appears)
- **zoom out button — shrink thumbnails and increase the grid column count** (Zoom Out row in the View Options popover; shifts when a status subtitle appears)
- **aspect ratio grid toggle — switch between aspect-ratio thumbnails and a square photo grid** (aspect-ratio row in the View Options popover; shifts when a status subtitle appears)
- **screenshots visibility toggle — show or hide screenshots in the library grid** (Screenshots row in the View Options popover; shifts when a status subtitle appears)
- **shared with you visibility toggle — show or hide items shared through Messages** (Shared with You row in the View Options popover; shifts when a status subtitle appears)
- **thumbnail — open or choose that item** (any visible photo thumbnail outside the view-options popover) — *one of many*

### Filter menu mode

The expanded Filter submenu over the library, offering item-type and metadata filters.

**Fixed:**
- **all items filter — show every library item** (upper center)
- **favorites filter — show only favorited items and close the menu** (center) → `library.filtered-empty`
- **edited filter — toggle inclusion of edited items** (center)
- **photos filter — toggle inclusion of still photos** (center)
- **videos filter — toggle inclusion of videos** (center)
- **screenshots filter — toggle inclusion of screenshots** (center)
- **shared with you filter — toggle shared items** (center)
- **not in an album filter — toggle items outside albums** (center)
- **filter header — collapse the expanded filter submenu** (upper center)
- **Select button — enter selection mode** (upper right)
- **Library button — open the Library screen** (lower left)
- **Collections button — open the Collections screen** (lower center)
- **Search button — open Photos search** (lower right)

**Variable position:**
- **thumbnail — open or choose that item** (any visible photo thumbnail outside the filter popover) — *one of many*

### Filtered empty mode

The library with an active filter that matches no items; the filter glyph replaces the usual sort and Select controls.

**Fixed:**
- **active filter button — open the filtered-library menu** (upper right) → `library.sort-menu-filtered`
- **Library button — open the Library screen** (lower left)
- **Collections button — open the Collections screen** (lower center)
- **Search button — open Photos search** (lower right)

### Sort menu filtered mode

The filtered library menu, showing the current filter and an additional Remove Filter command.

**Fixed:**
- **sort by recently added option — order by addition time** (upper center)
- **sort by date captured option — order by capture date** (upper center)
- **filter submenu — expand filters while a filter is active** (upper center) → `library.filter-menu-filtered`
- **remove filter command — clear the active filter** (upper center)
- **view options submenu — open grid view controls** (center)
- **highlighted menu button — close the open popover** (upper right)
- **Library button — open the Library screen** (lower left)
- **Collections button — open the Collections screen** (lower center)
- **Search button — open Photos search** (lower right)

### Filter menu filtered mode

The expanded filter submenu while a filter is active, with the current filter checked.

**Fixed:**
- **all items filter — clear active filters and return to the unfiltered library** (upper center) → `library.normal`
- **favorites filter — toggle inclusion of favorites** (center)
- **edited filter — toggle inclusion of edited items** (center)
- **photos filter — toggle inclusion of still photos** (center)
- **videos filter — toggle inclusion of videos** (center)
- **screenshots filter — toggle inclusion of screenshots** (center)
- **shared with you filter — toggle inclusion of items shared through Messages** (center)
- **not in an album filter — toggle inclusion of items outside albums** (center)
- **filter header — collapse the expanded filter submenu** (upper center)
- **Library button — open the Library screen** (lower left)
- **Collections button — open the Collections screen** (lower center)
- **Search button — open Photos search** (lower right)

## Slideshow

### Music permission mode

A system permission alert over the slideshow asking whether Photos may access Apple Music for Memories songs.

**Fixed:**
- **Don’t Allow button — continue the slideshow without Apple Music access** (middle left) → `slideshow.normal`
- **Allow button — grant Photos access to Apple Music activity and the media library** (middle right) — *mutates data*

### Normal mode

A full-screen slideshow frame with playback, favorite, and sharing controls over the image.

**Fixed:**
- **back button — leave the slideshow** (upper left)
- **replay button — restart slideshow playback and hide the controls** (lower center) → `slideshow.playing`
- **favorite button — mark the displayed item as a favorite** (lower center) — *mutates data*
- **share button — open sharing options** (lower center)

**Variable position:**
- **photo surface — hide or show the viewer controls** (slideshow image surface; tap to show or hide playback chrome)

### Playing mode

The slideshow actively advances full-screen images with all controls hidden.

**Variable position:**
- **slideshow image — reveal playback controls** (full-screen slideshow image; tap to reveal controls) → `slideshow.controls`
- **left-edge back gesture — no effect while slideshow playback chrome is hidden** (left-edge back gesture on the full-screen slideshow)

### Controls mode

Slideshow playback controls over the current image, with audio, pause, filmstrip, music, and grid navigation.

**Fixed:**
- **back button — leave the slideshow** (upper left)
- **audio button — mute or unmute slideshow sound** (upper right)
- **more button — show slideshow options** (upper right)
- **play/pause button — toggle slideshow playback and hide the controls** (center) → `slideshow.playing`
- **share button — open sharing options** (lower left)
- **grid button — show all slideshow items** (lower right)

**Variable position:**
- **photo area — dismiss the open actions menu** (slideshow image outside the controls; tap to hide chrome)
- **thumbnail — open or choose that item** (any thumbnail in the slideshow filmstrip) — *one of many*

## Photo

### Normal mode

The single-item viewer with date, navigation filmstrip, sharing, favorite, info, editing, and deletion controls.

**Fixed:**
- **back button — return to the presenting photo grid** (upper left)
- **more button — open item actions** (upper right) → `photo.more-menu`
- **immersive-view button — hide the standard toolbar and show a close control** (upper right) → `photo.immersive`
- **share button — open sharing options** (lower left)
- **favorite button — mark the item as a favorite** (lower center) — *mutates data*
- **info button — open photo metadata and caption details** (lower center) → `photo.info`
- **edit button — open the nondestructive photo editor** (lower center) → `photo.editor`
- **delete button — delete the displayed item after confirmation** (lower right) — *mutates data*

**Variable position:**
- **photo surface — hide or show the viewer controls** (displayed photo surface; tap to hide or show chrome)
- **photo surface — move between adjacent items** (displayed photo surface; swipe horizontally to move between adjacent items)
- **thumbnail — open or choose that item** (any thumbnail in the bottom filmstrip) — *one of many*

### Editor mode

The nondestructive photo editor on the Adjust tab, with temporary adjustment controls and Cancel or Done.

**Fixed:**
- **Cancel button — discard temporary edits and return to the item viewer** (upper left) → `photo.normal`
- **Done button — save the current photo edits** (upper right) — *mutates data*
- **undo button — undo the latest temporary edit when enabled** (upper left)
- **redo button — redo an undone temporary edit when enabled** (upper left)
- **markup button — open drawing and annotation tools before saving** (upper right)
- **more button — open editor actions** (upper right)
- **auto-enhance button — toggle a temporary automatic adjustment** (lower center)
- **Adjust tab — show light and color adjustment controls** (lower center)
- **Filters tab — show preset filters** (lower center)
- **Crop tab — show crop, straighten, rotate, and perspective controls** (lower center)

**Variable position:**
- **adjustment type — choose the property controlled by the slider** (any circular adjustment-type button in the horizontal adjustment strip) — *one of many*
- **adjustment slider — change the selected temporary adjustment** (horizontal adjustment slider below the photo)

### Info mode

The item information panel showing caption, capture metadata, location, and source attribution above the bottom toolbar.

**Fixed:**
- **Adjust button — change the item’s capture date and time** (middle right) — *mutates data*
- **Add a location button — attach location metadata to the item** (lower center) — *mutates data*
- **source attribution row — open the app or page the item was saved from** (lower center)
- **share button — open sharing options** (lower left)
- **favorite button — mark the item as a favorite** (lower center) — *mutates data*
- **highlighted info button — close the metadata panel** (lower center) → `photo.normal`
- **edit button — open the item editor** (lower center)
- **delete button — delete the displayed item after confirmation** (lower right) — *mutates data*

**Variable position:**
- **caption field — add or change the item caption** (Add a Caption field below the photo) — *mutates data*

### Immersive mode

An immersive item view with only a Close button and the bottom filmstrip visible around the photo.

**Fixed:**
- **close button — return to the standard item viewer** (upper right) → `photo.normal`

**Variable position:**
- **photo surface — hide or show the viewer controls** (displayed photo surface in immersive view)
- **thumbnail — open or choose that item** (any thumbnail in the bottom filmstrip) — *one of many*

### More menu mode

The displayed-item actions menu with copy and slideshow plus data-changing duplicate, hide, album, metadata, and delete operations.

**Fixed:**
- **copy command — copy the displayed item to the system clipboard and close the menu** (upper center) → `photo.normal`
- **duplicate command — create a copy of the displayed item** (upper center) — *mutates data*
- **hide command — move the displayed item into the Hidden collection** (upper center) — *mutates data*
- **slideshow command — play a slideshow beginning with the displayed item** (upper center) → `slideshow.normal`
- **add to album command — add the displayed item to an album** (upper center) — *mutates data*
- **adjust date and time command — change the item’s capture date metadata** (center) — *mutates data*
- **adjust location command — change the item’s location metadata** (center) — *mutates data*
- **delete command — delete the displayed item after confirmation** (center) — *mutates data*
- **back button — return to the presenting collection** (upper left)
- **more button — close the item actions menu** (upper right)
- **share button — open sharing options** (lower left)
- **favorite button — mark the item as a favorite** (lower center) — *mutates data*
- **info button — show item metadata** (lower center)
- **edit button — open the item editor** (lower center)
- **delete button — delete the displayed item after confirmation** (lower right) — *mutates data*

**Variable position:**
- **photo area — dismiss the open actions menu** (displayed photo outside the actions popover)
- **thumbnail — open or choose that item** (any thumbnail in the bottom filmstrip) — *one of many*

## Collections

### Normal mode

A vertically scrollable dashboard of Memories, Pinned, Albums, People & Pets, and additional collection sections.

**Fixed:**
- **more button — open Collections options** (upper right)
- **profile button — open account and Photos settings** (upper right)
- **Library button — open the Library screen** (lower left)
- **Collections button — open the Collections screen** (lower center)
- **Search button — open Photos search with the query field focused** (lower right) → `search.normal`

**Variable position:**
- **Memories section title — open the Memories collection** (Memories section title; moves as the dashboard scrolls) → `collection.normal`
- **section chevron — collapse or expand that Collections section** (blue collapse chevron beside any collection section; moves as the dashboard scrolls) — *one of many*
- **Pinned section title — open all pinned collections** (Pinned section title; moves as the dashboard scrolls) → `pinned.normal`
- **Pinned Edit button — choose and reorder pinned collections** (Pinned Edit button; moves as the dashboard scrolls) — *mutates data*
- **card — open that collection** (any card in the horizontally scrolling Pinned row) → `collection.normal` — *one of many*
- **Albums section title — open all albums** (Albums section title; moves as the dashboard scrolls) → `collection.normal`
- **card — open that collection** (any personal album card in the Albums row) → `collection.normal` — *one of many*
- **People & Pets section title — open recognized people and pets** (People & Pets section title; moves as the dashboard scrolls) → `collection.normal`
- **Collections dashboard — scroll vertically through all collection sections** (Collections dashboard; drag vertically to reveal more sections)
- **Featured Photos section title — open Featured Photos** (Featured Photos section title; moves as the dashboard scrolls) → `collection.normal`
- **card — open that collection** (any card in the Featured Photos row) → `collection.normal` — *one of many*
- **Shared Albums section title — open Shared Albums** (Shared Albums section title; moves as the dashboard scrolls) → `collection.normal`
- **Start Sharing button — begin configuring shared albums** (Start Sharing button in the Shared Albums section) — *mutates data*
- **Recent Days section title — open recent day collections** (Recent Days section title; moves as the dashboard scrolls) → `collection.normal`
- **card — open that collection** (any card in the Recent Days row) → `collection.normal` — *one of many*
- **Trips section title — open trip collections** (Trips section title; moves as the dashboard scrolls) → `collection.normal`
- **Media Types section title — open media-type collections** (Media Types section title; moves as the dashboard scrolls) → `collection.normal`
- **row — open that collection** (any media-type row under Media Types) → `collection.normal` — *one of many*
- **Utilities section title — open all utility collections** (Utilities section title; moves as the dashboard scrolls) → `collection.normal`
- **Hidden utility — open the locked Hidden collection after device authentication** (Hidden utility row)
- **Recently Deleted utility — open the locked recently deleted collection after device authentication** (Recently Deleted utility row)
- **row — open that collection** (any unlocked utility row such as Recently Viewed, Imports, Recently Saved, or Map) → `collection.normal` — *one of many*
- **collection long press — open the Pin context menu** (any collection card or utility row; long press) → `collections.pin-menu` — *one of many*
- **Wallpaper Suggestions section title — open wallpaper suggestions** (Wallpaper Suggestions section title near the bottom of Collections) → `collection.normal`
- **Reorder button — enter Collections section reordering mode** (Reorder button below the final Collections section) → `collections.reorder`

### Reorder mode

A list of every Collections section with drag handles for changing their order.

**Fixed:**
- **Done button — save the section order and leave reorder mode** (upper right) — *mutates data*
- **Library button — open the Library screen** (lower left)
- **Collections button — open the Collections screen** (lower center)
- **Search button — open Photos search** (lower right)

**Variable position:**
- **section drag handle — reorder a Collections section** (drag handle at the right edge of any Collections section row) — *mutates data* — *one of many*

### Pin menu mode

A compact context menu over Collections offering to pin the pressed collection.

**Fixed:**
- **more button — open Collections options** (upper right)
- **profile button — open account and Photos settings** (upper right)
- **Library button — open the Library screen** (lower left)
- **Collections button — open the Collections screen** (lower center)
- **Search button — open Photos search** (lower right)

**Variable position:**
- **Pin command — add the pressed collection to Pinned** (Pin command in the context menu near the pressed collection) — *mutates data*
- **outside area — dismiss the Pin context menu** (area outside the Pin context menu) → `collections.normal`

## Search

### Normal mode

Photos search with a focused library query field, recent searches, and the software keyboard visible.

**Fixed:**
- **information button — explain why some search results may not appear** (upper center) → `search.info-popover`
- **dictation button — enter a query by voice** (middle right)
- **close search button — leave search** (middle right)

**Variable position:**
- **card — open that collection** (any card in the Recents section) — *one of many*
- **search field — type a query and show live photo and collection results** (Search your library field above the keyboard) → `search.results`

### Results menu mode

Search results with a popover for result sort order and view options.

**Fixed:**
- **sort by recently added option — order matching items by addition time** (upper center)
- **sort by date captured option — order matching items by capture date** (upper center)
- **view options submenu — open search result grid view controls** (upper center)
- **highlighted sort and view menu button — close the popover** (upper center) → `search.results`
- **Select button — enter result selection mode when results exist** (upper right)
- **Photos scope — show matching photos** (upper left)
- **Collections scope — show collection matches and dismiss the keyboard** (upper right) → `search.results-collections`
- **dictation button — enter a query by voice** (middle right)
- **close search button — leave search** (middle right)

**Variable position:**
- **query field — edit the current search query** (query field above the keyboard)

### Results collections mode

Collection-scoped search results with the keyboard dismissed and a compact bottom query bar.

**Fixed:**
- **Photos scope — show matching photos** (upper left)
- **Collections scope — show matching collections** (upper right)
- **share button — open sharing options** (lower left)
- **clear query button — erase the query and return to empty search** (lower right) → `search.normal`
- **close search button — return to Collections** (lower right)

**Variable position:**
- **query field — edit the current search query** (compact query field in the bottom bar)

### Results mode

Live search results for the entered query, with Photos and Collections scopes and a result grid above the focused query field.

**Fixed:**
- **sort and view menu button — open search result sorting and view options** (upper center) → `search.results-menu`
- **Select button — enter result selection mode when results exist** (upper right)
- **Photos scope — show matching photos** (upper left)
- **Collections scope — show matching collections** (upper right)
- **dictation button — enter a query by voice** (middle right)
- **close search button — leave search** (middle right)

**Variable position:**
- **thumbnail — open or choose that item** (any photo thumbnail in the search result grid) — *one of many*
- **query field — edit the current search query** (query field above the keyboard)

### Info popover mode

Search with a popover explaining that indexing occurs while the iPhone is locked, charging, and connected to Wi-Fi.

**Fixed:**
- **information button — close the indexing explanation** (upper center)
- **dictation button — enter a query by voice** (middle right)
- **close search button — leave search** (middle right)

**Variable position:**
- **outside area — dismiss the indexing explanation** (area outside the search indexing explanation popover) → `search.normal`
- **card — open that collection** (any card in the Recents section) — *one of many*
- **search field — enter a Photos query** (Search your library field above the keyboard)

## Pinned

A vertically scrollable two-column grid of pinned collections such as Favorites, Recently Saved, Map, Videos, and Screenshots.

**Fixed:**
- **back button — return to the presenting Collections screen** (upper left)
- **Edit button — choose and reorder pinned collections** (upper right) — *mutates data*
- **Library button — open the Library screen** (lower left)
- **Collections button — open the Collections screen** (lower center)
- **Search button — open Photos search** (lower right)

**Variable position:**
- **pinned collection card — open that collection** (any unlocked pinned collection card) → `collection.normal` — *one of many*
- **Recently Deleted card — open the locked recently deleted collection after device authentication** (Recently Deleted pinned card)
- **content area — scroll vertically** (Pinned grid; drag vertically when more cards exist)

## Collection

A named photo collection, empty here for Favorites, with Back and More controls and a photo grid when items exist.

**Fixed:**
- **back button — return to the presenting Collections screen** (upper left)
- **more button — inactive when the collection is empty** (upper right)

**Variable position:**
- **thumbnail — open or choose that item** (any photo thumbnail in the collection grid) — *one of many*
- **content area — scroll vertically** (collection grid; drag vertically when content exceeds the screen)
