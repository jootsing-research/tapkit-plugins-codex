---
name: facebook
description: This skill should be used when the user wants to use Facebook, browse the news feed, like or comment on posts, share stories, use Marketplace to buy or sell items, browse Reels, manage groups, send messages, or interact with the Facebook app on their iPhone.
---

# Facebook — Social Media App

Facebook is a social networking app for sharing posts, photos, and videos, joining groups, buying/selling on Marketplace, and messaging. Users browse feeds, interact with content, manage profiles, and connect with friends. This skill teaches you Facebook's UI layout and interaction patterns.

**Always take a screenshot after each action to verify what's on screen.** Use visual landmarks (text labels, icons, positions like "top-left") rather than memorized coordinates.

## TapKit Setup Reminder

Before acting in this app, follow the core TapKit setup: `list_phones()` -> choose `phone_id` -> `get_phone_status(phone_id)`. All TapKit examples in this skill assume every MCP tool call includes that `phone_id`.

For every text entry, focus the intended field, call `type_text(phone_id, text)`, then take a screenshot and verify the rendered text. Do not tap **Send**, **Post**, **Search**, **Save**, **Confirm**, **Share**, Return, or an equivalent submission control unless the user explicitly authorized that submission and visual verification succeeded.

## Privacy and Data Minimization

Treat screenshots and all visible Facebook account content as private operational context.

- Never surface, quote, summarize, infer, or mention feed posts, profile details, location, family, work, school, contact data, notifications, active contacts, conversation previews, or any other personal data unrelated to the user's exact request.
- Use unrelated content only visually to locate the requested target. Do not transcribe it into reasoning shown to the user or into the final response.
- If the requested post, profile, listing, person, or conversation is ambiguous, stop and ask the user to clarify without enumerating unrelated people, content, or personal details visible on screen.
- Report only the minimum task-relevant result. Never infer a person's identity, relationship, location, workplace, school, family connection, or contact information from surrounding Facebook content.

## App Structure

### Bottom Navigation Bar (6 tabs, always visible)

| Tab | Icon | Purpose |
|-----|------|---------|
| **Home** | House | Main news feed with posts, stories, and sponsored content |
| **Reels** | Play button | Full-screen vertical short-form video feed |
| **Marketplace** | Storefront | Buy/sell items, browse listings, search for jobs |
| **Profile** | Person silhouette | Your profile page — edit info, view your posts |
| **Notifications** | Bell | Friend requests, birthdays, activity alerts |
| **Menu** | Three lines (hamburger) | Access to all Facebook features and settings |

### Top Action Bar (visible on Home screen)

| Icon | Position | Action |
|------|----------|--------|
| **hamburger (three lines)** | Far left | Opens the Menu tab |
| **"facebook" logo** | Left | Scrolls feed to top / returns to Home |
| **+ (Create)** | Center-right | Opens create menu: Post, Story, Reel, Live, AI |
| **Search (magnifying glass)** | Right | Opens search with Meta AI, recent searches, trending topics |
| **Messenger (chat bubble)** | Far right | Opens Chats — shows badge count for unread messages |

---

## Home Feed

The main landing screen when you open Facebook.

Use feed content only within the scope the user requested. Do not describe surrounding posts, authors, stories, reactions, comments, suggested content, or sponsored content merely because they are visible.

**What you see:**
- **Stories row** at top — horizontally scrollable cards showing friends' stories; first card is "Create story" with a + icon
- **News Feed** — scrollable feed of posts from friends, pages you follow, and sponsored content
- **Post components:**
  - Author name, profile photo, timestamp, and audience icon (globe = public, friends icon, etc.)
  - Post text (truncated with "See more" for long posts)
  - Media (photos, videos) — videos have "Watch more" and "Watch again" overlays
  - **Reaction bar**: shows reaction emoji counts and comment count
  - **Action buttons**: Like, Comment, Share
  - **Post menu** (...) and dismiss (X) buttons on each post
- **Sponsored posts** appear in-feed marked with "Sponsored" label

## Reels

A full-screen, TikTok-style vertical video experience.

**What you see:**
- Full-screen video takes up the entire display
- **"Reels"** header at top left
- **Search** and **Profile** icons at top right
- **Right-side action column:**
  - Like (thumbs up) with count
  - Comment (speech bubble) with count
  - Share (arrow) with count
  - Save/Bookmark (flag) with count
  - More (...) menu
- **Creator info** at bottom: profile picture, name, verified badge, Follow button
- Swipe up to see the next reel

## Marketplace

