---
name: instagram
description: This skill should be used when the user wants to use Instagram, browse the feed, like or comment on posts, watch or create Reels, send direct messages, search for accounts or content, view stories, manage their profile, or interact with the Instagram app on their iPhone.
---

# Instagram — Photo & Video Sharing App

Instagram is a photo/video sharing social media app. Users browse feeds, post photos and Reels, watch stories, send direct messages, and discover content. The interface uses a dark theme with a bottom tab bar for primary navigation. This skill teaches you Instagram's UI layout and interaction patterns.

**Always take a screenshot after each action to verify what's on screen.** Use visual landmarks (text labels, icons, positions like "top-left") rather than memorized coordinates.

## App Structure

### Bottom Tab Bar (5 tabs, always visible at ~y=1280)

| Position | Icon | Approx x | Description |
|----------|------|-----------|-------------|
| 1 (left) | House (filled when active) | ~65 | **Home** — Main feed of posts/reels from followed accounts |
| 2 | Play button | ~190 | **Reels** — Full-screen vertical video feed |
| 3 (center) | Flag/pennant with badge | ~310 | **Direct Messages** — Inbox for private messages |
| 4 | Magnifying glass | ~435 | **Search/Explore** — Discover content and search |
| 5 (right) | Person outline (filled when active) | ~555 | **Profile** — Your profile page |

The active tab's icon appears filled/bold. A red badge with a number on the DM icon indicates unread messages.

---

## Home Tab

### Top Bar (~y=100)
- **"+" button** (top-left, ~x=40): Opens the **Create** flow
- **"Instagram" logo** (center): Decorative branding
- **Heart icon** (top-right, ~x=580): Opens **Activity/Notifications** screen. Red dot when new notifications.

### Stories Row (~y=150-280)
A horizontally scrollable row of circular profile pictures:
- **"Your story"** (leftmost): Your profile pic with a blue "+" overlay to add a new story
- **Friends' stories**: Circular thumbnails with colored ring borders:
  - **Pink/orange gradient ring**: Unseen story
  - **Green ring**: Close Friends story
  - **Gray/no ring**: Already viewed story
- Tap a story circle to open it full-screen. Stories auto-advance.

### Feed Content (~y=320 and below)
Vertically scrolling list. Each post contains:

**Post Header:**
- Profile picture (circular, left) — tap to visit profile
- Username (bold) — verified accounts show blue checkmark
- Three-dot menu "..." (far right, ~x=590) — post options

**Post Media:**
- Full-width image or video. Videos autoplay muted.
- Mute/unmute icon in bottom-right of video content

**Engagement Bar (below media):**
| Icon | Position | Action |
|------|----------|--------|
| Heart | Left | **Like** — tap to like/unlike. Shows count |
| Speech bubble | Second | **Comment** — opens comments |
| Repost arrows | Third | **Reshare** — share to story or send to others |
| Paper plane | Fourth | **Send** — share via DM |
| Bookmark | Far right (~x=580) | **Save** — save to collections |

**Post Details:**
- "Liked by [username] and others" social proof line
- Caption: Username in bold + caption text
- Comment preview with top comment(s)
- Timestamp (relative)

---

## Reels Tab

Full-screen vertical video experience. Each reel takes the entire screen.

### Top Bar
- **"+" button** (top-left): Create a new reel
- **"Reels"** (center, with dropdown arrow)
- **Filter/preferences icon** (top-right): Adjust reel preferences

### Right-Side Engagement Column (~x=575)
| Icon | Description |
|------|-------------|
| Heart + count | Like the reel |
| Comment bubble + count | Open comments |
| Repost arrows + count | Reshare the reel |
| Paper plane + count | Share via DM |

### Bottom Overlay
- **Profile pic + username** (bottom-left): Creator info with Follow button for non-followed accounts
- **Three-dot menu "..."**: Post options menu
- **Caption text**: Truncated with "...more" to expand
- **Audio thumbnail** (bottom-right corner): Tap to explore content using same audio

