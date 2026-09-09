---
name: safari
description: Layout and navigation of the Safari iPhone app — its screens, modes, and where every control is located. Use when operating Safari and you cannot find a control or a screen.
---

# Safari app UI map

Positions describe equal thirds of the screen in a 3×3 grid: upper left, upper center, upper right; middle left, center, middle right; lower left, lower center, lower right. Elements under **Fixed** — bars, popups, sheets — sit in the listed region whenever the mode is shown. Locate the described control visually within that region before tapping. Elements under **Variable position** move with scrolling content; scroll to reveal them.

## Start page

### Normal mode

Safari's customizable start page, showing navigation categories, Favorites, a Privacy Report card, and the bottom address and tab controls.

**Fixed:**
- **start page button — keep the start page selected** (upper left)
- **bookmarks button — show bookmarks** (upper center) → `start-page.bookmarks`
- **reading list button — show Reading List** (upper center) → `start-page.reading-list`
- **history button — show browsing history** (upper right) → `start-page.history`
- **show all favorites button — expand the full Favorites grid** (upper right) → `start-page.favorites-expanded`
- **privacy report card — open Safari's tracker-prevention report** (center) → `privacy-report.normal`
- **edit button — open Start Page customization** (center) → `customize-start-page.normal`
- **back button — return to the previous page when browsing history is available** (lower left)
- **address field — focus Safari’s address and search editor** (lower center) → `address-entry.normal`
- **tabs button — open the tab overview** (lower right) → `tabs.normal`

**Variable position:**
- **favorite tile — open the favorite website** (any favorite tile in the Favorites grid) → `web-page.normal` — *one of many*

### Favorites expanded mode

Safari's start page with the full Favorites grid expanded, moving Privacy Report and later sections downward.

**Fixed:**
- **start page button — show Safari’s Start Page** (upper left) → `start-page.normal`
- **bookmarks button — show bookmarks** (upper center) → `start-page.bookmarks`
- **reading list button — show Reading List** (upper center) → `start-page.reading-list`
- **history button — show browsing history** (upper right) → `start-page.history`
- **show less favorites button — collapse the Favorites grid** (upper right) → `start-page.normal`
- **privacy report card — open Safari’s tracker-prevention report** (lower center) → `privacy-report.normal`
- **back button — return to the previous page when browsing history is available** (lower left)
- **address field — focus Safari’s address and search editor** (lower center) → `address-entry.normal`
- **tabs button — open the tab overview** (lower right) → `tabs.normal`

**Variable position:**
- **favorite tile — open the favorite website** (any favorite tile in the expanded Favorites grid) → `web-page.normal` — *one of many*
- **expanded Start Page — scroll through sections moved below the full Favorites grid** (the vertically scrolling expanded Start Page)

### Bookmarks mode

The Bookmarks category on Safari's start page, showing recently saved bookmark cards, bookmark folders, a menu, and the bottom browser controls.

**Fixed:**
- **start page button — show Safari’s Start Page** (upper left) → `start-page.normal`
- **bookmarks button — show bookmarks** (upper center) → `start-page.bookmarks`
- **reading list button — show Reading List** (upper center) → `start-page.reading-list`
- **history button — show browsing history** (upper right) → `start-page.history`
- **bookmarks options button — open the bookmarks options menu** (upper right) → `start-page.bookmarks-menu`
- **recently saved disclosure — show the full Recently Saved collection** (upper center)
- **Favorites folder row — open the Favorites bookmark folder** (center)
- **Tab Group Favorites row — open favorites associated with tab groups** (center)
- **back button — return to the previous page when browsing history is available** (lower left)
- **address field — focus Safari’s address and search editor** (lower center) → `address-entry.normal`
- **tabs button — open the tab overview** (lower right) → `tabs.normal`

