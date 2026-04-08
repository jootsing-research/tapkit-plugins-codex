---
name: facebook
description: This skill should be used when the user wants to use Facebook, browse the news feed, like or comment on posts, share stories, use Marketplace to buy or sell items, browse Reels, manage groups, send messages, or interact with the Facebook app on their iPhone.
---

# Facebook — Social Media App

Facebook is a social networking app for sharing posts, photos, and videos, joining groups, buying/selling on Marketplace, and messaging. Users browse feeds, interact with content, manage profiles, and connect with friends. This skill teaches you Facebook's UI layout and interaction patterns.

**Always take a screenshot after each action to verify what's on screen.** Use visual landmarks (text labels, icons, positions like "top-left") rather than memorized coordinates.

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

**What you see:**
- **Cover photo** with camera icon to change it
- **Profile photo** with camera icon overlay
- **Name**, friend count, post count
- **Bio line**: location, workplace, school
- **Action buttons**: + Create, Edit profile
- **Content tabs**: All, Photos, Reels
- **Personal details section**: Location, Hometown, Relationship status, Family, Gender
- **Work section**: Job history with titles and dates
- **Education section**: Schools with class years

## Notifications

All alerts and activity related to your account.

- **Header**: "Notifications" with more (...), search, and Messenger icons
- **Friend requests** section at top with Confirm/Delete buttons and "See all"
- **Time-grouped notifications**: Today, Earlier
- **Notification types**: Birthday reminders, event announcements, group activity, comments, likes

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

Tapping the Messenger bubble opens the Chats screen:
- **Header**: "Chats" with settings gear and compose icons
- **Search bar** for finding conversations
- **Active contacts row**: Horizontally scrollable avatars with green dot for online
- **Filter tabs**: Inbox, Communities, Requests, Spam
- **Chat list**: Conversations with preview text, timestamps, unread indicators

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
1. open_app("Facebook") → screenshot to verify
2. Home tab should be selected by default
3. Swipe up from center of screen to scroll down
4. screenshot → verify new posts loaded
```

### Like a Post
```
1. screenshot → find a post and locate its action buttons
2. Tap the Like button
3. screenshot → verify like registered
```

### Comment on a Post
```
1. Tap the Comment button on a post
2. screenshot → verify comment input appeared
3. copy_text_to_phone("your comment")
4. long_press on the comment field (duration: 1500) → tap "Paste" in the tooltip
5. Tap the send button
6. screenshot → verify comment posted
```

### Share a Story
```
1. Tap + (Create) in the top bar
2. Tap "Story"
3. screenshot → verify story creation screen
4. Select or capture media
5. Tap "Share" to publish
```

### Search for Content
```
1. Tap the magnifying glass icon in the top bar
2. copy_text_to_phone("search query")
3. long_press on the search bar (duration: 1500) → tap "Paste" in the tooltip
4. Tap "search" on keyboard
5. screenshot → verify results
```

### Browse Marketplace
```
1. Tap the Marketplace tab in bottom nav
2. screenshot → verify Marketplace loaded with "Today's picks"
3. Scroll to browse listings, or tap Search to find specific items
```

### Send a Message
```
1. Tap the Messenger bubble in the top bar
2. Tap a conversation or tap compose for new message
3. copy_text_to_phone("your message")
4. long_press on the message field (duration: 1500) → tap "Paste" in the tooltip
5. Tap send
6. screenshot → verify message sent
```

## Tips and Gotchas

- **Sponsored posts** appear in-feed marked with "Sponsored" label — be aware when scrolling.
- **Scrolling**: Swipe up to scroll down, swipe down to scroll up.
- **Back navigation**: Back arrow (top-left) or swipe right from left edge.
- **Dismissing sheets/popups**: Tap dimmed area above, or swipe down on sheet handle.
- **App loading**: May take 1-2 seconds after opening or switching tabs.
- **Keyboard dismissal**: Tap non-interactive area above it.