### Inline Interest Buttons
On suggested content, two buttons may appear:
- **✕ Not interested** — less content like this
- **✓ Interested** — more content like this

### Navigation
- **Swipe up**: Next reel
- **Swipe down**: Previous reel
- **Tap anywhere on video**: Pause/play
- **Long-press**: Pauses only (does NOT open context menu)

### Three-Dot Menu
Opens a bottom sheet with:
- **Top row**: Save, Remix, Sequence
- **Menu items**: View fullscreen, See all remixes (conditional), QR code, Why you're seeing this post, Interested, Not interested, Report, Manage content preferences, See your algorithm

---

## Search/Explore Tab

### Search Bar (top, ~y=105)
- Tap to activate text input and search for accounts, hashtags, places, or content

### Content Grid (below search bar)
- Mosaic/pinterest-style grid of trending content in 3 columns
- Mix of photos and video thumbnails
- Video thumbnails show eye icon + view count
- Tap any thumbnail to open full-screen

---

## Direct Messages Tab

### Top Bar
- **Username** (center, with dropdown arrow)
- **Compose icon** (top-right, pencil in square): Start a new message

### Quick Access Row
- **"Your note"**: Tap to create/edit a Note
- **Map**: Shows friends' shared locations
- **Active contacts**: Profile pics with green dots for online users

### Messages List
- **"Messages" header** with notification bell
- **"Requests" link**: Message requests from non-followers
- Each conversation row: Profile picture, username, last message preview, timestamp, camera icon
- Blue dot indicates unread messages
- Group chats show "Name + Name" format

### Sending a DM

**From a User's Profile:**
1. Tap username/profile pic on a post to visit their profile
2. Tap the **"Message"** button
3. Type and send your message

**From the DM Inbox:**
1. Tap compose icon (pencil, top-right)
2. Search for recipient in "To: Search" field
3. Tap result to select recipient
4. Type and send message

**DM Input Bar (full features for mutual contacts):**
| Element | Description |
|---------|-------------|
| Camera (blue circle) | Take a photo/video to send |
| "Message..." field | Text input |
| Microphone | Record voice message |
| Gallery/Image | Pick from camera roll |
| Sticker/GIF | Browse stickers/GIFs |
| "+" (more) | Location, Draw, AI images, Meta AI |

**Important**: The return key (↵) on the keyboard sends the message — no separate Send button. Cold DMs to non-followers go to their "Requests" folder and have a stripped-down input bar (text only).

---

## Profile Tab

### Top Bar
- **"+" button** (top-left): Create content
- **Username** (center, with dropdown): Switch accounts
- **Hamburger menu "≡"** (top-right): Settings and Activity

### Profile Header
- **Profile picture** with blue "+" for story
- **Stats row**: Posts, Followers, Following counts (all tappable)
- **Display name** and **Bio text**
- **Action buttons**: Edit profile, Share profile, Person+ icon

### Story Highlights (~y=480-570)
Horizontally scrollable saved story highlights

### Content Tabs (~y=640)
| Icon | Description |
|------|-------------|
| Grid (3x3 dots) | **Posts** grid view (default) |
| Play button in square | **Reels** only |
| Person in frame | **Tagged** posts |

### Posts Grid
3-column grid of square thumbnails. Reel posts show play icon in top-right.

---

## Activity/Notifications

Accessed via heart icon on Home tab's top bar.

- Notifications grouped: Highlights, Yesterday, Last 7 days, Last 30 days
- Types: Follow suggestions, new followers, post interactions, comments, channel invites, security alerts

---

## Comments

Tapping the comment bubble opens a bottom sheet:

### Comments Sheet Layout
- **Drag handle** at top
- **AI Search bar** for searching within comments
- **Comments list** sorted by relevance
- **Quick-react emoji row**: ❤️ 🙌 🔥 👏 😢 😍 😮 😂
- **Comment input bar**: "Join the conversation..."

