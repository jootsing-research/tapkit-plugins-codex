---
name: shortcuts
description: Layout and navigation of the Shortcuts iPhone app — its screens, modes, and where every control is located. Use when operating Shortcuts and you cannot find a control or a screen.
---

# Shortcuts app UI map

Positions describe equal thirds of the screen in a 3×3 grid: upper left, upper center, upper right; middle left, center, middle right; lower left, lower center, lower right. Elements under **Fixed** — bars, popups, sheets — sit in the listed region whenever the mode is shown. Locate the described control visually within that region before tapping. Elements under **Variable position** move with scrolling content; scroll to reveal them.

## All shortcuts

### Normal mode

The All Shortcuts grid shows shortcut cards beneath search, with editing and creation controls and the app tab bar.

**Fixed:**
- **back button — return to the Library screen** (upper left) → `library.normal`
- **edit button — enter shortcut selection mode** (upper right) → `all-shortcuts.select`
- **new shortcut button — creates and opens an auto-saving shortcut** (upper right) — *mutates data*
- **search field — focus and filter the visible shortcuts or actions** (upper center) → `all-shortcuts.search`
- **dictation button — request voice dictation for the search field** (upper right) → `dictation-permission.normal`
- **Library tab — show the Library root** (lower left) → `library.normal`
- **Automation tab — show personal automations** (lower center) → `automation.normal`
- **Gallery tab — browse suggested shortcuts** (lower right) → `gallery.normal`

**Variable position:**
- **shortcut card — runs the shortcut, which may perform arbitrary actions** (any shortcut card; moves as the grid scrolls) — *mutates data* — *one of many*
- **shortcut overflow button — open the shortcut editor without running it** (overflow button at the upper-right of any shortcut card; moves as the grid scrolls) → `shortcut-editor.existing` — *one of many*
- **scrollable content — browse additional items in the indicated direction** (shortcut grid; drag vertically to scroll)

### Select mode

All Shortcuts in selection mode shows Select All and Done, selection circles on cards, and bulk folder and delete actions.

**Fixed:**
- **select all button — toggle selection of every shortcut** (upper left)
- **done button — leave shortcut selection mode** (upper right) → `all-shortcuts.normal`
- **search field — focus shortcut search** (upper center) → `all-shortcuts.select-search`
- **dictation button — request voice dictation for the search field** (upper right) → `dictation-permission.normal`
- **add-to-folder bulk action — changes folder membership for selected shortcuts** (lower center) — *mutates data*
- **move-to-folder bulk action — changes folder membership for selected shortcuts** (lower center) — *mutates data*
- **delete bulk action — deletes selected shortcuts after confirmation** (lower center) — *mutates data*

**Variable position:**
- **shortcut selection control — toggle the shortcut selection** (any shortcut card or its selection circle; moves as the grid scrolls) — *one of many*
- **scrollable content — browse additional items in the indicated direction** (shortcut grid; drag vertically to scroll)

### Select search mode

All Shortcuts selection mode with focused search, an X control, and the keyboard visible when available.

**Fixed:**
- **select all button — toggle selection of every filtered shortcut** (upper left)
- **done button — leave selection mode while retaining focused search** (upper right) → `all-shortcuts.search`
- **search field — keep focus in the live shortcut filter** (upper center)
- **dictation button — request voice dictation for the search field** (upper right) → `dictation-permission.normal`
- **close search button — dismiss focused search** (upper right) → `all-shortcuts.normal`
- **add-to-folder bulk action — changes folder membership for selected shortcuts** (lower center) — *mutates data*
- **move-to-folder bulk action — changes folder membership for selected shortcuts** (lower center) — *mutates data*
- **delete bulk action — deletes selected shortcuts after confirmation** (lower center) — *mutates data*

**Variable position:**
- **shortcut selection control — toggle the shortcut's selection** (any visible shortcut card or its selection circle) — *one of many*
- **shortcut grid — scroll filtered selection results and reveal compact floating chrome** (shortcut grid; drag vertically to scroll filtered results) → `all-shortcuts.select-search-scrolled`

