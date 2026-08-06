---
name: craigslist
description: This skill should be used when the user wants to use Craigslist, browse or search local classifieds, filter listings, save searches, favorite or hide postings, reply to listings, manage Craigslist account settings, create posting drafts, or interact with the Craigslist app on their iPhone.
---

# Craigslist — Local Classifieds App

Craigslist is a classifieds app for browsing and posting local listings. Users search by location and category, filter results, save searches, favorite or hide postings, reply to posters, manage account settings, and create posting drafts. This skill teaches Craigslist's UI layout and interaction patterns.

**Always take a screenshot after each action to verify what's on screen.** Use visible labels, icons, and spatial relationships rather than memorized tap positions.

## TapKit Setup Reminder

Before acting in this app, follow the core TapKit setup: `list_phones()` -> choose `phone_id` -> `get_phone_status(phone_id)`. All TapKit examples in this skill assume every MCP tool call includes that `phone_id`.

For every text entry, focus the intended field, call `type_text(phone_id, text)`, then take a screenshot and verify the rendered text. Do not tap **Send**, **Post**, **Search**, **Save**, **Confirm**, Return, or an equivalent submission control unless the user explicitly authorized that separate action and visual verification succeeded. Publication has the stricter just-in-time confirmation gate below.

## App Structure

### Bottom Tab Bar

The bottom tab bar is persistent across most screens. The active tab is highlighted in purple.

| Tab | Relative position | Purpose |
|-----|-------------------|---------|
| **Search** | Leftmost tab | Browse categories, search listings, view results, map listings, save searches |
| **Favorites** | Next to Search | View favorited and hidden postings |
| **Post** | Center tab | Start posting flow or manage drafts/active/archived postings |
| **Account** | Next to the rightmost tab | Login, settings, privacy/about, feedback, logout |
| **Feedback / Chat** | Rightmost tab | Logged-out state can show Feedback; logged-in state can show Chat |

### Global Safety Rules

- Do not send chat, text, email, call, copy contact details, or reveal contact rows unless the user explicitly asks for that specific action.
- Mask poster contact information in every model response. Never transcribe, echo, or store a poster's exact phone number, email address, or street address; direct the user to review it on the device instead.
- Do not enable iOS notifications or open Settings to change notification permissions unless the user asks.
- Treat every authentication step as user-only. Stop and hand the device to the user for login, sign-up, account email entry, passwords, authentication links, one-time or verification codes, and account recovery. Do not open authentication email or links, operate those screens, or read, copy, reveal, enter, store, or echo authentication material. Resume only after the user says they completed the flow and Craigslist shows a non-sensitive app screen.
- Treat Terms of Use as user-only. The user must review and tap acceptance or decline controls themselves; never make or execute that decision for them. Resume only after the user completes the Terms screen.
- Never operate payment UI or enter, inspect, summarize, or submit payment information. Hand the device to the user at any fee or payment screen and resume only after the user completes or exits it and a non-sensitive Craigslist screen is visible.
- Always stop at the final posting preview, even when the initial request included publication. Present the final preview summary described below and ask for fresh, just-in-time confirmation before tapping **publish**.
- Leave **publish phone number** and **show address** off by default. Before enabling either, require the user to review the exact value on the device and explicitly confirm that it may be public. Never transcribe that exact value into model output. Reconfirm each disclosure's enabled state in the final preview summary.
- Preserve saved searches and drafts by default. Never delete one merely because it was created during exploration. Before any deletion, identify the exact target and obtain a fresh, just-in-time confirmation for that target.
- If a non-authentication flow opens Mail, Messages, Phone, Settings, or a browser, protect unrelated content and return to Craigslist when done.

## Search Tab

Search is the main app surface. It has two modes: **categories** and **my searches**.

### Header

At the top of the Search tab:

