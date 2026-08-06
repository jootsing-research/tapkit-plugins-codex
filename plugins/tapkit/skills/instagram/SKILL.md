---
name: instagram
description: This skill should be used when the user wants to use Instagram, browse the feed, like or comment on posts, watch or create Reels, send direct messages, search for accounts or content, view stories, manage their profile, or interact with the Instagram app on their iPhone.
---

# Instagram — Photo & Video Sharing App

Instagram is a photo/video sharing social media app. Users browse feeds, post photos and Reels, watch stories, send direct messages, and discover content. The interface uses a dark theme with a bottom tab bar for primary navigation. This skill teaches you Instagram's UI layout and interaction patterns.

**Always take a screenshot after each action to verify what's on screen.** Use visual landmarks (text labels, icons, positions like "top-left") rather than memorized tap locations.

## TapKit Setup Reminder

Before acting in this app, follow the core TapKit setup: `list_phones()` -> choose `phone_id` -> `get_phone_status(phone_id)`. All TapKit examples in this skill assume every MCP tool call includes that `phone_id`.

For every text entry, focus the intended field, call `type_text(phone_id, text)`, then take a screenshot and verify the rendered text. Do not tap **Send**, **Post**, **Search**, **Save**, **Confirm**, **Share**, Return, or an equivalent submission control unless the user explicitly authorized that submission and visual verification succeeded.

Treat the photo library as user-controlled private data. Never open, scroll, search, or inspect the library beyond the exact asset the user selected. If an asset has not already been selected, hand control to the user to choose it; resume only after Instagram returns to the selected asset's preview. Inspect only that preview, not adjacent thumbnails, other assets, filenames, dates, locations, or metadata.

## App Structure

### Bottom Tab Bar (5 tabs, always visible at the bottom)

| Position | Icon | Description |
|----------|------|-------------|
| 1 (left) | House (filled when active) | **Home** — Main feed of posts/reels from followed accounts |
| 2 | Play button | **Reels** — Full-screen vertical video feed |
| 3 (center) | Flag/pennant with badge | **Direct Messages** — Inbox for private messages |
| 4 | Magnifying glass | **Search/Explore** — Discover content and search |
| 5 (right) | Person outline (filled when active) | **Profile** — Your profile page |

The active tab's icon appears filled/bold. A red badge with a number on the DM icon indicates unread messages.

---

## Home Tab

### Top Bar
- **"+" button** (top-left): Opens the **Create** flow
- **"Instagram" logo** (center): Decorative branding
- **Heart icon** (top-right): Opens **Activity/Notifications** screen. Red dot when new notifications.

### Stories Row
A horizontally scrollable row of circular profile pictures:
- **"Your story"** (leftmost): Your profile pic with a blue "+" overlay to add a new story
- **Friends' stories**: Circular thumbnails with colored ring borders:
  - **Pink/orange gradient ring**: Unseen story
  - **Green ring**: Close Friends story
  - **Gray/no ring**: Already viewed story
- Tap a story circle to open it full-screen. Stories auto-advance.

### Feed Content
Vertically scrolling list. Each post contains:

**Post Header:**
- Profile picture (circular, left) — tap to visit profile
- Username (bold) — verified accounts show blue checkmark
- Three-dot menu "..." (far right) — post options

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
| Bookmark | Far right | **Save** — save to collections |

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

### Right-Side Engagement Column
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

### Search Bar (top)
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
3. Tap the message field to focus it
4. Call `type_text(phone_id, "your message")`
5. Take a screenshot and verify the exact message rendered correctly
6. Only if the user explicitly authorized sending that message and visual verification succeeded, tap Return

**From the DM Inbox:**
1. Tap compose icon (pencil, top-right)
2. Tap the "To: Search" field to focus it
3. Call `type_text(phone_id, "recipient name")`
4. Take a screenshot and verify the intended recipient name rendered correctly and the correct result is visible
5. Only if the user explicitly authorized selecting that recipient and visual verification succeeded, tap the result
6. Tap the message field to focus it
7. Call `type_text(phone_id, "your message")`
8. Take a screenshot and verify the exact message rendered correctly
9. Only if the user explicitly authorized sending that message and visual verification succeeded, tap Return