### Select search scrolled mode

All Shortcuts selection and search mode after scrolling, with Select All, Done, and search condensed into floating chrome over the grid.

**Fixed:**
- **select all button — toggle selection of every filtered shortcut** (upper left)
- **done button — leave selection mode while retaining the scrolled grid** (upper right) → `all-shortcuts.search-scrolled`
- **search field — focus the live shortcut filter** (upper center)
- **dictation button — request voice dictation for the search field** (upper right) → `dictation-permission.normal`
- **close search button — dismiss focused search** (upper right) → `all-shortcuts.select`
- **add-to-folder bulk action — changes folder membership for selected shortcuts** (lower center) — *mutates data*
- **move-to-folder bulk action — changes folder membership for selected shortcuts** (lower center) — *mutates data*
- **delete bulk action — deletes selected shortcuts after confirmation** (lower center) — *mutates data*

**Variable position:**
- **shortcut selection control — toggle the shortcut's selection** (any visible shortcut card or its selection circle in the scrolled grid) — *one of many*
- **shortcut grid — continue scrolling selection results** (scrolled shortcut grid; drag vertically to continue scrolling)

### Search scrolled mode

All Shortcuts after scrolling with focused search condensed into floating chrome over the card grid.

**Fixed:**
- **back button — return to the Library screen** (upper left) → `library.normal`
- **edit button — enter selection mode at the current scroll position** (upper right) → `all-shortcuts.select-search-scrolled`
- **new shortcut button — creates and opens an auto-saving shortcut** (upper right) — *mutates data*
- **search field — keep focus in the live shortcut filter** (upper center)
- **dictation button — request voice dictation for the search field** (upper right) → `dictation-permission.normal`
- **close search button — dismiss focused search** (upper right) → `all-shortcuts.scrolled`
- **Library tab — show the Library root** (lower left) → `library.normal`
- **Automation tab — show personal automations** (lower center) → `automation.normal`
- **Gallery tab — browse suggested shortcuts** (lower right) → `gallery.normal`

**Variable position:**
- **shortcut card — runs the shortcut, which may perform arbitrary actions** (any visible shortcut card in the scrolled grid) — *mutates data* — *one of many*
- **shortcut overflow button — open the shortcut editor without running it** (overflow button at the upper-right of any visible shortcut card in the scrolled grid) → `shortcut-editor.existing` — *one of many*
- **shortcut grid — continue scrolling filtered results** (scrolled shortcut grid; drag vertically to continue scrolling)

### Scrolled mode

All Shortcuts after scrolling, with a compact floating title bar over the shortcut grid and no search field.

**Fixed:**
- **back button — return to the Library screen** (upper left) → `library.normal`
- **edit button — enter selection mode at the current scroll position** (upper right) → `all-shortcuts.select-search-scrolled`
- **new shortcut button — creates and opens an auto-saving shortcut** (upper right) — *mutates data*
- **Library tab — show the Library root** (lower left) → `library.normal`
- **Automation tab — show personal automations** (lower center) → `automation.normal`
- **Gallery tab — browse suggested shortcuts** (lower right) → `gallery.normal`

**Variable position:**
- **shortcut card — runs the shortcut, which may perform arbitrary actions** (any visible shortcut card in the scrolled grid) — *mutates data* — *one of many*
- **shortcut overflow button — open the shortcut editor without running it** (overflow button at the upper-right of any visible shortcut card in the scrolled grid) → `shortcut-editor.existing` — *one of many*
- **shortcut grid — continue scrolling through shortcuts** (scrolled shortcut grid; drag vertically to continue scrolling)

### Search mode

All Shortcuts with focused search, an X control, and the keyboard visible when available.

**Fixed:**
- **edit button — enter selection mode** (upper right) → `all-shortcuts.select`
- **new shortcut button — creates and opens an auto-saving shortcut** (upper right) — *mutates data*
- **search field — focus and filter the visible shortcuts or actions** (upper center)
- **dictation button — request voice dictation for the search field** (upper right) → `dictation-permission.normal`
- **close search button — dismiss focused search** (upper right) → `all-shortcuts.normal`