**Variable position:**
- **recently saved bookmark card — open the saved website** (any card in the horizontally scrolling Recently Saved row) → `web-page.normal` — *one of many*
- **recently saved card row — scroll horizontally through bookmark cards** (the horizontally scrolling Recently Saved card row)

### History menu mode

The History options menu offers website selection and destructive history clearing over the history list.

**Fixed:**
- **start page button — show Safari’s Start Page** (upper left) → `start-page.normal`
- **bookmarks button — show bookmarks** (upper center) → `start-page.bookmarks`
- **reading list button — show Reading List** (upper center) → `start-page.reading-list`
- **history button — show browsing history** (upper right) → `start-page.history`
- **select websites command — enter history selection mode** (upper right)
- **clear history command — open controls that delete browsing history** (upper right) — *mutates data*

**Variable position:**
- **outside area — dismiss the History options menu** (any visible area outside the History options menu) → `start-page.history`

### History mode

Safari's History category, with the current period expanded into page rows and older day groups collapsed in a vertically scrollable list.

**Fixed:**
- **start page button — show Safari’s Start Page** (upper left) → `start-page.normal`
- **bookmarks button — show bookmarks** (upper center) → `start-page.bookmarks`
- **reading list button — show Reading List** (upper center) → `start-page.reading-list`
- **history button — show browsing history** (upper right) → `start-page.history`
- **history options button — open selection and clearing commands** (upper right) → `start-page.history-menu`
- **expanded date-group disclosure — collapse the current history group** (upper right) → `start-page.history-collapsed`
- **back button — return to the previous page when browsing history is available** (lower left)
- **address field — focus Safari’s address and search editor** (lower center) → `address-entry.normal`
- **tabs button — open the tab overview** (lower right) → `tabs.normal`

**Variable position:**
- **history entry — open the recorded website** (any individual history entry in an expanded date group) → `web-page.normal` — *one of many*
- **collapsed date-group row — expand that period’s history entries** (any collapsed date-group row in the history list) → `start-page.history` — *one of many*
- **history list — scroll through older browsing periods** (the vertically scrolling history list)

### History collapsed mode

Safari History with all date groups collapsed into disclosure rows in a vertically scrollable list.

**Fixed:**
- **start page button — show Safari’s Start Page** (upper left) → `start-page.normal`
- **bookmarks button — show bookmarks** (upper center) → `start-page.bookmarks`
- **reading list button — show Reading List** (upper center) → `start-page.reading-list`
- **history button — show browsing history** (upper right) → `start-page.history`
- **history options button — open selection and clearing commands** (upper right) → `start-page.history-menu`
- **back button — return to the previous page when browsing history is available** (lower left)
- **address field — focus Safari’s address and search editor** (lower center) → `address-entry.normal`
- **tabs button — open the tab overview** (lower right) → `tabs.normal`

**Variable position:**
- **collapsed date-group row — expand that period’s history entries** (any collapsed date-group row in the history list) → `start-page.history` — *one of many*
- **history list — scroll through older browsing periods** (the vertically scrolling history list)

### Reading list mode

The empty Reading List category, showing an explanatory message plus category, options, address, back, and tab controls.

**Fixed:**
- **start page button — show Safari’s Start Page** (upper left) → `start-page.normal`
- **bookmarks button — show bookmarks** (upper center) → `start-page.bookmarks`
- **reading list button — show Reading List** (upper center) → `start-page.reading-list`
- **history button — show browsing history** (upper right) → `start-page.history`
- **reading list options button — open Reading List commands** (upper right)
- **back button — return to the previous page when browsing history is available** (lower left)
- **address field — focus Safari’s address and search editor** (lower center) → `address-entry.normal`
- **tabs button — open the tab overview** (lower right) → `tabs.normal`

### Bookmarks inline menu mode

The Bookmarks options menu while folders are inline, offering layout, restoring folders to the top section, selection, and folder creation.