| Element | Purpose |
|---------|---------|
| Craigslist peace-logo | Brand mark on the categories screen |
| **location** selector | Shows current location, such as "San Francisco" |
| **search craigslist** field | Keyword search across selected category/location |
| **categories** tab | Category and subcategory browser |
| **my searches** tab | Saved searches with optional alerts |

### Category Browser

The category browser uses a two-column split view:

- Left column: top-level category groups.
- Right column: subcategories for the selected group.
- Selected category and subcategory appear in bold.
- Tapping a subcategory opens results scoped to that category and current location.

Observed groups and examples:

| Group | Example subcategories |
|-------|-----------------------|
| **community** | Community listings |
| **for sale** | all for sale, antiques, appliances, arts & crafts, auto parts, bicycles, books & magazines, cars & trucks |
| **gigs** | Gig categories |
| **housing** | all housing, apartments / housing for rent, office & commercial, parking & storage, rooms & shares, sublets & temporary, vacation rentals |
| **jobs** | all jobs, accounting/finance, admin/office, architect/engineer/cad, art/media/design, customer service, education/teaching, food/beverage/hospitality, general labor, healthcare |
| **resumes** | Resume postings |
| **services** | Service categories |

### My Searches

The **my searches** tab shows saved searches. Empty state:

- Bookmark icon.
- "my searches".
- "save a search for easy access and optional alerts when new postings match your search".
- "you have no saved searches".

Saved searches are created from results overflow -> **save search**. Rows show the saved name, category/location/radius, and a summary of query and filters. Leading icon meaning:

| Icon | Meaning |
|------|---------|
| Bookmark | Saved search with no alerts |
| Envelope | Email alert enabled |

Tap a saved search to restore that result state. Swipe a row left to expose **edit** and trash actions.

## Searching

Tap **search craigslist** to start keyword search.

### Search Entry Screen

When the field is focused:

- Keyboard appears.
- **cancel** appears to the right of the search field.
- Active **location** and **category** selectors remain visible above the field.
- Recent searches appear when there is no typed query.
- Recent-search rows include category/location/radius plus query/filter summary.
- **clear all** removes recent searches.

After typing a query, Craigslist can show:

- Quoted keyword suggestions, such as `"desk"`.
- Related phrase suggestions, such as `"office desk"`.
- **more suggestions** disclosure.
- **results by category** with counts.

Tapping **more suggestions** expands suggestions and can hide category counts until collapsed or the query changes. Press keyboard **search**, tap a suggestion, or tap a category result to run the search.

## Results

Result pages show:

- Back arrow at top-left.
- Location selector.
- Category selector.
- Search field.
- Overflow menu at top-right.
- Result count.
- Scrollable list/grid/gallery of postings.

Active filters appear as purple chips below the search field, such as **max price: 10**, **for sale by owner**, and **has pic**. Back navigation can restore older result/filter states, so verify visible chips and result count before acting.

### Location Selector

Tapping the location value opens **search location**:

- **X** close action.
- Top-right **apply**.
- Search field: **city or zip/postal code**.
- Apple map with purple circular search radius.
- Current-location arrow.
- Map zoom **+** and **-**.
- Bottom summary with the selected place and search radius.
- Bottom purple **choose this location** button.

Typing a city or ZIP shows suggestions. Closing with **X** discards pending changes. Use **choose this location** or **apply** only when the user wants to change the active search location.

### Category Selector

The category selector opens **select a category** from an active results context. It uses the same two-column browser as the Search tab and opens near the active category. Use **X** to leave the category unchanged.

### Result Card Variants

| View style | What it looks like |
|------------|--------------------|
| **Gallery** | Large image cards; common in housing |
| **Grid** | Two-column image grid; common in for sale |
| **Thumb** | Smaller image rows/cards |
| **List** | Text-only cards; common for jobs or no-image contexts |

For sale cards show photo, title, price, and sometimes neighborhood. Housing cards show neighborhood, title, posting age, price, and image carousel dots. Job cards are mostly text-only with neighborhood/source, title, and posting age.