A buy/sell platform integrated into Facebook, localized to your area.

### Marketplace Header

| Icon | Position | Action |
|------|----------|--------|
| **"Marketplace"** | Left (large text) | Page title |
| **Messenger (chat bubble)** | Center-right | Opens Marketplace messages (shows badge count) |
| **You (person silhouette)** | Right | Opens your personal Marketplace hub ("You" page) |
| **Search (magnifying glass)** | Far right | Opens Marketplace-specific search |

### Category Tabs

A horizontal tab bar below the header with 5 options:

| Tab | Default? | Description |
|-----|----------|-------------|
| **Sell** | No | Opens the Selling dashboard — manage listings, view stats, create new listings |
| **For you** | Yes | Personalized feed of recommended listings ("Today's picks") |
| **Local** | No | Listings filtered to nearby items only ("Suggested near you") |
| **Jobs** | No | Local job postings with pay rates, job types, and employer info |
| **More** | No | Full category browser, shortcuts to special features, and saved items |

### "For you" Tab (Default View)

Treat the location indicator, nearby listings, seller identities, maps, and surrounding recommendations as private incidental data unless the user's exact request requires one of them. Never infer or report the user's location from Marketplace UI.

- **"Today's picks"** section header with **location indicator** (blue pin icon + city name — tappable to change location)
- **2-column grid** of listing cards that scroll infinitely
- **Each listing card shows:**
  - Photo thumbnail (large, square)
  - Price (bold) — if the seller has dropped the price, the original price appears with a strikethrough
  - Item title (truncated if long)
  - Optional tags overlaid on the photo: **"Just listed"**, **"Nearby"**

### Listing Detail Page

Tapping any listing card opens a full-screen detail view with:
- Photo carousel (swipeable with page indicator dots)
- Title, price, action icons (Like, Save, Share)
- Message seller button with pre-filled "Is this still available?" text
- Description, seller info with star rating, condition details
- Location map, related items

### Marketplace Search

- Search bar: "What do you want to buy?"
- **Tabs:** Recent | Saved searches
- Results show in **2-column grid** with distance from your location
- **Filters**: Sort by, Price, Delivery, Condition, Date listed, Category, Availability, Brand, Color, Material

## Profile

Your personal Facebook profile page.

Use stable navigation landmarks such as the profile header, **+ Create**, **Edit profile**, and the **All**, **Photos**, and **Reels** tabs. Profiles can expose sensitive personal details and posts; inspect and report only the exact field or content the user requested, and do not infer missing information or relationships from visible context.

## Notifications

The screen has a **Notifications** header with more (...), search, and Messenger controls. Notification rows can reveal names, relationships, events, and activity. Do not enumerate, summarize, or mention any notification outside the exact requested scope; use unrelated rows only as visual landmarks.

## Menu

The central hub for accessing all Facebook features.

- **Your profile card** at top with name and profile switch dropdown
- **Feature grid**: Memories, Saved, Groups, Reels, Marketplace, Friends, Feeds, Dating
- **Expanded features** (via "See more"): Avatars, Birthdays, Chat with AIs, Community Notes, Events, Explore, Fandom, Finds, Games, Messenger Kids, Pages
- **Bottom sections**: Help and support, Settings and privacy, Professional access

## Groups

Accessible via Menu > Groups.

### Groups Tabs
| Tab | Description |
|-----|-------------|
| **For you** | Default — "Your groups" list + "From your groups" post feed |
| **Your groups** | Full list of all joined groups with search and sort |
| **Jump back in** | Masonry grid of posts you've previously interacted with |
| **Posts** | Full-width feed of posts from your groups |
| **Discover** | Suggested groups to join in a 2-column card grid |
| **Manage** | Admin dashboard for groups you manage |

### Individual Group Page
- Cover photo, group name, privacy type, member count
- Action buttons: Joined dropdown, Invite button
- Content tabs: Featured, Reels, You, About, Photos
- Post composer with "Write something..." field
- Group feed with sort options

## Messenger (Chats)

Tapping the Messenger bubble opens the **Chats** screen with settings, compose, search, and filter controls. The screen can expose active contacts, conversation names, message previews, timestamps, and unread state. Never surface any of those details unless they are necessary for the exact requested conversation. Navigate by the requested recipient or conversation only; if multiple results could match, ask for clarification without listing the other people or previews.

## Create Menu (+)

Tapping **+** on the Home screen opens:
- **Post** — Write a text post, attach photos/videos
- **Story** — Create a 24-hour ephemeral story
- **Reel** — Record/edit a short-form video
- **Live** — Start a live video broadcast
- **AI** — Open a conversation with Meta AI