### Writing a Comment
1. `copy_text_to_phone("your comment")`
2. `long_press(x, y, duration: 1500)` on the comment input bar
3. Tap **"Paste"** in the tooltip that appears
4. Tap the **blue send arrow** to post

### Replying to a Comment
1. Tap "Reply" on the comment
2. Input changes to "Replying to [username]" with pre-filled @mention
3. `copy_text_to_phone("your reply")` → `long_press` the input → tap "Paste" → tap blue send arrow
4. Tap "X" to cancel reply mode

### Liking Comments
- Tap heart icon on right side, or double-tap the comment text

### Long-Press Comment Menu
- Reply with a reel, Add to story, Share, Block, Report

---

## Create Flow

Accessed via "+" button on Home or Profile.

- **Photo library grid**: Shows camera roll
- **Content type selector** (bottom pills): POST, STORY, REEL

---

## Settings and Activity

Accessed via hamburger menu (≡) on Profile.

- **Your account**: Accounts Center (Meta)
- **How you use Instagram**: Saved, Archive, Your activity, Notifications, Time management
- **Who can see your content**: Account privacy, Close Friends, Crossposting, Blocked

---

## Key Workflows

### Browse the Feed
```
1. open_app("Instagram") → screenshot to verify
2. Home tab should be selected by default
3. Swipe up from center to scroll down
4. screenshot → verify new posts loaded
```

### Like a Post
```
1. screenshot → find a post and locate its engagement bar
2. Tap the heart icon, or double-tap the post media
3. screenshot → verify heart turned red
```

### Comment on a Post
```
1. Tap the comment bubble icon on a post
2. screenshot → verify comments sheet opened
3. copy_text_to_phone("your comment")
4. long_press on the "Join the conversation..." input bar (duration: 1500)
5. Tap "Paste" in the tooltip
6. Tap the blue send arrow
7. screenshot → verify comment posted
```

### Watch Reels
```
1. Tap the Reels tab (~190, 1280) in bottom nav
2. screenshot → verify reel playing
3. Swipe up to see next reel
4. Tap heart icon (~575) to like
```

### Send a DM
```
1. Tap the DM tab (~310, 1280) in bottom nav
2. Tap compose icon (pencil, top-right)
3. copy_text_to_phone("recipient name") → long_press search field (1500ms) → tap "Paste"
4. Tap the correct result
5. copy_text_to_phone("your message") → long_press the "Message..." input field (1500ms) → tap "Paste"
6. Tap return key to send
7. screenshot → verify message sent
```

### Search for Content
```
1. Tap the Search tab (~435, 1280) in bottom nav
2. copy_text_to_phone("search query")
3. long_press the search bar at top (duration: 1500) → tap "Paste"
4. Results appear in real-time; tap a result
```

### View Your Profile
```
1. Tap the Profile tab (~555, 1280)
2. screenshot → verify profile loaded
3. Browse content tabs: Posts, Reels, Tagged
```

### Post a Story
```
1. Tap "Your story" circle in stories row, or tap "+" > Story
2. Select or capture media
3. Add stickers, text, or effects
4. Tap "Share" to publish
```

## Tips and Gotchas

- **Double-tap likes**: Double-tapping a post's media or a comment text will like it — be careful with accidental double-taps.
- **Long-press on Reels pauses only** — it does NOT open a context menu (unlike feed posts).
- **Return key sends DMs**: The return key on the keyboard sends messages — no separate Send button.
- **Cold DMs go to Requests**: Messages to non-followers land in their Requests folder, not main inbox.
- **Scrolling**: Swipe up to scroll down, swipe down to scroll up.
- **Back navigation**: Back arrow (top-left) or swipe right from left edge.
- **Horizontal swipes navigate between tabs** — be careful near screen edges.
- **App loading**: May take 1-2 seconds after opening or switching tabs.