**Variable position:**
- **shortcut card — runs the shortcut, which may perform arbitrary actions** (any visible shortcut card) — *mutates data* — *one of many*
- **shortcut overflow button — open the shortcut editor without running it** (overflow button at the upper-right of any visible shortcut card) → `shortcut-editor.existing` — *one of many*
- **scrollable content — browse additional items in the indicated direction** (shortcut grid; drag vertically to scroll filtered results)

## Gallery

### Normal mode

The Gallery presents curated shortcut collections and horizontally scrolling suggestion cards beneath search, with vertical section scrolling and the app tab bar.

**Fixed:**
- **search field — focus Gallery search** (upper center) → `gallery.search`
- **dictation button — request voice dictation for the search field** (upper right) → `dictation-permission.normal`
- **Library tab — show the Library root** (lower left) → `library.normal`
- **Automation tab — show personal automations** (lower center) → `automation.normal`
- **Gallery tab — browse suggested shortcuts** (lower right) → `gallery.normal`

**Variable position:**
- **featured collection banner — open the collection's themed Gallery sections** (any large featured collection banner) → `gallery-collection.normal` — *one of many*
- **See All button — open the complete list for that Gallery section** (See All button at the right of any Gallery section heading) → `gallery-section.normal` — *one of many*
- **suggested shortcut card — open its preview and setup sheet** (any suggested shortcut card in a horizontal carousel) → `gallery-shortcut-preview.normal` — *one of many*
- **add suggested shortcut button — adds the shortcut to the Library** (plus button at the upper-right of any suggested shortcut card) — *mutates data* — *one of many*
- **scrollable content — browse additional items in the indicated direction** (Gallery page; drag vertically to scroll sections)
- **shortcut carousel — browse additional suggestion cards horizontally** (any Gallery shortcut carousel; drag horizontally to browse cards) — *one of many*

### Search mode

The Gallery with its search field focused and an X control beside the expanded search field.

**Fixed:**
- **search field — keep focus in Gallery search** (upper center)
- **dictation button — request voice dictation for Gallery search** (upper right) → `dictation-permission.normal`
- **close search button — dismiss focused Gallery search** (upper right) → `gallery.normal`
- **Library tab — show the Library root** (lower left) → `library.normal`
- **Automation tab — show personal automations** (lower center) → `automation.normal`
- **Gallery tab — browse suggested shortcuts** (lower right) → `gallery.normal`

**Variable position:**
- **featured collection banner — open the themed Gallery collection** (any large featured collection banner) → `gallery-collection.normal` — *one of many*
- **See All button — open the complete list for that section** (See All button at the right of any Gallery section heading) → `gallery-section.normal` — *one of many*
- **suggested shortcut card — open its preview and setup sheet** (any suggested shortcut card in a horizontal carousel) → `gallery-shortcut-preview.normal` — *one of many*
- **add suggested shortcut button — adds the shortcut to the Library** (plus button at the upper-right of any suggested shortcut card) — *mutates data* — *one of many*
- **scrollable content — browse additional items in the indicated direction** (Gallery page; drag vertically to scroll sections)
- **shortcut carousel — browse additional suggestion cards horizontally** (any Gallery shortcut carousel; drag horizontally to browse cards) — *one of many*

## Gallery section

A Gallery section lists suggested shortcuts vertically with descriptions and individual add controls.

**Fixed:**
- **back or close button — return to the presenting screen** (upper left)
- **Library tab — show the Library root** (lower left) → `library.normal`
- **Automation tab — show personal automations** (lower center) → `automation.normal`
- **Gallery tab — browse suggested shortcuts** (lower right) → `gallery.normal`

**Variable position:**
- **suggested shortcut row — open a preview and setup sheet** (any suggested shortcut card-and-description row) → `gallery-shortcut-preview.normal` — *one of many*
- **add suggested shortcut button — adds the shortcut to the Library** (plus button on any suggested shortcut row) — *mutates data* — *one of many*
- **scrollable content — browse additional items in the indicated direction** (Gallery section list; drag vertically to scroll)

