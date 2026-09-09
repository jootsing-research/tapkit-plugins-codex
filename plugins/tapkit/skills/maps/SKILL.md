---
name: maps
description: Layout and navigation of the Maps iPhone app — its screens, modes, and where every control is located. Use when operating Maps and you cannot find a control or a screen.
---

# Maps app UI map

Positions describe equal thirds of the screen in a 3×3 grid: upper left, upper center, upper right; middle left, center, middle right; lower left, lower center, lower right. Elements under **Fixed** — bars, popups, sheets — sit in the listed region whenever the mode is shown. Locate the described control visually within that region before tapping. Elements under **Variable position** move with scrolling content; scroll to reveal them.

## Notifications onboarding

### Location alert mode

The Maps notifications onboarding page is dimmed behind a system alert asking to turn on Location Services for Maps.

**Fixed:**
- **settings button — would leave Maps to change the persistent Location Services setting** (middle left) — *mutates data*
- **cancel button — dismiss the Location Services alert without changing authorization** (middle right) → `notifications-onboarding.normal`

### Normal mode

The Maps onboarding page explains that notifications provide turn-by-turn directions, shared ETAs, and report updates.

**Fixed:**
- **enable notifications button — would request or change persistent notification authorization** (lower center) — *mutates data*
- **not now button — continue without changing notification authorization** (lower center) → `ads-onboarding.normal`

## Ads onboarding

A privacy notice explains that Maps may show local ads based on approximate location, searches, or the visible map, without linking advertising information to the Apple Account.

**Fixed:**
- **about Apple Advertising and Privacy link — attempt to open Apple's explanatory privacy page; the onboarding page remained visible on this phone** (lower center)
- **continue button — acknowledge the advertising privacy notice and continue** (lower center) → `map.normal`

## Map

### Normal mode

The main Maps globe view with Location Services off and a partially expanded bottom sheet containing search, account access, saved Places, and Guides.

**Fixed:**
- **Location Services is Off banner — would offer a path to change persistent Location Services authorization** (upper center) — *mutates data*
- **map canvas — pan the globe without changing user data** (upper center)
- **map options button — open map type and display controls** (middle right) → `map.map-modes`
- **current location button — ask Maps to locate the device; blocked because Location Services is off** (middle right) — *mutates data*
- **sheet handle — drag to resize the Maps bottom sheet** (center)
- **search field — enter destination and place queries** (middle left) → `map-search.normal`
- **voice search button — would request microphone authorization and begin voice input** (middle right) — *mutates data*
- **account button — open account, favorites, guides, and Maps settings** (middle right) → `map.account`
- **Places disclosure — expand or collapse saved place shortcuts** (lower left)
- **add Home button — would save a Home address** (lower left) — *mutates data*
- **add Work button — would save a Work address** (lower center) — *mutates data*
- **add place button — would add a saved place** (lower center) — *mutates data*
- **Your Guides disclosure — open the guides collection** (lower left)

**Variable position:**
- **guide card — open a curated guide** (any guide card in the horizontal carousel; moves as the sheet scrolls) — *one of many*

### Map modes mode

A Map Modes sheet overlays the globe and offers Explore, Driving, Transit, and Satellite presentation choices; the selected choice has a blue outline.

**Fixed:**
- **close button — dismiss Map Modes and return to the main map** (lower right) → `map.normal`
- **Explore map mode button — show the standard detailed map** (lower left)
- **Driving map mode button — emphasize road conditions and driving information** (lower center)
- **Transit map mode button — emphasize public-transit routes** (lower center)
- **Satellite map mode button — show satellite imagery** (lower right) → `map.satellite-modes`

### Satellite modes mode

The Map Modes sheet with Satellite selected expands to include Traffic and Labels display toggles; these persistent presentation settings are left unchanged.

**Fixed:**
- **close button — dismiss Map Modes and return to the main satellite map** (middle right) → `map.normal`
- **Explore map mode button — return to the standard detailed map** (lower left) → `map.map-modes`
- **Driving map mode button — emphasize road conditions and driving information** (lower center) → `map.map-modes`
- **Transit map mode button — emphasize public-transit routes** (lower center) → `map.map-modes`
- **Satellite map mode button — keep satellite imagery selected** (lower right)
- **Traffic toggle — would change the persistent satellite traffic overlay setting** (lower right) — *mutates data*
- **Labels toggle — would change the persistent satellite labels setting** (lower right) — *mutates data*

### Account mode

An account sheet overlays the map with sign-in, Places, Reports, Offline Maps, and Preferences rows.

