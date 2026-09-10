---
name: messages
description: Layout and navigation of the Messages iPhone app — its screens, modes, and where every control is located. Use when operating Messages and you cannot find a control or a screen.
---

# Messages app UI map

Positions describe equal thirds of the screen in a 3×3 grid: upper left, upper center, upper right; middle left, center, middle right; lower left, lower center, lower right. Elements under **Fixed** — bars, popups, sheets — sit in the listed region whenever the mode is shown. Locate the described control visually within that region before tapping. Elements under **Variable position** move with scrolling content; scroll to reveal them.

## Messages

### Normal mode

The empty Messages conversation list, with editing and filtering controls above and search and compose controls below.

**Fixed:**
- **edit button — open the Messages editing menu** (upper left) → `messages.edit-menu`
- **filters button — open the Messages filter list** (upper right) → `messages.filters`
- **search field — enter conversation search mode** (lower center) → `messages.search`
- **audio input button — start voice transcription for search** (lower right) — *mutates data*
- **compose button — start a new message draft** (lower right) → `compose.normal`

### Edit menu mode

The conversation list with the Edit popover open, offering profile setup while the list controls remain visible behind it.

**Fixed:**
- **set up name and photo button — open Share Name and Photo introduction** (upper center) → `share-name-photo.normal`
- **filters button — open the Messages filter list** (upper right) → `messages.filters`
- **search field — enter conversation search mode** (lower center) → `messages.search`
- **audio input button — start voice transcription for search** (lower right) — *mutates data*
- **compose button — start a new message draft** (lower right) → `compose.normal`

**Variable position:**
- **outside popover — dismiss the Edit menu** (any point outside the Edit popover) → `messages.normal`

### Search mode

The conversation list in active search mode, with an empty search field, voice input, a cancel control, and the keyboard visible.

**Fixed:**
- **search field — type a query to filter conversations and message content** (center) → `messages.search-results`
- **audio input button — start voice transcription for the search query** (middle right) — *mutates data*
- **cancel button — clear search and return to the conversation list** (middle right) → `messages.normal`

### Search results mode

The conversation list searching for a typed query, with no matching conversations on this empty phone.

**Fixed:**
- **search field — edit the active query** (center) → `messages.search-results`
- **clear button — erase the typed search query** (middle right) → `messages.search`
- **cancel button — clear search and return to the conversation list** (middle right) → `messages.normal`

### Filters mode

The empty conversation list with a filter popover offering Messages, Spam, Recently Deleted, and filtering management.

**Fixed:**
- **Messages filter — show the ordinary conversation list** (upper center) → `messages.normal`
- **Spam filter — show conversations classified as spam** (upper center) → `spam.normal`
- **Recently Deleted filter — show recoverable deleted conversations** (upper center) → `recently-deleted.normal`
- **Manage Filtering button — open Messages filtering settings** (upper center) → `filtering-settings.normal`

## Compose

### Normal mode

A New Message sheet with an empty recipient field and message composer, app drawer control, and keyboard.

**Fixed:**
- **close button — discard the empty message draft and return to the conversation list** (upper right)
- **recipient field — enter a person, phone number, or address for the new message** (upper center) — *mutates data*
- **add recipient button — open the contact picker** (upper right) → `contact-picker.normal`
- **Messages apps button — open the app drawer** (middle left) → `compose.app-drawer`
- **message field — enter the outgoing message body** (center) — *mutates data*
- **audio message button — begin recording an outgoing voice message** (middle right) — *mutates data*

### App drawer mode

The New Message sheet with the Messages app drawer open over the keyboard, listing attachment and message-service integrations.

**Fixed:**
- **close button — discard the empty message draft and return to the conversation list** (upper right)
- **recipient field — enter a person, phone number, or address for the new message** (upper center) — *mutates data*
- **add recipient button — open the contact picker** (upper right) → `contact-picker.normal`
- **Camera app button — capture media for the outgoing message** (center) — *mutates data*
- **Photos app button — select photo-library media for the outgoing message** (center) — *mutates data*
- **Stickers app button — choose a sticker for the outgoing message** (center) — *mutates data*
- **Apple Cash app button — start an Apple Cash payment request** (center) — *mutates data*
- **Send Later app button — schedule the outgoing message** (lower center) — *mutates data*
- **Audio app button — record an audio attachment** (lower center) — *mutates data*
- **Store button — open the iMessage App Store** (lower center)