### Results Overflow Menu

Tap the purple three-line overflow icon at top-right.

| Option | Purpose |
|--------|---------|
| **filter & sort** | Opens category-aware filters |
| **show map** | Toggles map view of listings |
| **change view** | Opens gallery/grid/thumb/list selector |
| **save search** | Saves current search to My Searches |
| **share** | Opens iOS share flow for the search |

### Change View

The change-view sheet is titled **select** and offers **gallery**, **grid**, **thumb**, and **list**. Tap **ok** to keep the selection. Result view mode can persist across categories.

## Map View

Map view is reached from results overflow -> **show map**.

Observed layout:

- Apple Maps-style dark map.
- Purple circular search radius around current location.
- Cluster bubbles showing listing counts, such as `2.5k`, `810`, or `113`.
- **refresh** button in the top-right map area.
- Location-arrow button in the top-right map area.
- Bottom tab bar remains visible.

The results overflow menu remains available. **show map** is checked while map view is active; tapping it again returns to listings.

## Filter And Sort

Filters are category-aware. The top bar has **X**, title **filter & sort**, and top-right **apply**. Sticky bottom buttons show **clear** and **apply**.

### Common Filters

Most categories include:

| Filter | Options |
|--------|---------|
| **sort by** | newest, oldest, distance; for sale/housing can include price low-to-high and high-to-low |
| **use craigslist sub-area** | san francisco, south bay, east bay, peninsula, north bay, santa cruz |
| **posting flags** | has image, posted today, search titles only |
| **duplicates** | hide duplicates or show duplicates, depending on category |

For keyword searches, **relevant** can appear as the default sort. Applying filters returns to results with purple filter chips and an updated count.

### For Sale Filters

Observed for **all for sale**:

- Sort: newest, oldest, price low-to-high, price high-to-low, distance.
- **free** toggle.
- Price min/max.
- **sold by**: all, owner, dealer.
- Make and model search field.
- **condition** disclosure: new, like new, excellent, good, fair, salvage.
- Craigslist sub-area chips.
- Has image, hide duplicates, posted today, search titles only.
- Cryptocurrency ok.
- Delivery available.
- Language of posting disclosure.

### Housing Filters

Observed for **apartments / housing for rent**:

- **by open house date** toggle.
- Sort: newest, oldest, price low-to-high, price high-to-low, distance.
- Price min/max with histogram and average marker.
- Bedrooms min/max.
- Bathrooms min/max.
- Sq ft min/max.
- Amenity chips: air conditioning, cats ok, dogs ok, EV charging, furnished, no application fee, no broker fee, no smoking, wheelchair accessible.
- Rent period, housing type, laundry, and parking disclosures.
- Availability chips: within 30 days, beyond 30 days.
- Craigslist sub-area chips.
- Has image, posted today, search titles only, show duplicates.

### Jobs Filters

Observed for **all jobs**:

- Sort: newest, oldest, distance.
- Internship.
- Non-profit organization.
- Telecommuting ok.
- **employment type** disclosure: full-time, part-time, contract, employee's choice.
- Craigslist sub-area chips.
- Has image, hide duplicates, posted today, search titles only.

## Saved Searches And Alerts

Saved searches are created from results overflow -> **save search**.

The **save search** screen includes:

- Top-left **X**; editing an existing saved search also shows top-right **delete**.
- Title: **save search**.
- **name** field, often prefilled from query.
- **search settings** summary with query, location/radius, category, and filter chips.
- **preview** button.
- **alert me about new results (optional)**.
- **notifications** toggle.
- **email** toggle.
- Bottom purple **save**.

The **preview** button returns to results with a banner such as `previewing saved search "desk"` and a black **save** button. Tapping the banner's **save** returns to the editor.

### Alert Behavior

| Toggle | Behavior |
|--------|----------|
| **notifications** | Can trigger iOS notification permission. If permission is denied, saving with notifications on can show a Craigslist **notifications disabled** alert with **cancel** and **open settings**. |
| **email** | Can be enabled without an iOS permission prompt. Saved-search rows show an envelope icon when email alerts are on. |