**Fixed:**
- **close button — dismiss the account sheet** (middle right) → `map.normal`
- **Apple Account sign-in button — would begin authentication and change account state** (center) — *mutates data*
- **Places row — open saved places** (lower center) → `places.normal`
- **Reports row — open submitted Maps reports** (lower center) → `reports.normal`
- **Offline Maps row — open downloaded-map management** (lower center) → `offline-maps.normal`
- **Preferences row — open Maps navigation and route preferences** (lower center) → `preferences.normal`

## Places

The Places sheet summarizes Pinned, Saved Places, Guides, and Routes, all empty on this phone, with an empty Recently Added section.

**Fixed:**
- **close button — dismiss Places and return to the map** (upper right) → `map.normal`
- **Pinned row — open pinned places** (upper center) → `pinned.normal`
- **Saved Places row — open saved places** (upper center) → `saved-places.normal`
- **Guides row — open personal guides** (center) → `guides.normal`
- **Routes row — open saved routes** (center) → `routes.normal`

## Pinned

### Normal mode

The Pinned sheet offers empty Home and Work shortcuts plus a Siri suggestion for Nearby Transit.

**Fixed:**
- **close button — dismiss Pinned and return to the map** (upper right) → `map.normal`
- **add Home row — would save a Home address** (upper left) — *mutates data*
- **add Work row — would save a Work address** (upper left) — *mutates data*
- **Nearby Transit suggestion row — unexpectedly promoted the suggestion into Pinned when tapped; avoid during safe mapping** (center) → `pinned.nearby-transit-pinned` — *mutates data*
- **pin Nearby Transit button — would add the suggestion to Pinned** (middle right) — *mutates data*
- **add pinned place button — would create a new pinned place** (lower center) — *mutates data*
- **edit pinned places button — enter editing; used only to undo an unintended Nearby Transit pin** (lower center) → `pinned.edit`

### Edit mode

Pinned editing mode shows removal controls for Home, Work, and the accidentally pinned Nearby Transit item, reorder handles, and a completion checkmark.

**Fixed:**
- **remove Home button — would remove the Home shortcut** (upper left) — *mutates data*
- **remove Work button — would remove the Work shortcut** (upper left) — *mutates data*
- **remove Nearby Transit button — remove the accidentally pinned suggestion to restore the initial state** (middle left) — *mutates data*
- **Nearby Transit reorder handle — would change pinned-item order** (middle right) — *mutates data*
- **done button — commit the restoration and exit editing** (lower right) — *mutates data*

### Nearby transit pinned mode

Pinned after the Nearby Transit suggestion was unexpectedly promoted into the main list; this transient state is immediately reverted.

**Fixed:**
- **close button — dismiss Pinned and return to the map** (upper right) → `map.normal`
- **add Home row — would save a Home address** (upper left) — *mutates data*
- **add Work row — would save a Work address** (upper left) — *mutates data*
- **Nearby Transit pinned row — open nearby departure options** (center)
- **add pinned place button — would create a new pinned place** (lower center) — *mutates data*
- **edit pinned places button — enter editing to undo the unintended pin** (lower center) → `pinned.edit`

## Map search

### Normal mode

The expanded Maps search sheet has the keyboard focused, a natural-language search tip, and nearby category shortcuts.

**Fixed:**
- **focused search field — type a destination or place query** (upper center) → `map-search.query-location-alert`
- **voice search button — would request microphone authorization and begin voice input** (upper right) — *mutates data*
- **close button — cancel search and return to the main map** (upper right) → `map.normal`
- **dismiss search tip button — would persistently dismiss the natural-language search tip** (upper right) — *mutates data*

**Variable position:**
- **nearby category row — run a category search; not exercised because Location Services is off** (any Find Nearby category row, such as Gas Stations or Breakfast; moves as the sheet scrolls) — *one of many*

### Query location alert mode

A live text query has produced suggestions, but a Location Services system alert blocks the search sheet because location is off.

**Fixed:**
- **settings button — would leave Maps to change persistent Location Services authorization** (middle left) — *mutates data*
- **cancel button — dismiss the location alert without changing authorization** (middle right) → `map-search.query`

### Query mode

The focused search sheet contains a partial query and live suggestions while Location Services remains off.

**Fixed:**
- **query field — edit the current search text** (upper center)
- **clear query button — clear the current search text** (upper right) → `map-search.normal`
- **close button — cancel search and return to the main map** (upper right) → `map.normal`
- **keyboard search button — submit the rendered query; not used because live suggestions already triggered the location alert** (lower right)

**Variable position:**
- **search suggestion row — open a matching place or region; not exercised because location is unavailable** (any live search suggestion row; moves with results) — *one of many*

## Saved places

An empty Saved Places sheet invites the user to add a place.