## Gallery shortcut preview

A Gallery shortcut preview sheet shows the shortcut description, preview card, availability notes, sharing, and a setup button.

**Fixed:**
- **back or close button — return to the presenting screen** (upper left)
- **share button — opens sharing for the Gallery shortcut** (upper right) — *mutates data*
- **Set Up Shortcut button — begins configuring and adding the shortcut** (lower center) — *mutates data*

**Variable position:**
- **preview overflow button — inspect the shortcut's read-only action list** (overflow button on the shortcut preview card) → `gallery-shortcut-actions.normal`

## Gallery shortcut actions

A read-only action-list preview shows the Gallery shortcut's actions and explanatory comments.

**Fixed:**
- **done button — return to the Gallery shortcut preview** (upper right) → `gallery-shortcut-preview.normal`

**Variable position:**
- **action disclosure button — reveal or hide additional action details** (blue disclosure button on any preview action) — *one of many*
- **scrollable content — browse additional items in the indicated direction** (read-only action list; drag vertically to scroll)

## Gallery collection

A themed Gallery collection lists sections of suggested shortcuts in horizontal carousels, each with See All and add controls.

**Fixed:**
- **back button — return to the Gallery** (upper left)
- **Library tab — show the Library root** (lower left) → `library.normal`
- **Automation tab — show personal automations** (lower center) → `automation.normal`
- **Gallery tab — show suggested shortcuts** (lower right) → `gallery.normal`

**Variable position:**
- **See All button — open the complete list for that section** (See All button at the right of any collection section heading) → `gallery-section.normal` — *one of many*
- **suggested shortcut card — open its preview and setup sheet** (any suggested shortcut card in a collection carousel) → `gallery-shortcut-preview.normal` — *one of many*
- **add suggested shortcut button — adds the shortcut to the Library** (plus button at the upper-right of any suggested shortcut card) — *mutates data* — *one of many*
- **scrollable content — browse additional items in the indicated direction** (collection page; drag vertically to scroll sections)
- **shortcut carousel — browse additional suggestion cards horizontally** (any collection shortcut carousel; drag horizontally to browse cards) — *one of many*

## Library

### Normal mode

The Library root lists built-in shortcut collections and user folders, with editing and folder creation controls and the app tab bar.

**Fixed:**
- **edit button — enter folder editing mode** (upper right) → `library.edit`
- **new folder button — creates a new shortcut folder** (upper right) — *mutates data*
- **Library tab — show the Library root** (lower left) → `library.normal`
- **Automation tab — show personal automations** (lower center) → `automation.normal`
- **Gallery tab — browse suggested shortcuts** (lower right) → `gallery.normal`

**Variable position:**
- **scrollable content — browse additional items in the indicated direction** (All Shortcuts row near the top of the Library list)
- **scrollable content — browse additional items in the indicated direction** (Share Sheet row near the top of the Library list)
- **scrollable content — browse additional items in the indicated direction** (Apple Watch row near the top of the Library list)
- **scrollable content — browse additional items in the indicated direction** (any user folder row in the Folders section; moves as the list scrolls) — *one of many*
- **scrollable content — browse additional items in the indicated direction** (Library list; drag vertically to scroll)

### Edit mode

The Library in folder editing mode shows a completion button plus delete, information, and reorder controls on user folders.

**Fixed:**
- **done button — leave folder editing mode** (upper right) → `library.normal`
- **Library tab — show the Library root** (lower left) → `library.normal`
- **Automation tab — show personal automations** (lower center) → `automation.normal`
- **Gallery tab — browse suggested shortcuts** (lower right) → `gallery.normal`