For exploration, leave alerts off unless the user asks for them. Preserve the saved search afterward unless the user identifies it for deletion and confirms that exact deletion just before it occurs. Queued alert emails can still arrive after alerts are changed or a search is later deleted.

### Editing And Deleting Saved Searches

From **my searches**, swipe a row left:

- Purple edit button opens the editor.
- Red trash button can delete immediately.

Because the row trash action may delete immediately, do not reveal or tap it until the user has reviewed the exact saved-search name and confirmed deletion of that target. The editor's top-right **delete** action opens an app confirmation alert, but it does not replace the required user confirmation. After an authorized deletion, take a screenshot and verify only the intended row was removed.

## Listing Detail

Tapping a result opens a full-screen detail page.

### Top Bar

| Element | Purpose |
|---------|---------|
| **X** | Close detail and return to results |
| **prev** | Previous result in current result set |
| Result position | Example: `2/25,000+` or `1/897` |
| **next** | Next result |
| **...** | Listing actions |

### Detail Structure

For sale and housing details can show photo carousel, title, posting age/location, category and owner/dealer marker, green price, description, attributes, and embedded map preview.

Job details can show title, company or poster name, posting age and neighborhood, job category, and long description.

Sticky bottom action bar:

- Star: favorite posting.
- **reply** button.
- Trash icon: hide posting.

Use the trash icon only when the user asks to hide a posting.

### Listing Actions Menu

Tap **...** on listing detail.

| Option | Purpose |
|--------|---------|
| **share** | Share listing via iOS share sheet |
| **copy url to clipboard** | Copy listing URL |
| **vote for best-of** | Nominate/vote for Craigslist best-of |
| **flag as prohibited** | Report prohibited content |
| **view on web** | Open listing in a browser/web view |
| **cancel** | Dismiss menu |

## Reply Flow

Tap **reply** only when the user wants to contact the poster or inspect contact options.

The reply sheet is posting-specific. It always includes listing title/header and **cancel**. Observed options:

| Option | Purpose |
|--------|---------|
| **chat** | Opens Craigslist in-app chat composer |
| **call** | Hands off to Phone/call flow |
| **text** | Hands off to Messages with poster number prefilled |
| **email** | Opens Apple Mail compose |
| **view/copy contact info** | Reveals available phone/text/email rows and copy controls |
| **cancel** | Dismiss reply sheet |

Observed variants:

- Job listing: **email**, **view/copy contact info**, **cancel**.
- For-sale item: **chat**, **email**, **view/copy contact info**, **cancel**.
- Service listing: **call**, **email**, **view/copy contact info**, **cancel**.
- Car/truck listing: **chat**, **call**, **text**, **email**, **view/copy contact info**, **cancel**.

### Chat

Tapping **chat** opens an inline Craigslist message composer over listing detail:

- **cancel** on the left.
- Text field placeholder: **new message**.
- Send arrow on the right.
- Keyboard.

Do not type or send a chat message unless the user explicitly asks.

### Email

Tapping **email** opens Apple Mail compose. Recipient and subject are usually prefilled; body is focused and can include the listing URL plus Mail signature. Top-right send arrow sends the message.

Preserve the Mail draft by default. When leaving the composer, save the draft if needed; never choose **Delete Draft** automatically. Before deleting, identify it without exposing the poster's address, such as by its Craigslist listing title, and obtain fresh confirmation for that exact draft. After sending, Mail may return to an unrelated message; do not summarize it, and reopen Craigslist if needed.

Incoming replies can appear in Mail as `craigslist [listing id]` or from a Craigslist relay-domain sender. Search-alert emails can show as **CL Search Alerts**.

When a poster asks for prescreening details, summarize the request for the user and avoid supplying extra personal details without explicit approval.

### Text