**Variable position:**
- **outside drawer — dismiss the Messages app drawer** (any point outside the app drawer) → `compose.normal`

## Contact picker

### Normal mode

The contact picker for a new message, showing the phone's contact list and a search field.

**Fixed:**
- **back button — return to the empty New Message sheet** (upper left)
- **close button — dismiss the contact picker** (upper right)
- **search field — filter the contact list by name** (lower center) → `contact-picker.search`

**Variable position:**
- **contact row — add that contact as the message recipient** (any contact row in the list) — *mutates data* — *one of many*

### Search mode

The contact picker with its search field focused and the keyboard available for filtering contacts.

**Fixed:**
- **search field — type or edit the contact filter** (center) → `contact-picker.search`
- **close button — dismiss the contact picker** (upper right)

## Spam

### Normal mode

The empty Spam conversation filter, with editing and filtering controls and disabled bulk actions.

**Fixed:**
- **edit button — enter Spam conversation selection mode** (upper left) → `spam.edit-menu`
- **filters button — open the Messages filter list** (upper right) → `spam.filters`
- **Read All button — mark all spam conversations as read; disabled while the list is empty** (lower left) — *mutates data*
- **delete button — delete selected spam conversations; disabled while the list is empty** (lower right) — *mutates data*

### Filters mode

The empty Spam list with the shared Messages filter popover open.

**Fixed:**
- **Messages filter — show the ordinary conversation list** (upper center) → `messages.normal`
- **Spam filter — show conversations classified as spam** (upper center) → `spam.normal`
- **Recently Deleted filter — show recoverable deleted conversations** (upper center) → `recently-deleted.normal`
- **Manage Filtering button — open Messages filtering settings** (upper center) → `filtering-settings.normal`

### Edit menu mode

The empty Spam list with the Edit popover open, offering shared-profile setup while bulk actions remain disabled.

**Fixed:**
- **set up name and photo button — open Share Name and Photo introduction** (upper center) → `share-name-photo.normal`
- **filters button — open the Messages filter list** (upper right) → `spam.filters`
- **Read All button — mark all spam conversations as read; disabled while the list is empty** (lower left) — *mutates data*
- **delete button — delete selected spam conversations; disabled while nothing is selected** (lower right) — *mutates data*

**Variable position:**
- **outside popover — dismiss the Edit menu** (any point outside the Edit popover) → `spam.normal`

## Recently deleted

### Normal mode

The empty Recently Deleted conversation filter, with disabled recovery and permanent-deletion controls.

**Fixed:**
- **filters button — open the Messages filter list** (upper right) → `recently-deleted.filters`
- **Recover All button — restore all deleted conversations; disabled while the list is empty** (lower left) — *mutates data*
- **delete button — permanently delete selected conversations; disabled while the list is empty** (lower right) — *mutates data*

### Filters mode

The empty Recently Deleted list with the shared Messages filter popover open.

**Fixed:**
- **Messages filter — show the ordinary conversation list** (upper center) → `messages.normal`
- **Spam filter — show conversations classified as spam** (upper center) → `spam.normal`
- **Recently Deleted filter — show recoverable deleted conversations** (upper center) → `recently-deleted.normal`
- **Manage Filtering button — open Messages filtering settings** (upper center) → `filtering-settings.normal`

## Filtering settings

### Normal mode

The system Messages settings page at its filtering section, showing sharing rows, unknown-sender and spam controls, and conversation display settings.

**Fixed:**
- **back button — return to Messages** (upper left)
- **Share Name and Photo row — open shared-profile settings** (upper center) → `share-name-photo.normal`
- **Shared with You row — configure per-app content sharing** (center) → `shared-with-you.normal`
- **Screen Unknown Senders switch — enable or disable unknown-sender screening** (middle right) — *mutates data*
- **Text Message Filter row — shows the selected filtering extension; unavailable because none is installed** (center)
- **Filter Spam switch — enable or disable automatic spam filtering** (lower right) — *mutates data*
- **Conversation Backgrounds switch — enable or disable conversation backgrounds** (lower right) — *mutates data*
- **Start with Photos Visible switch — change the default photo tray visibility** (lower right) — *mutates data*