**Variable position:**
- **All Shortcuts row — open the complete shortcut grid and leave folder editing mode** (All Shortcuts row near the top of the Library list) → `all-shortcuts.normal`
- **Share Sheet row — open shortcuts available from the share sheet and leave folder editing mode** (Share Sheet row near the top of the Library list) → `share-sheet.normal`
- **scrollable content — browse additional items in the indicated direction** (Apple Watch row near the top of the Library list)
- **folder remove button — begins deleting the folder** (red remove button beside any user folder; moves as the list scrolls) — *mutates data* — *one of many*
- **scrollable content — browse additional items in the indicated direction** (information button beside any user folder; moves as the list scrolls) — *one of many*
- **folder reorder handle — changes the folder order when dragged** (reorder handle beside any user folder; moves as the list scrolls) — *mutates data* — *one of many*
- **scrollable content — browse additional items in the indicated direction** (Library list; drag vertically to scroll)

## Share sheet

### Normal mode

The Share Sheet collection shows shortcuts enabled for the system share sheet in a searchable card grid.

**Fixed:**
- **back button — return to the presenting Library mode** (upper left)
- **edit button — enter shortcut selection mode** (upper right) → `share-sheet.select`
- **new shortcut button — creates and opens an auto-saving shortcut** (upper right) → `shortcut-editor.normal` — *mutates data*
- **search field — focus and filter the visible shortcuts or actions** (upper center) → `share-sheet.search`
- **dictation button — request voice dictation for the search field** (upper right) → `dictation-permission.normal`
- **Library tab — show the Library root** (lower left) → `library.normal`
- **Automation tab — show personal automations** (lower center) → `automation.normal`
- **Gallery tab — browse suggested shortcuts** (lower right) → `gallery.normal`

**Variable position:**
- **shortcut card — runs the shortcut, which may perform arbitrary actions** (any shortcut card; moves as the grid scrolls) — *mutates data* — *one of many*
- **shortcut overflow button — open the shortcut editor without running it** (overflow button at the upper-right of any shortcut card; moves as the grid scrolls) → `shortcut-editor.existing` — *one of many*
- **scrollable content — browse additional items in the indicated direction** (shortcut grid; drag vertically to scroll)

### Select mode

The Share Sheet collection in selection mode replaces the title controls with Select All and Done, adds selection circles to cards, and shows bulk actions.

**Fixed:**
- **select all button — toggle selection of every visible shortcut** (upper left)
- **done button — leave shortcut selection mode** (upper right) → `share-sheet.normal`
- **search field — focus shortcut search** (upper center) → `share-sheet.select-search`
- **dictation button — request voice dictation for the search field** (upper right) → `dictation-permission.normal`
- **add-to-folder bulk action — changes folder membership for selected shortcuts** (center) — *mutates data*
- **share bulk action — opens sharing for selected shortcuts** (center) — *mutates data*
- **delete bulk action — deletes selected shortcuts after confirmation** (center) — *mutates data*

**Variable position:**
- **shortcut selection control — toggle the shortcut's selection** (any shortcut card or its selection circle; moves as the grid scrolls) — *one of many*
- **shortcut grid — attempt to scroll selection results** (shortcut grid; drag vertically to scroll)

### Select search mode

Share Sheet selection mode with the search field focused, an on-screen keyboard visible, and an X control beside the expanded search field.

**Fixed:**
- **select all button — toggle selection of every filtered shortcut** (upper left)
- **done button — leave selection mode while keeping search focused** (upper right) → `share-sheet.search`
- **search field — keep focus in the live shortcut filter** (upper center)
- **dictation button — request voice dictation for the search field** (upper right) → `dictation-permission.normal`
- **close search button — dismiss focused search and the keyboard** (upper right) → `share-sheet.select`
- **add-to-folder bulk action — changes folder membership for selected shortcuts** (center) — *mutates data*
- **share bulk action — opens sharing for selected shortcuts** (center) — *mutates data*
- **delete bulk action — deletes selected shortcuts after confirmation** (center) — *mutates data*

**Variable position:**
- **shortcut selection control — toggle the shortcut's selection while search remains focused** (any visible shortcut card or its selection circle above the keyboard) → `share-sheet.select-search` — *one of many*
- **shortcut grid — attempt to scroll filtered selection results** (shortcut grid above the keyboard; drag vertically to scroll)

### Search mode

The Share Sheet collection with search focused, the keyboard visible, and an X control beside the expanded search field.