Tapping **text** hands off to Messages. First use may show onboarding prompts; dismiss or choose privacy-preserving options unless the user asks to change settings. Messages opens **New Message** with the poster's number prefilled and a blank focused message field.

Do not type or send a text unless the user explicitly asks.

### View / Copy Contact Info

This sheet reveals available contact rows:

- Envelope row for email, sometimes initially **show email**.
- Phone row for call number, sometimes initially **show number**.
- Speech-bubble row for text number.
- Each row can have **copy**.
- Bottom **close** dismisses the panel.

Do not tap **copy**, reveal contact rows, call, text, or email unless the user explicitly wants that specific contact action. Even then, never transcribe, echo, or store the poster's exact phone number, email address, or street address. Refer to the selected contact method generically or in masked form and let the user review exact values on the device.

## Favorites Tab

The Favorites tab has two top tabs:

| Tab | Purpose |
|-----|---------|
| **favorites** | Saved/favorited postings |
| **hidden** | Postings hidden with the trash icon |

Observed empty states:

- "You have no favorited postings."
- "You have no hidden postings."
- **retry** button.

## Post Tab

The Post tab opens a login/sign-up gate when logged out.

### Authentication And Terms Gates

When Craigslist shows a login, sign-up, password, authentication-link, code, account-recovery, or Terms screen, stop immediately and hand the device to the user. Do not type an account email, choose an authentication method, open Mail or a browser for a login link, enter a password or code, create an account, or tap an acceptance or decline control. Do not inspect or report the user's credentials or authentication material.

Resume only after the user confirms they completed or exited the entire user-only flow and a screenshot shows a non-sensitive Craigslist screen. Do not take or relay screenshots while credentials, codes, authentication links, payment information, or other secrets are visible.

### Post List After User-Completed Login

After the user completes any required authentication and Terms decisions, Post becomes a posting manager:

- Title: **post**.
- Top-right **+**.
- Tabs: **drafts**, **active**, **archived**.
- Empty-state text: "press the button below to post on craigslist" and "(swipe down to refresh)".
- Bottom purple **create posting** button.

Draft cards show title, category/type, age, and inline **edit** / **delete**. Preserve drafts by default. Before tapping **delete**, show the user the exact draft title/category target and obtain fresh confirmation for that target; the app's own confirmation alert does not replace this gate.

## Posting Flow

After the user completes any required authentication and Terms decisions, tap **create posting** or top-right **+**.

1. **choose images**: top-right **skip**, image library, camera, "include up to 24 images", bottom **skip images** / **continue**.
2. **choose location**: Apple map, pin, search icon, location-arrow, selected place label, top-right and bottom **continue**.
3. **choose type**: job offered, gig offered, resume / job wanted, housing offered, housing wanted, for sale by owner/dealer, wanted by owner/dealer, service offered, community, event / class.
4. **choose category**: category list depends on type; for sale by owner includes antiques, appliances, arts & crafts, auto parts, bicycles, boats, and more. Header includes prohibited list, recall information, and avoiding scams links.
5. **posting details**: required title, price, area chips, city/neighborhood, required description, optional details, condition chips, language, reply options, and location info.
6. **preview**: title **preview**, top-right **publish**, buttons **edit post**, **edit location**, **edit images**, and a prominent purple **publish** button near the bottom.

Posting details for for-sale-by-owner can include:

- Price field prefixed with `$`.
- Area chips: city of san francisco, south bay area, east bay area, peninsula, north bay / marin, santa cruz co.
- City or neighborhood, often prefilled from location.
- Make / manufacturer and model name / number.
- Condition chips: new, like new, excellent, good, fair, salvage.
- Options: cryptocurrency ok, delivery available, include "more ads by this user" link.
- Reply options with CL mail relay and CL chat checked by default, plus unchecked publish phone number.
- Location info with unchecked show address option.