**Variable position:**
- **settings list — scroll through additional Messages preferences** (Messages settings list; drag upward to reveal additional settings) → `filtering-settings.scrolled`

### Scrolled mode

The Messages settings page after scrolling, revealing additional preference groups below filtering.

**Fixed:**
- **back button — return to Messages** (upper left)

**Variable position:**
- **settings list — scroll back toward the top of Messages preferences** (Messages settings list; drag downward to return to the top) → `filtering-settings.normal`

## Shared with you

The Shared with You settings page, with a master automatic-sharing switch and a scrollable list of per-app switches.

**Fixed:**
- **back button — return to Messages settings** (upper left)
- **Automatic Sharing switch — enable or disable Shared with You globally** (upper right) — *mutates data*

**Variable position:**
- **per-app switch — enable or disable Shared with You for that app** (any per-app switch in the Apps list) — *mutates data* — *one of many*
- **Apps list — scroll through all apps participating in Shared with You** (Apps list; drag upward to reveal more apps) → `shared-with-you.normal`

## Share name photo

An introduction explaining that Share Name and Photo applies across the Apple Account's other devices, with Continue and Cancel controls.

**Fixed:**
- **continue button — proceed to choose an avatar** (lower center) → `profile-avatar.normal`
- **cancel button — abandon shared-profile setup and return to Messages** (lower center) → `messages.normal`

## Profile avatar

### Normal mode

The avatar picker, with Avatar and Poster tabs, creation sources, and a vertically scrollable grid of preset avatar styles.

**Fixed:**
- **close button — cancel profile setup and return to Messages** (upper left)
- **Avatar tab — show avatar choices** (upper center) → `profile-avatar.normal`
- **Poster tab — show contact-poster choices** (upper center) → `profile-avatar.poster`
- **photos avatar source — open Camera and Photo Library menu** (upper left) → `profile-avatar.photos-menu`
- **monogram avatar source — preview the initials avatar and sharing profile** (upper center) → `profile-preview.normal`
- **Memoji avatar source — create or choose a Memoji for the profile draft** (upper center) — *mutates data*
- **Emoji avatar source — choose an emoji for the profile draft** (upper right) — *mutates data*

**Variable position:**
- **preset avatar style — select it for the shared profile draft** (any preset avatar style in the scrolling grid) — *mutates data* — *one of many*
- **avatar grid — scroll through additional preset avatar styles** (avatar grid; drag upward to scroll) → `profile-avatar.normal`

### Poster mode

The poster picker, with Avatar and Poster tabs, photo, monogram, and Memoji sources, and a vertically scrollable grid of preset contact-poster styles.

**Fixed:**
- **close button — cancel profile setup and return to its introduction** (upper left)
- **Avatar tab — show avatar choices** (upper center) → `profile-avatar.normal`
- **Poster tab — show contact-poster choices** (upper center) → `profile-avatar.poster`
- **photos poster source — open Camera and Photo Library choices** (upper left) → `profile-avatar.photos-menu`
- **monogram poster source — preview an initials-based contact poster** (upper center) → `profile-preview.normal`
- **Memoji poster source — open the Memoji poster editor** (upper right) — *mutates data*

**Variable position:**
- **preset contact-poster style — select it for the shared profile draft** (any preset contact-poster style in the scrolling grid) — *mutates data* — *one of many*
- **poster grid — scroll through additional preset contact-poster styles** (poster grid; drag upward to scroll) → `profile-avatar.poster`

### Photos menu mode

The avatar picker with a small source menu offering Camera and Photo Library.

**Fixed:**
- **close button — cancel profile setup and return to Messages** (upper left)
- **Avatar tab — show avatar choices behind the source menu** (upper center) → `profile-avatar.normal`
- **Poster tab — show contact-poster choices** (upper center) → `profile-avatar.poster`
- **camera button — capture a new profile image** (upper left) — *mutates data*
- **photo library button — open the system photo picker** (upper left) → `photo-picker.photos`