**Fixed:**
- **start page button — show Safari’s Start Page** (upper left) → `start-page.normal`
- **bookmarks button — show bookmarks** (upper center) → `start-page.bookmarks`
- **reading list button — show Reading List** (upper center) → `start-page.reading-list`
- **history button — show browsing history** (upper right) → `start-page.history`
- **large layout option — switch to large bookmark cards and close the menu** (upper center) → `start-page.bookmarks-folders-inline`
- **compact layout option — switch to compact bookmark cards and close the menu** (upper center) → `start-page.bookmarks-folders-inline`
- **show folders on top toggle — restore the titled Folders section and close the menu** (upper right) → `start-page.bookmarks`
- **select bookmarks command — enter bookmark selection mode** (middle right)
- **new folder command — open bookmark-folder creation** (middle right)

**Variable position:**
- **outside area — dismiss the bookmarks options menu** (any visible area outside the inline-folder bookmarks options menu) → `start-page.bookmarks-folders-inline`

### Bookmarks menu mode

The Bookmarks options menu is open over the bookmarks category, with layout, sorting, folder placement, selection, and folder-creation commands. The software keyboard is visible below Safari.

**Fixed:**
- **start page button — show Safari’s Start Page** (upper left) → `start-page.normal`
- **bookmarks button — show bookmarks** (upper center) → `start-page.bookmarks`
- **reading list button — show Reading List** (upper center) → `start-page.reading-list`
- **history button — show browsing history** (upper right) → `start-page.history`
- **large layout option — switch to large bookmark cards and close the menu** (upper center) → `start-page.bookmarks`
- **compact layout option — switch to compact bookmark cards and close the menu** (upper center) → `start-page.bookmarks`
- **sort by submenu — open bookmark sort choices** (upper right) → `start-page.bookmarks-sort-menu`
- **show folders on top toggle — move folder rows between their titled section and inline placement** (middle right) → `start-page.bookmarks-folders-inline`
- **select bookmarks command — enter bookmark selection mode** (middle right)
- **new folder command — open bookmark-folder creation** (middle right)

**Variable position:**
- **outside area — dismiss the bookmarks options menu** (any visible area outside the bookmarks options menu) → `start-page.bookmarks`

### Bookmarks sort menu mode

The bookmark Sort By submenu is expanded over the Bookmarks category, offering None, Date Added, Name, and Address ordering.

**Fixed:**
- **start page button — show Safari’s Start Page** (upper left) → `start-page.normal`
- **bookmarks button — show bookmarks** (upper center) → `start-page.bookmarks`
- **reading list button — show Reading List** (upper center) → `start-page.reading-list`
- **history button — show browsing history** (upper right) → `start-page.history`
- **sort by header — collapse the sort choices** (upper right) → `start-page.bookmarks-menu`
- **none sort option — preserve bookmark order and close the menu** (center) → `start-page.bookmarks`
- **date added sort option — order bookmarks by date added and close the menu** (center) → `start-page.bookmarks`
- **name sort option — order bookmarks by name and close the menu** (center) → `start-page.bookmarks`
- **address sort option — order bookmarks by URL and close the menu** (center) → `start-page.bookmarks`

**Variable position:**
- **outside area — dismiss the expanded Sort By menu** (any visible area outside the expanded Sort By menu) → `start-page.bookmarks`

### Bookmarks folders inline mode

The Bookmarks category with Show Folders on Top disabled, placing folder rows directly below recently saved cards without a Folders heading.

**Fixed:**
- **start page button — show Safari’s Start Page** (upper left) → `start-page.normal`
- **bookmarks button — show bookmarks** (upper center) → `start-page.bookmarks`
- **reading list button — show Reading List** (upper center) → `start-page.reading-list`
- **history button — show browsing history** (upper right) → `start-page.history`
- **bookmarks options button — open the options menu for inline folder placement** (upper right) → `start-page.bookmarks-inline-menu`
- **recently saved disclosure — show the full Recently Saved collection** (upper center)
- **Favorites folder row — open the Favorites bookmark folder** (center)
- **Tab Group Favorites row — open favorites associated with tab groups** (center)
- **back button — return to the previous page when browsing history is available** (lower left)
- **address field — focus Safari’s address and search editor** (lower center) → `address-entry.normal`
- **tabs button — open the tab overview** (lower right) → `tabs.normal`