**Fixed:**
- **close button — dismiss Saved Places and return to Places** (upper right)
- **add a place button — would create a saved place** (center) — *mutates data*

## Guides

### Normal mode

The Guides sheet contains an empty Favorites guide and controls to create or select guides.

**Fixed:**
- **close button — dismiss Guides and return to Places** (upper right)
- **Favorites guide row — open the Favorites guide** (upper center) → `favorite-guide.normal`
- **add guide button — would create a new guide** (lower center) — *mutates data*
- **select guides button — enter guide selection mode** (lower center) → `guides.select`

### Select mode

Guide selection mode for choosing guides to edit or delete; Favorites is the only guide and no selection is made.

**Fixed:**
- **Favorites guide selection row — tapping the protected Favorites guide did not select it on this phone** (upper center)
- **delete selected guides button — disabled until a guide is selected; would delete selected guides** (lower left) — *mutates data*
- **done button — exit guide selection mode** (lower right) → `guides.normal`

## Favorite guide

The empty Favorites guide appears as a bottom sheet over the globe and invites adding places.

**Fixed:**
- **close button — dismiss the Favorites guide** (middle right)
- **sheet handle — drag to resize the Favorites guide sheet** (center)
- **add place button — would add a place to Favorites** (lower right) — *mutates data*

## Routes

An empty Routes sheet explains custom walking routes and offers route creation.

**Fixed:**
- **close button — dismiss Routes and return to Places** (upper right)
- **create route button — would begin creating and saving a custom route** (lower center) — *mutates data*

## Reports

An empty Reports sheet explains that submitted street, place, and route issues would appear here.

**Fixed:**
- **close button — dismiss Reports and return to the account sheet** (upper right)
- **report a new issue button — would begin submitting a Maps report** (lower center) — *mutates data*

## Offline maps

An empty Offline Maps sheet explains offline routing and offers downloading a new map.

**Fixed:**
- **close button — dismiss Offline Maps and return to the account sheet** (upper right)
- **download new map button — would choose and download an offline region** (center) — *mutates data*

## Preferences

### Normal mode

Maps Preferences with Driving selected and persistent route-avoidance settings for driving, walking, and cycling; settings are recorded but not changed.

**Fixed:**
- **close button — dismiss Preferences and return to the account sheet** (upper right)
- **Driving directions preference — currently selected; would change the persistent preferred travel mode** (upper center) — *mutates data*
- **Walking directions preference — would change the persistent preferred travel mode** (upper center) — *mutates data*
- **Transit directions preference — would change the persistent preferred travel mode** (center) — *mutates data*
- **Cycling directions preference — would change the persistent preferred travel mode** (center) — *mutates data*
- **Avoid Tolls toggle — would change a persistent driving preference** (middle right) — *mutates data*
- **Avoid Highways toggle — would change a persistent driving preference** (middle right) — *mutates data*
- **walking Avoid Hills toggle — would change a persistent walking preference** (lower right) — *mutates data*
- **Avoid Busy Roads toggle — would change a persistent walking preference** (lower right) — *mutates data*
- **Avoid Stairs toggle — would change a persistent walking preference** (lower right) — *mutates data*
- **cycling Avoid Hills toggle — would change a persistent cycling preference** (lower right) — *mutates data*
- **preferences list — scroll to additional settings without changing them** (lower center) → `preferences.scrolled`

### Scrolled mode

Preferences scrolled to show cycling Avoid Busy Roads and persistent transit-mode choices in addition to the route-avoidance toggles.

**Fixed:**
- **close button — dismiss Preferences and return to the account sheet** (upper right)
- **Avoid Tolls toggle — would change a persistent driving preference** (upper right) — *mutates data*
- **Avoid Highways toggle — would change a persistent driving preference** (upper right) — *mutates data*
- **walking Avoid Hills toggle — would change a persistent walking preference** (middle right) — *mutates data*
- **Avoid Busy Roads toggle — would change a persistent walking preference** (middle right) — *mutates data*
- **Avoid Stairs toggle — would change a persistent walking preference** (middle right) — *mutates data*
- **cycling Avoid Hills toggle — would change a persistent cycling preference** (middle right) — *mutates data*
- **cycling Avoid Busy Roads toggle — would change a persistent cycling preference** (lower right) — *mutates data*
- **Bus transit preference — currently enabled; would change persistent transit-mode filtering** (lower center) — *mutates data*
- **Subway and Light Rail transit preference — currently enabled; would change persistent transit-mode filtering** (lower center) — *mutates data*
- **Commuter Rail transit preference — currently enabled; would change persistent transit-mode filtering** (lower center) — *mutates data*
- **Ferry transit preference — currently enabled; would change persistent transit-mode filtering** (lower center) — *mutates data*