**Variable position:**
- **outside popover — dismiss the Photos source menu** (any point outside the Photos source popover) → `profile-avatar.normal`

## Photo picker

### Photos mode

The system photo picker sheet in Photos view, with a close control, Photos and Collections tabs, photo thumbnails, and search.

**Fixed:**
- **close button — dismiss the system photo picker** (upper left)
- **Photos tab — show photo-library thumbnails** (upper center) → `photo-picker.photos`
- **Collections tab — show photo collections** (upper center) → `photo-picker.collections`
- **search button — search the photo library** (lower right) → `photo-picker.photos`

**Variable position:**
- **photo thumbnail — select that image for the profile draft** (any photo thumbnail in the picker grid) — *mutates data* — *one of many*

### Collections mode

The system photo picker in Collections view, with pinned collection tiles and vertically scrolling album sections.

**Fixed:**
- **close button — dismiss the system photo picker** (upper left)
- **Photos tab — show photo-library thumbnails** (upper center) → `photo-picker.photos`
- **Collections tab — show photo collections** (upper center) → `photo-picker.collections`
- **Pinned disclosure — open the full pinned collections grid** (upper left) → `photo-picker-pinned.normal`

**Variable position:**
- **pinned collection tile — open that photo collection** (any pinned collection tile in the horizontal row) → `photo-picker-collection.normal` — *one of many*
- **album or collection row — open that group of photos** (any available album or collection row) → `photo-picker-collection.normal` — *one of many*
- **collections content — scroll through additional albums and collection groups** (collections content; drag upward to scroll) → `photo-picker.collections`

## Photo picker pinned

A two-column grid of pinned photo collections inside the system picker.

**Fixed:**
- **back button — return to the presenting screen** (upper left)

## Profile preview

### Normal mode

A preview of the selected initials avatar and contact poster, followed by name and automatic-sharing settings.

**Fixed:**
- **back button — return to the avatar picker** (upper left)
- **edit avatar button — open the monogram editor** (center) → `monogram-editor.normal`
- **contact preview card — switch between the profile's avatar and poster preview** (lower center) → `profile-preview.avatar`
- **first name field — edit the shared first name** (lower center) — *mutates data*
- **last name field — edit the shared last name** (lower center) — *mutates data*
- **share automatically setting — change who receives the shared profile** (lower center) — *mutates data*

**Variable position:**
- **profile form — scroll to reveal the remaining profile controls** (profile form; drag upward to reveal lower controls) → `profile-preview.avatar`

### Avatar mode

The shared-profile preview in its compact avatar state, with the complete name and sharing form plus the final Done button visible.

**Fixed:**
- **back button — return to the avatar picker** (upper left)
- **edit avatar button — open the profile image editor** (center) → `monogram-editor.normal`
- **contact preview card — switch between the avatar and poster preview** (center) → `profile-preview.normal`
- **first name field — edit the shared first name** (lower center) — *mutates data*
- **last name field — edit the shared last name** (lower center) — *mutates data*
- **share automatically setting — change who receives the shared profile** (lower center) — *mutates data*
- **done button — save and enable the shared Messages profile** (lower center) — *mutates data*

## Monogram editor

### Normal mode

The shared-profile avatar editor, showing the current monogram above photo, Memoji, and monogram source sections.

**Fixed:**
- **close button — discard editor changes and return to the profile preview** (upper left)
- **Avatar tab — show avatar editing controls** (upper center) → `monogram-editor.normal`
- **Poster tab — show poster editing controls** (upper center) → `monogram-editor.poster`
- **done button — save the edited profile image** (upper right) — *mutates data*
- **customize button — open monogram appearance controls** (center) → `monogram-customize.normal`
- **choose a photo button — open the system photo picker** (lower left) → `photo-picker.photos`
- **Memoji disclosure — open the Memoji avatar chooser** (lower left) — *mutates data*
- **Monogram disclosure — open additional initials-based avatar choices** (lower left) — *mutates data*

