---
name: craigslist
description: This skill should be used when the user wants to use Craigslist, browse or search local classifieds, filter listings, save searches, favorite or hide postings, reply to listings, manage Craigslist account settings, create posting drafts, or interact with the Craigslist app on their iPhone.
---

# Craigslist — Local Classifieds App

Craigslist is a classifieds app for browsing and posting local listings. Users search by location and category, filter results, save searches, favorite or hide postings, reply to posters, manage account settings, and create posting drafts. This skill teaches Craigslist's UI layout and interaction patterns.

The app was explored on TJ's iPhone. Craigslist commonly uses a dark theme, purple primary actions, and gray/black backgrounds.

**Always take a screenshot after each action to verify what's on screen.** Use visible labels, icons, and spatial relationships rather than memorized tap positions.

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

- Do not send chat, text, email, call, copy contact details, reveal contact rows, or share personal details unless the user explicitly asks.
- Do not enable iOS notifications or open Settings to change notification permissions unless the user asks.
- Do not enter an email address unless the user provides one or explicitly confirms using the configured Mail account.
- Do not set a Craigslist password unless the user explicitly provides one.
- Do not accept or decline Craigslist Terms of Use unless the user explicitly instructs you.
- Stop at posting preview unless the user explicitly asks to publish.
- Stop before payment, phone verification, one-time-code entry, or final publish confirmation unless the user explicitly asks to continue.
- If a flow opens Mail, Messages, Phone, Settings, or a browser, inspect safely and return to Craigslist when done.

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

For exploration, leave alerts off or delete the saved search when done. Queued alert emails can still arrive later even after a test search is deleted.

### Editing And Deleting Saved Searches

From **my searches**, swipe a row left:

- Purple edit button opens the editor.
- Red trash button can delete immediately.

The editor's top-right **delete** action opens a confirmation alert. Verify the **my searches** empty state or expected remaining searches after deleting a test search.

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

To inspect safely, close with **X** and choose **Delete Draft** unless the user wants to keep or send the draft. After sending, Mail may return to an unrelated Mail message; reopen Craigslist if needed.

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

Do not tap **copy**, reveal contact rows, call, text, or email unless the user explicitly wants contact details or contact action. When documenting behavior, describe row types without recording specific phone numbers or email addresses.

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

### Email Gate

Observed first screen:

- Title: **log in or sign up to post**.
- Text: "Please enter your email address to post to craigslist."
- Email field.
- Email keyboard with **next** key.
- Valid email reveals purple **continue** button.

Do not enter an email address unless the user provides one or explicitly confirms using the configured Mail account.

### Confirm Email

After tapping **continue**:

- Title: **confirm email**.
- Message: "Thanks, [email]. How can we make sure this is really you?"
- **send me a link**.
- **log in with my craigslist password**.

If no password is available, use **send me a link**. The next screen tells the user to check email for a login link.

### Mail Handoff

Craigslist login email can arrive in Apple Mail immediately. Sender is Craigslist automated sender, with a main **complete account sign-up** button and secondary **didn't request this link?** link.

Tap **complete account sign-up** only when continuing the requested login. Do not tap **didn't request this link?** unless the user wants to cancel/report signup.

### Password Options

After the email link opens Craigslist:

- Title: **password options**.
- **set password**.
- **skip password**.

Do not set a password unless the user explicitly provides one. If the user wants email-link login, choose **skip password**.

### Terms Of Use Gate

After choosing **skip password**, Craigslist shows **terms of use** with **I ACCEPT** and **I DECLINE**.

This is a hard stop. Do not tap **I ACCEPT** or **I DECLINE** unless the user explicitly instructs you. Accepting legal terms on behalf of a user requires explicit approval.

### Post List After Login

After Terms acceptance, Post becomes a posting manager:

- Title: **post**.
- Top-right **+**.
- Tabs: **drafts**, **active**, **archived**.
- Empty-state text: "press the button below to post on craigslist" and "(swipe down to refresh)".
- Bottom purple **create posting** button.

Draft cards show title, category/type, age, and inline **edit** / **delete**. Deleting a draft opens confirmation: "Are you sure you want to permanently delete this draft?"

## Posting Flow

After login and Terms acceptance, tap **create posting** or top-right **+**.

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

Agents must stop at preview unless the user explicitly asks to publish. Do not tap the top-right **publish** action or the prominent purple **publish** button near the bottom without explicit instruction.

Some categories and locations require payment. Craigslist can require email confirmation from `robot@craigslist.org`, phone verification with a one-time code, and payment for paid categories. Stop before payment submission, verification-code entry, or publish confirmation unless explicitly instructed.

Craigslist warns that requests for personal email addresses, phone numbers, or verification codes may be scams. Never share phone verification codes or personal contact details unless the user explicitly instructs you and the current screen is clearly part of Craigslist's posting flow.

## Account Tab

When logged out, Account begins with an email gate:

- Title: **account**.
- Text: "Please enter your email address to view your account."
- Email field.

After login and Terms acceptance, Account shows:

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
1. open_app("Craigslist") -> screenshot to verify
2. Tap Search if needed
3. Tap categories
4. Select a top-level group on the left
5. Select a subcategory on the right
6. screenshot -> verify result count and visible result cards
```

### Search Listings

```
1. Tap the search craigslist field
2. copy_text_to_phone("query")
3. long_press the search field (about 1500ms) -> tap Paste
4. Choose a suggestion/category result or tap the keyboard search key
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
6. Tap save to create the saved search
7. After exploration, open my searches, swipe the test search left, and delete it
8. screenshot -> verify empty state or intended remaining saved searches
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
7. For email, inspect Mail compose if needed, then close with X -> Delete Draft unless asked to send/save
8. For text, stop at Messages composer unless asked to send
```

### Create A Posting Draft

```
1. Confirm the user is logged in and has accepted Terms of Use themselves
2. Post tab -> create posting or +
3. Choose images or skip images
4. Choose location -> continue
5. Choose type -> choose category
6. Fill required posting details using user-provided information
7. Resolve validation messages
8. Stop at preview unless the user explicitly asks to publish
9. Delete only clearly labeled test drafts created during exploration
```

## Tips And Gotchas

- Result view mode persists across categories. If listings look unexpectedly large, text-only, or image-heavy, use overflow -> **change view**.
- Search suggestions expose category counts before running a search.
- Verify active filter chips because back navigation can restore older search states.
- The same top-right overflow menu controls filters, map mode, view mode, saving, and sharing.
- Category filters differ substantially; re-open **filter & sort** after changing categories.
- Saved-search notification alerts require iOS notification permission. Do not enable notifications or open Settings unless asked.
- Email alerts can be enabled without an iOS notification prompt. Delete test saved searches after exploration.
- Post and account flows require an email address before deeper account/posting features are available.
- Posting details can auto-save as a draft once enough data has been entered. Delete only the test draft you created.
- The bottom trash icon on listing detail hides a posting; use only when the user asks.
- Reply sheets can expose chat, call, text, email, and copy actions. Avoid sending, calling, texting, copying, or storing exact contact details unless explicitly requested.
- The app can jump to iOS Settings from **app permissions**; use the top-left return link to get back to Craigslist.