## Key Workflows

### Browse the Feed
```
1. `press_home(phone_id)` → screenshot
2. If **Facebook** is visible, tap it; otherwise, swipe left to the App Library and tap its search field to focus it
3. If using App Library search, call `type_text(phone_id, "Facebook")`
4. If using App Library search, take a screenshot and verify **Facebook** rendered correctly and the intended app result is visible
5. Only if the user explicitly authorized opening Facebook and visual verification succeeded, tap that App Library result
6. screenshot → verify Facebook opened
7. Home tab should be selected by default
8. Swipe up from center of screen to scroll down
9. screenshot → verify new posts loaded
10. Use visible posts only to locate content within the user's requested scope; do not report unrelated posts, people, stories, or recommendations
11. If the target is ambiguous, ask the user to clarify without enumerating the visible alternatives
```

### Like a Post
```
1. screenshot → locate the exact post described by the user without reporting surrounding feed content
2. If more than one post could match, ask the user to clarify without listing unrelated posts or authors
3. Tap the Like button on the unambiguous target
4. screenshot → verify like registered without describing adjacent content
```

### Comment on a Post
```
1. Locate the exact post described by the user; if ambiguous, ask for clarification without listing unrelated posts or authors
2. Tap the Comment button on that post
3. screenshot → verify comment input appeared without describing surrounding comments or profiles
4. Tap the comment field to focus it
5. Call `type_text(phone_id, "your comment")`
6. Take a screenshot and verify the exact comment rendered correctly
7. Only if the user explicitly authorized posting that comment and visual verification succeeded, tap the send button
8. If sent, take a screenshot and verify the comment posted
```

### Share a Story
```
1. Tap + (Create) in the top bar
2. Tap "Story"
3. screenshot → verify story creation screen
4. Select or capture media
5. Only if the user explicitly authorized publishing that exact story and the final preview was visually verified, tap "Share"
```

### Search for Content
```
1. Tap the magnifying glass icon in the top bar
2. Tap the search bar if it is not already focused
3. Call `type_text(phone_id, "search query")`
4. Take a screenshot and verify the intended query rendered correctly
5. Only if the user explicitly authorized running that query and visual verification succeeded, tap "search" on the keyboard
6. If submitted, take a screenshot and verify the results
7. Report only results relevant to the exact query; do not mention unrelated people, profiles, posts, locations, or suggestions
8. If multiple results could be the requested target, ask for clarification without enumerating unrelated results
```

### Inspect a Profile
```
1. Navigate only to the profile explicitly identified by the user
2. screenshot → verify the requested profile without reporting any unrelated profile or feed content
3. Inspect and report only the exact field, post, photo, or setting requested by the user
4. Do not infer or mention location, family, relationships, work, school, or contact data outside that exact scope
5. If the profile or requested field is ambiguous, ask for clarification without enumerating visible people or personal details
```

### Browse Marketplace
```
1. Tap the Marketplace tab in bottom nav
2. screenshot → verify Marketplace loaded without reporting the location indicator, surrounding listings, or seller details
3. Scroll or search only within the item/category scope requested by the user
4. Report only matching listing details needed for the request; do not mention unrelated listings, sellers, profile data, maps, locations, or contact information
5. If multiple listings could be the target, ask for clarification without enumerating unrelated sellers or content
```

### Send a Message
```
1. Tap the Messenger bubble in the top bar
2. Navigate only to the conversation explicitly identified by the user, or tap compose and search for the requested recipient
3. Do not read or report other conversation names, active contacts, message previews, timestamps, or unread state
4. If multiple recipients or conversations could match, stop and ask for clarification without listing the alternatives
5. Tap the message field to focus it
6. Call `type_text(phone_id, "your message")`
7. Take a screenshot and verify the exact recipient and rendered message without reporting unrelated chat content
8. Only if the user explicitly authorized sending that message and visual verification succeeded, tap send
9. If sent, take a screenshot and verify the message was sent without describing other conversations
```

## Tips and Gotchas

- **Sponsored posts** appear in-feed marked with "Sponsored" label — be aware when scrolling.
- **Scrolling**: Swipe up to scroll down, swipe down to scroll up.
- **Back navigation**: Back arrow (top-left) or swipe right from left edge.
- **Dismissing sheets/popups**: Tap dimmed area above, or swipe down on sheet handle.
- **App loading**: May take 1-2 seconds after opening or switching tabs.
- **Keyboard dismissal**: Tap non-interactive area above it.