Keep **publish phone number** and **show address** unchecked unless the user reviews the exact value on the device and explicitly confirms that specific public disclosure. Do not reproduce the value in model output. If either option is enabled, verify its state again at preview and call it out without exposing the underlying value.

### Posting Validation

Continuing without required fields returns to the top and shows a red validation summary, such as:

- "Some required information is missing or incorrect. Please correct the fields marked in red:"
- "All postings must have a title."
- Title field marked red with "This field is required."

If price is blank in a for-sale flow, Craigslist can open **is it free**:

- "You did not enter a price. Please select an option or go back to add a price."
- **The item is free**.
- **Price is negotiable**.
- **I just don't want to show a price**.
- Bottom **go back** and **continue**.

### Publishing, Fees, And Verification

Always stop at preview, including when the user's initial request said to publish. Verify the preview on-screen, then present a concise final preview summary containing:

- title, posting type/category, price or free/negotiable state, and non-sensitive city/area;
- image count and material listing details;
- enabled reply methods;
- whether **publish phone number** and **show address** are on or off, without transcribing either value;
- any visible fee, validation, or verification requirement.

Ask for fresh, just-in-time confirmation to publish that summarized version. Upfront authorization is not sufficient. Tap **publish** only after the user's reply confirms this exact preview. If the preview changes, repeat the summary and confirmation gate.

If phone or address disclosure is enabled, publication also requires the user to confirm they reviewed the exact on-device value and still approve making it public. If that confirmation is absent or ambiguous, leave the option off and do not publish.

Some categories and locations require authentication, phone verification, or payment. Every such step is user-only: hand over the device without opening links, reading or entering codes, or operating payment controls. Resume only after the user completes or exits the step and a non-sensitive Craigslist screen is visible. If the flow returns to an editable preview, repeat the final summary and obtain a new just-in-time publish confirmation.

## Account Tab

When logged out, Account begins with an authentication gate. Apply the user-only authentication and Terms boundary above; do not enter account information or operate that flow.

After the user completes any required login and Terms decisions, Account shows:

| Row | Purpose |
|-----|---------|
| **manage postings** | Opens posting manager |
| **settings** | App configuration |
| **feedback** | Feedback form |
| **privacy** | Privacy information |
| **about** | App info, legal links, version |
| **log out** | Ends Craigslist app account session |

### Settings

Observed settings rows:

| Setting | Behavior |
|---------|----------|
| **app permissions** | Opens iOS Settings for Craigslist |
| **dark mode options** | always dark, always light, use system setting |
| **default location** | Opens map/location picker |
| **select email app** | Choose email app; default Mail observed |

### About

About shows Craigslist branding, legal links, version, and help ID. Observed links: terms of use, privacy policy, third party code licenses. Observed version: `1.27.0-20260106-122639-7feb1f8`.

## Feedback Tab

Feedback shows:

- Title: **feedback**.
- Large text area with placeholder **tell us what you think**.
- **submit** button disabled until text is entered.

## Chat Tab

When logged in, the bottom-right tab can show **chat** instead of Feedback.

Observed layout:

- Title: **chat**.
- Back arrow at top-left.
- Search icon at top-right.
- Tabs: **active** and **hidden**.
- Notifications banner: **notifications off**.
- Banner actions: **dismiss** and **turn on notifications**.
- Empty state: **no conversations**.

Do not turn on notifications, search conversations, hide conversations, or send chat messages unless the user asks.

## Key Workflows

### Browse A Category

```
1. `press_home(phone_id)` -> screenshot
2. If **Craigslist** is visible, tap it; otherwise, swipe left to the App Library and tap its search field to focus it
3. If using App Library search, call `type_text(phone_id, "Craigslist")`
4. If using App Library search, take a screenshot and verify **Craigslist** rendered correctly and the intended app result is visible
5. Only if the user explicitly authorized opening Craigslist and visual verification succeeded, tap that App Library result
6. screenshot -> verify Craigslist opened
7. Tap Search if needed
8. Tap categories
9. Select a top-level group on the left
10. Select a subcategory on the right
11. screenshot -> verify result count and visible result cards
```