**Variable position:**
- **recently saved bookmark card — open the saved website** (any card in the horizontally scrolling Recently Saved row) → `web-page.normal` — *one of many*
- **recently saved card row — scroll horizontally through bookmark cards** (the horizontally scrolling Recently Saved card row)

## Privacy report

### Normal mode

Safari's Privacy Report sheet summarizes prevented trackers and lists websites by tracker activity, with Websites and Trackers views.

**Fixed:**
- **done button — close Privacy Report** (upper right) → `start-page.normal`
- **show more button — expand Privacy Report explanations** (upper center) → `privacy-report.explanation`
- **websites segment — keep website-centered tracker statistics visible** (middle left) → `privacy-report.normal`
- **trackers segment — list trackers by contacted websites** (middle right) → `privacy-report.trackers`

**Variable position:**
- **website row — show tracker details for that site** (any website row in the privacy report) — *one of many*
- **privacy report — scroll through website tracker statistics** (the vertically scrolling privacy report)

### Trackers mode

Privacy Report's Trackers view, listing contacted tracking domains and their website counts.

**Fixed:**
- **done button — close Privacy Report** (upper right) → `start-page.normal`
- **show more button — expand Privacy Report explanations** (upper center) → `privacy-report.explanation`
- **websites segment — return to website-centered tracker statistics** (middle left) → `privacy-report.normal`
- **trackers segment — keep tracker-centered statistics visible** (middle right) → `privacy-report.trackers`

**Variable position:**
- **tracker row — show websites associated with that tracker** (any tracker row in the privacy report) — *one of many*
- **privacy report — scroll through tracker statistics** (the vertically scrolling privacy report)

### Explanation mode

Privacy Report with the tracker-prevention explanation expanded above the report statistics.

**Fixed:**
- **done button — close Privacy Report** (upper right) → `start-page.normal`
- **show less button — collapse Privacy Report explanations** (upper center) → `privacy-report.normal`

**Variable position:**
- **expanded privacy report — scroll through explanations and statistics** (the vertically scrolling expanded privacy explanation and report)

## Customize start page

The Customize Start Page sheet, with iCloud sync, section visibility and ordering, and background image controls.

**Fixed:**
- **close button — dismiss Start Page customization** (upper right) → `start-page.normal`
- **use Start Page on all devices switch — toggle iCloud synchronization of Start Page appearance** (upper right)
- **background image switch — show or hide the selected Start Page background** (middle right)
- **add background tile — choose a custom Start Page background image** (lower left)

**Variable position:**
- **section visibility switch — show or hide that Start Page section** (any Start Page section visibility switch) — *one of many*
- **section reorder handle — drag to change Start Page section order** (any reorder handle beside a Start Page section) — *one of many*
- **background thumbnail — select that Start Page background** (any background image thumbnail) — *one of many*
- **background download icon — download that background choice** (any download icon on an uninstalled background thumbnail) — *one of many*
- **customization sheet — scroll through all Start Page sections and background choices** (the vertically scrolling customization sheet)

## Web page

### Normal mode

A loaded website in Safari, with page-provided content filling the viewport and Safari's bottom browser toolbar visible.

**Fixed:**
- **back button — attempt to return in browsing history; unavailable on this page** (lower left)
- **page menu button — open Safari page actions** (lower left) → `web-page.page-menu`
- **address field — focus the current URL for editing** (lower center) → `address-entry.normal`
- **reload button — reload the current website** (lower right) → `web-page.normal`
- **tabs button — open the tab overview** (lower right) → `tabs.normal`