**Fixed:**
- **edit button — enter selection mode while keeping search focused** (upper right) → `share-sheet.select-search`
- **screen control — perform the labeled interface action** (upper right)
- **search field — focus and filter the visible shortcuts or actions** (upper center)
- **dictation button — request voice dictation for the search field** (upper right) → `dictation-permission.normal`
- **close search button — dismiss focused search** (upper right) → `share-sheet.normal`

**Variable position:**
- **shortcut card — runs the shortcut, which may perform arbitrary actions** (any visible shortcut card above the keyboard) — *mutates data* — *one of many*
- **shortcut overflow button — open the shortcut editor without running it** (overflow button at the upper-right of any visible shortcut card above the keyboard) → `shortcut-editor.existing` — *one of many*
- **scrollable content — browse additional items in the indicated direction** (shortcut grid above the keyboard; drag vertically to scroll)

## Dictation permission

A system alert asks whether to enable Dictation after the search microphone is used.

**Fixed:**
- **Enable Dictation button — enables the system Dictation setting** (center) — *mutates data*
- **Not Now button — dismiss the Dictation prompt without changing settings** (center)
- **About Siri, Dictation & Privacy button — open Apple's Dictation privacy information** (lower center) → `dictation-privacy.normal`

## Dictation privacy

### Normal mode

A scrollable system sheet explains Siri and Dictation privacy and includes a link to Apple's legal site.

**Fixed:**
- **close button — return to the presenting Dictation prompt** (upper left)

**Variable position:**
- **apple.com legal link — open Apple's Improve Siri and Dictation privacy page outside Shortcuts** (apple.com legal link within the privacy text; moves as the sheet scrolls)
- **privacy information sheet — scroll through the privacy explanation and reveal compact title chrome** (privacy information sheet; drag vertically to scroll) → `dictation-privacy.scrolled`

### Scrolled mode

The Dictation privacy sheet after scrolling, with its title condensed into the fixed top bar.

**Fixed:**
- **close button — return to the presenting Dictation prompt** (upper left)

**Variable position:**
- **apple.com legal link — open Apple's Improve Siri and Dictation privacy page outside Shortcuts** (apple.com legal link within the privacy text; moves as the sheet scrolls)
- **privacy information sheet — continue scrolling through the explanation** (privacy information sheet; drag vertically to scroll)

## Shortcut editor

### Normal mode

The shortcut editor shows the shortcut name, its Share Sheet input configuration, and a lower action drawer with search, categories, suggestions, and apps.

**Fixed:**
- **back button — leave the editor and return to the presenting shortcut collection** (upper left)
- **shortcut name menu button — open shortcut management actions** (upper right) → `shortcut-editor.name-menu`
- **search field — focus and filter the visible shortcuts or actions** (center)
- **dictation button — request voice dictation for the search field** (middle right) → `dictation-permission.normal`

**Variable position:**
- **input types parameter — changes which input types the shortcut accepts** (blue input-types parameter in the Receive block) — *mutates data*
- **Share Sheet source parameter — changes where the shortcut is available** (blue Share Sheet source parameter in the Receive block) — *mutates data*
- **no-input behavior parameter — changes how the shortcut handles missing input** (blue no-input behavior parameter in the Receive block) — *mutates data*
- **action drawer grabber — expand or collapse the action drawer** (action drawer grabber above Search Actions)
- **action category chip — filter the action drawer by category** (any action category chip beneath Search Actions) — *one of many*
- **suggested action row — adds that action to the shortcut** (any suggested action row in the action drawer) — *mutates data* — *one of many*
- **information button — show details for the adjacent item** (information button at the right of any suggested action row) — *one of many*
- **app row — browse actions supplied by that app** (any app row in the action drawer) — *one of many*
- **scrollable content — browse additional items in the indicated direction** (action drawer contents; drag vertically to scroll)

### Existing mode

The editor for an existing shortcut shows its action stack, editable parameters, and a collapsed lower action drawer with shortcut controls.