### Search Listings

```
1. Tap the search craigslist field to focus it
2. Call `type_text(phone_id, "query")`
3. Take a screenshot and verify the intended query rendered correctly
4. Only if the user explicitly authorized running that query and visual verification succeeded, choose a suggestion/category result or tap the keyboard search key
5. screenshot -> verify result count, active category, location, and filter chips
```

### Filter Results

```
1. Open a result page
2. Tap top-right overflow menu
3. Tap filter & sort
4. Choose filters or enter min/max values
5. Tap apply
6. screenshot -> verify result count and active purple filter chips
```

### Save A Search Safely

```
1. Configure search, category, location, and filters
2. Tap results overflow -> save search
3. Review name and search settings
4. Leave notifications and email off unless the user wants alerts
5. Tap preview if needed to verify saved result state
6. Only if the user explicitly authorized saving this search and the preview was visually verified, tap save to create it
7. Preserve the saved search after exploration by default
8. If the user asks to delete one, show its exact name/settings, obtain fresh confirmation for that target, delete only it, and take a screenshot to verify the intended row was removed
```

### Use Map View

```
1. Open a result page
2. Tap overflow -> show map
3. Use cluster bubbles, refresh, or location arrow as needed
4. Tap overflow -> show map again to return to listings
5. screenshot -> verify expected view
```

### Open And Respond To A Listing

```
1. Tap a result card
2. Review title, price/category/posting metadata, description, attributes, and map
3. Use prev/next to move through results if needed
4. Tap reply only when the user wants contact action
5. Choose chat, call, text, email, or view/copy contact info only with explicit user intent
6. For chat, stop at the new message composer unless asked to send
7. For email, preserve the Mail draft by default; never choose Delete Draft without fresh confirmation for that exact draft
8. For text, stop at Messages composer unless asked to send
9. In every model response, mask poster contact information and never transcribe an exact phone number, email address, or street address
```

### Create A Posting Draft

```
1. If authentication or Terms appears, stop and let the user complete the entire flow themselves; resume only on a non-sensitive Craigslist screen
2. Post tab -> create posting or +
3. Choose images or skip images
4. Choose location -> continue
5. Choose type -> choose category
6. Fill required posting details using user-provided information
7. Resolve validation messages
8. Leave publish phone number and show address off unless the user reviews the exact on-device value and explicitly confirms that public disclosure
9. Always stop at preview, present the final preview summary, and obtain fresh confirmation for that exact version before publish
10. Hand every authentication, verification, code, and payment screen to the user; never operate it
11. Preserve the draft by default; delete it only after fresh confirmation of its exact title/category target
```

## Tips And Gotchas

- Result view mode persists across categories. If listings look unexpectedly large, text-only, or image-heavy, use overflow -> **change view**.
- Search suggestions expose category counts before running a search.
- Verify active filter chips because back navigation can restore older search states.
- The same top-right overflow menu controls filters, map mode, view mode, saving, and sharing.
- Category filters differ substantially; re-open **filter & sort** after changing categories.
- Saved-search notification alerts require iOS notification permission. Do not enable notifications or open Settings unless asked.
- Email alerts can be enabled without an iOS notification prompt. Preserve test and exploratory saved searches unless the user confirms deletion of an exact target.
- Post and account flows can require authentication before deeper features are available. Hand the entire authentication and Terms flow to the user.
- Posting details can auto-save as a draft once enough data has been entered. Preserve it unless the user confirms deletion of that exact draft.
- The bottom trash icon on listing detail hides a posting; use only when the user asks.
- Reply sheets can expose chat, call, text, email, and copy actions. Take only the requested contact action, and always mask poster contact information in model output; never transcribe or store an exact phone number, email address, or street address.
- The app can jump to iOS Settings from **app permissions**; use the top-left return link to get back to Craigslist.