**Variable position:**
- **web page link or control — follow a site-provided interaction within the loaded page** (any link or control supplied by the loaded web page) → `web-page.normal` — *one of many*
- **web page content area — scroll the page; this page remained at the same viewport** (the loaded web page content area)

### Page menu mode

Safari's page menu over a loaded website, with sharing, bookmark, find, zoom, distraction control, tab, privacy, desktop-site, and toolbar actions.

**Fixed:**
- **share command — open the system share sheet** (upper center) → `share-sheet.normal`
- **add to bookmarks command — save the current page as a bookmark** (upper center) — *mutates data*
- **add bookmark to command — save the current page into a chosen bookmark folder** (upper center) — *mutates data*
- **find on page command — open the in-page search bar** (upper center) → `web-page.find`
- **page zoom command — open page text and zoom controls** (center)
- **hide distracting items command — enter distraction-control mode** (center)
- **tab actions submenu — open actions for the current tab** (center)
- **privacy and security submenu — open per-site privacy controls** (center)
- **request desktop website command — reload the site using its desktop presentation** (center) → `web-page.normal`
- **hide toolbar command — collapse Safari’s browser toolbar** (center)

**Variable position:**
- **outside area — dismiss the page menu** (any visible area outside the page menu) → `web-page.normal`

### Find mode

Find on Page mode dims the website and shows a search field with close, previous-match, and next-match controls above the keyboard.

**Fixed:**
- **close find button — leave Find on Page mode** (middle left) → `web-page.normal`
- **find field — enter text to search within the loaded page** (center)
- **previous match button — move to the previous in-page match** (middle right)
- **next match button — move to the next in-page match** (middle right)

## Share sheet

The system share sheet for the current webpage, with item options, app destinations, quick actions, and a swipe-to-dismiss sheet.

**Fixed:**
- **options button — open sharing options for the current page** (center)
- **copy action — copy the current page URL** (lower left)
- **add to bookmarks action — save the current page as a bookmark** (lower center) — *mutates data*
- **add to reading list action — save the current page to Reading List** (lower center) — *mutates data*
- **view more action — show additional share-sheet actions** (lower right)

**Variable position:**
- **share destination — open the selected app’s share composer** (any app destination in the horizontally scrolling share row) — *one of many*
- **share sheet surface — swipe down to dismiss the sheet** (the share sheet surface; drag downward to dismiss) → `web-page.normal`

## Tabs

Safari's tab overview, showing a grid of open tab cards with search, options, tab-group controls, new-tab, and Done buttons.

**Fixed:**
- **tab search button — search open tabs** (upper left)
- **tab overview options button — open tab-management commands** (upper right)
- **new tab button — create a new tab and show Safari's start page** (lower left) → `start-page.normal`
- **Private button — switch to Private Browsing tabs** (lower center)
- **tab group button — keep the current tab group selected** (lower center)
- **done button — close the tab overview and return to the selected tab** (lower right) → `web-page.normal`

**Variable position:**
- **tab preview — select and open that tab** (any open tab preview card) → `web-page.normal` — *one of many*
- **tab close button — close the corresponding open tab** (the close button at the upper-right of any tab preview) — *mutates data* — *one of many*

## Address entry

Safari's focused address editor, with the current URL selected above the software keyboard and the bookmarks panel visible behind it.

**Fixed:**
- **start page button — show Safari’s Start Page** (upper left) → `start-page.normal`
- **bookmarks button — show bookmarks** (upper center) → `start-page.bookmarks`
- **reading list button — show Reading List** (upper center) → `start-page.reading-list`
- **history button — show browsing history** (upper right) → `start-page.history`
- **selected address field — edit or replace the current URL or search text** (center)
- **clear text button — clear the selected address field** (middle right)
- **cancel button — dismiss address editing and return to the loaded page** (middle right) → `web-page.normal`