**DM Input Bar (full features for mutual contacts):**
| Element | Description |
|---------|-------------|
| Camera (blue circle) | Take a photo/video to send |
| "Message..." field | Text input |
| Microphone | Record voice message |
| Gallery/Image | Attach the exact asset the user selects; library browsing remains user-controlled |
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

### Story Highlights
Horizontally scrollable saved story highlights

### Content Tabs
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
1. Tap the comment input bar to focus it
2. Call `type_text(phone_id, "your comment")`
3. Take a screenshot and verify the exact comment rendered correctly
4. Only if the user explicitly authorized posting that comment and visual verification succeeded, tap the **blue send arrow**

### Replying to a Comment
1. Tap "Reply" on the comment
2. Input changes to "Replying to [username]" with pre-filled @mention
3. Tap the reply input to focus it
4. Call `type_text(phone_id, "your reply")`
5. Take a screenshot and verify the @mention and exact reply rendered correctly
6. Only if the user explicitly authorized posting that reply and visual verification succeeded, tap the blue send arrow
7. Tap "X" to cancel reply mode when not submitting

### Liking Comments
- Tap heart icon on right side, or double-tap the comment text

### Long-Press Comment Menu
- Reply with a reel, Add to story, Share, Block, Report

---

## Create Flow

Accessed via "+" button on Home or Profile.

- **Media selection**: Hand control to the user to choose the exact asset. Do not inspect or browse the library; resume only on the selected asset's preview.
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
1. `press_home(phone_id)` → screenshot
2. If **Instagram** is visible, tap it; otherwise, swipe left to the App Library and tap its search field to focus it
3. If using App Library search, call `type_text(phone_id, "Instagram")`
4. If using App Library search, take a screenshot and verify **Instagram** rendered correctly and the intended app result is visible
5. Only if the user explicitly authorized opening Instagram and visual verification succeeded, tap that App Library result
6. screenshot → verify Instagram opened
7. Home tab should be selected by default
8. Swipe up from center to scroll down
9. screenshot → verify new posts loaded
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
3. Tap the "Join the conversation..." input bar to focus it
4. Call `type_text(phone_id, "your comment")`
5. Take a screenshot and verify the exact comment rendered correctly
6. Only if the user explicitly authorized posting that comment and visual verification succeeded, tap the blue send arrow
7. If sent, take a screenshot and verify the comment posted
```

### Watch Reels
```
1. From the current screenshot, locate the labeled Reels tab by its play-button icon in the bottom navigation and tap it
2. screenshot → verify reel playing
3. Swipe up to see next reel
4. Locate the heart icon in the reel's right-side engagement column and tap it to like
```

### Send a DM
```
1. From the current screenshot, locate the Direct Messages tab by its flag/pennant icon in the bottom navigation and tap it
2. Tap compose icon (pencil, top-right)
3. Tap the recipient search field to focus it
4. Call `type_text(phone_id, "recipient name")`
5. Take a screenshot and verify the intended name rendered correctly and the correct result is visible
6. Only if the user explicitly authorized selecting that recipient and visual verification succeeded, tap the correct result
7. Tap the "Message..." input field to focus it
8. Call `type_text(phone_id, "your message")`
9. Take a screenshot and verify the exact message rendered correctly
10. Only if the user explicitly authorized sending that message and visual verification succeeded, tap the return key
11. If sent, take a screenshot and verify the message was sent
```

### Search for Content
```
1. From the current screenshot, locate the Search/Explore tab by its magnifying-glass icon in the bottom navigation and tap it
2. Tap the search bar at the top to focus it
3. Call `type_text(phone_id, "search query")`
4. Take a screenshot and verify the intended query rendered correctly and the expected live results appeared
5. Only if the user explicitly authorized opening a result and visual verification succeeded, tap the intended result
```

### View Your Profile
```
1. From the current screenshot, locate the Profile tab by its person icon at the right end of the bottom navigation and tap it
2. screenshot → verify profile loaded
3. Browse content tabs: Posts, Reels, Tagged
```

### Post a Story
```
1. To use an existing asset, hand control to the user before opening the Story media picker and ask them to navigate to and select the exact asset
2. Resume only after Instagram returns to the selected asset's preview; do not screenshot, scroll, or inspect the photo library
3. To capture new media instead, tap "Your story" or "+" > Story only when the user requested capture and approved any permission prompt
4. Add requested stickers, text, or effects
5. Only if the user explicitly authorized publishing that exact story and the final preview was visually verified, tap "Share"
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