**Fixed:**
- **back button — leave the editor and return to the presenting shortcut collection** (upper left)
- **shortcut name menu button — open shortcut management actions** (upper center) → `shortcut-editor.name-menu`
- **search field — focus and filter the visible shortcuts or actions** (lower center)
- **dictation button — request voice dictation for the search field** (lower right) → `dictation-permission.normal`
- **undo button — reverses the last shortcut edit** (lower left) — *mutates data*
- **redo button — reapplies an undone shortcut edit** (lower left) — *mutates data*
- **shortcut information button — show shortcut details** (lower center)
- **share button — opens sharing for the shortcut** (lower right) — *mutates data*
- **run button — runs the shortcut and may perform arbitrary actions** (lower right) — *mutates data*

**Variable position:**
- **action card drag gesture — changes the order of actions** (any action card in the shortcut action stack; drag to reorder) — *mutates data* — *one of many*
- **action parameter — changes the configured action value** (any editable text or blue parameter within an action card) — *mutates data* — *one of many*
- **remove action button — deletes that action from the shortcut** (gray remove button at the upper-right of any action card) — *mutates data* — *one of many*
- **action disclosure button — reveal or hide advanced action options** (blue disclosure button at the right of an action card) → `shortcut-editor.action-expanded` — *one of many*
- **action drawer grabber — expand or collapse the action drawer** (action drawer grabber above Search Actions)

### Action expanded mode

The existing shortcut editor with one action expanded to show its advanced options, including Local Only and Expire At controls.

**Fixed:**
- **back button — leave the editor and return to the presenting shortcut collection** (upper left)
- **shortcut name menu button — open shortcut management actions** (upper center) → `shortcut-editor.name-menu`
- **search field — focus and filter the visible shortcuts or actions** (lower center)
- **dictation button — request voice dictation for the search field** (lower right) → `dictation-permission.normal`
- **undo button — reverses the last shortcut edit** (lower left) — *mutates data*
- **redo button — reapplies an undone shortcut edit** (lower left) — *mutates data*
- **shortcut information button — show shortcut details** (lower center)
- **share button — opens sharing for the shortcut** (lower right) — *mutates data*
- **run button — runs the shortcut and may perform arbitrary actions** (lower right) — *mutates data*

**Variable position:**
- **action card drag gesture — changes the order of actions** (any action card in the shortcut action stack; drag to reorder) — *mutates data* — *one of many*
- **action parameter — changes the configured action value** (any editable text or blue parameter within an action card) — *mutates data* — *one of many*
- **remove action button — deletes that action from the shortcut** (gray remove button at the upper-right of any action card) — *mutates data* — *one of many*
- **action disclosure button — collapse advanced action options** (blue disclosure button on the expanded action) → `shortcut-editor.existing`
- **Local Only toggle — changes whether clipboard content stays local** (Local Only toggle in the expanded action) — *mutates data*
- **Expire At control — changes clipboard expiration behavior** (Expire At control in the expanded action) — *mutates data*
- **action drawer grabber — expand or collapse the action drawer** (action drawer grabber above Search Actions)

### Name menu mode

A shortcut-name popover offers rename, icon, duplicate, move, and Home Screen management actions over the editor.

**Fixed:**
- **Rename action — changes the shortcut name** (upper center) — *mutates data*
- **Choose Icon action — changes the shortcut icon** (upper center) — *mutates data*
- **Duplicate action — creates a copy of the shortcut** (upper center) — *mutates data*
- **Move action — changes the shortcut folder** (upper center) — *mutates data*
- **Add to Home Screen action — creates a Home Screen shortcut icon** (upper center) — *mutates data*

**Variable position:**
- **outside popover — dismiss the shortcut-name menu** (outside the shortcut-name popover) → `shortcut-editor.existing`

## Automation

The Automation tab is empty and offers a single control to create the first personal automation.

**Fixed:**
- **New Automation button — begins creating a personal automation** (center) — *mutates data*
- **Library tab — show the Library root** (lower left) → `library.normal`
- **Automation tab — show personal automations** (lower center) → `automation.normal`
- **Gallery tab — browse suggested shortcuts** (lower right) → `gallery.normal`