**Variable position:**
- **Memoji preset — select it as the draft profile avatar** (any Memoji preset in the horizontal row) — *mutates data* — *one of many*
- **avatar source list — scroll through additional profile image sources** (avatar source list; drag upward to reveal more source options) → `monogram-editor.normal`

### Poster mode

The shared-profile poster editor, showing the current tall contact-poster preview above photo, Memoji, and monogram source sections.

**Fixed:**
- **close button — discard editor changes and return to the profile preview** (upper left)
- **Avatar tab — show avatar editing controls** (upper center) → `monogram-editor.normal`
- **Poster tab — show poster editing controls** (upper center) → `monogram-editor.poster`
- **done button — save the edited contact poster** (upper right) — *mutates data*
- **customize button — open poster appearance controls** (center) → `poster-customize.normal`
- **choose a photo button — open the system photo picker** (lower left) → `photo-picker.photos`
- **Memoji disclosure — open the Memoji poster chooser** (lower left) — *mutates data*

**Variable position:**
- **Memoji poster preset — select it for the draft contact poster** (any poster Memoji preset in the horizontal row) — *mutates data* — *one of many*
- **poster source list — scroll through additional contact-poster sources** (poster source list; drag upward to reveal more source options) → `monogram-editor.poster`

## Poster customize

### Normal mode

A full-screen contact-poster composer with the name treatment, avatar crop, background, color, and font controls.

**Fixed:**
- **cancel button — discard poster customization and return to the poster editor** (upper left)
- **done button — apply the customized poster** (upper right) — *mutates data*
- **name field — edit the name displayed on the poster** (upper center) — *mutates data*
- **avatar preview — reposition or resize the poster's profile image** (center) — *mutates data*
- **background color button — open the poster color palette** (lower left) → `poster-customize.color-menu`
- **poster lettering button — edit the initials displayed on the poster** (lower right) — *mutates data*

**Variable position:**
- **poster preview — browse alternate poster layout treatments** (poster preview; swipe horizontally to browse alternate layouts) → `poster-customize.normal`

### Color menu mode

The contact-poster composer with a bottom Background Color palette open.

**Variable position:**
- **color swatch — select that background for the draft poster** (any color swatch in the Background Color palette) — *one of many*
- **outside palette — dismiss the Background Color palette** (any point above the Background Color palette) → `poster-customize.normal`

## Monogram customize

### Normal mode

The monogram appearance chooser, with initials, typeface, and color controls above a grid of suggested styles.

**Fixed:**
- **cancel button — discard monogram customization and return to the avatar editor** (upper left)
- **choose button — apply the selected monogram style to the profile draft** (upper right) — *mutates data*
- **initials button — edit the monogram text** (middle left) — *mutates data*
- **typeface button — open the font and weight chooser** (center) → `monogram-customize.font-menu`
- **background color button — open the monogram color palette** (middle right) → `monogram-customize.color-menu`

**Variable position:**
- **suggested style — select that appearance for the profile draft** (any suggested monogram style in the grid) — *mutates data* — *one of many*
- **suggestions grid — scroll through more suggested monogram styles** (suggestions grid; drag upward to browse additional styles) → `monogram-customize.normal`

### Font menu mode

The monogram chooser with a Font sheet open, showing typeface samples and a font-weight slider.

**Fixed:**
- **close button — dismiss the Font sheet** (middle right)

**Variable position:**
- **typeface sample — select that font for the draft monogram** (any typeface sample in the Font sheet) — *one of many*
- **font-weight slider — adjust the draft monogram's stroke weight** (font-weight slider near the bottom of the Font sheet)

### Color menu mode

The monogram chooser with a Background Color sheet open over the suggested-style grid.

**Fixed:**
- **close button — dismiss the Background Color sheet** (middle right)

**Variable position:**
- **color swatch — select that background for the draft monogram** (any color swatch in the Background Color sheet) — *one of many*
- **pinned collection tile — open that collection** (any pinned collection tile) → `photo-picker-collection.normal` — *one of many*

## Photo picker collection

A selected photo collection in the system picker; this phone's collection is empty.

**Fixed:**
- **back button — return to the presenting screen** (upper left)
