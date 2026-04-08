---
name: twitter
description: This skill should be used when the user wants to use Twitter/X, browse the feed, like or repost tweets, compose posts, search for topics or people, check notifications, quote tweet, create threads or polls, or interact with the X (Twitter) app on their iPhone.
---

# X (Twitter) — Social Media App

X (formerly Twitter) is a social media platform for short-form posts, news, and conversations. Users browse feeds, post updates, repost/quote content, search for topics, and message contacts. This skill teaches you X's UI layout and interaction patterns.

**Always take a screenshot after each action to verify what's on screen.** Use visual landmarks (text labels, icons, positions like "top-left") rather than memorized coordinates.

## App Structure

### Bottom Navigation Bar

Five icons always visible at the bottom, left to right:

1. **Home** (house icon) — Main feed
2. **Search** (magnifying glass) — Explore, trending, search
3. **Grok** (slash icon) — AI assistant
4. **Notifications** (bell) — Activity and mentions
5. **Messages** (chat bubble) — Direct messages (X Chat)

### Top Bar

Present on most screens:
- **Profile avatar** (top-left) — Opens sidebar menu
- **X logo** or section title (center)
- **Section-specific icon** (top-right) — Varies by section

### Sidebar Menu (tap profile avatar)

Left-side drawer with: account info, Following/Followers counts, and menu items: Profile, Premium, Video, Communities, Bookmarks, Lists, Spaces, Creator Studio, Download Grok, Settings and privacy, Help Center. Dismiss by tapping the dimmed right side.

## Home Feed

### Feed Tabs

Two tabs near the top:
- **"For you"** — Algorithmic feed; has a small **chevron "v"** to its right for topic filtering
- **"Following"** — Chronological posts from followed accounts

The active tab has a **blue underline**. Tapping "For you" text switches tabs; tapping the **chevron** (slightly to the right of the text) opens the topic filter dropdown — these are different tap targets.

### "For you" Topic Filter (tap the chevron)

Bottom sheet with 9 toggleable categories: Politics, Iran Conflict, Sports, Business & Finance, Science & Technology, Entertainment & Arts, Artificial Intelligence, Gaming, Crypto. Dismiss by tapping dimmed area above.

### Following Tab

Chronological posts from accounts you follow (newest first). Reposts show "↻ [Name] reposted" above the post. A blue **"New posts"** pill appears at top when new content is available while scrolled down.

### Post Layout

Each post contains:
- **Avatar** (left side)
- **Header**: Display name (bold) + verified badge (blue/gold/grey) + @handle + timestamp
- **X icon** (top-right of post) — Watermark
- **Post text** — @mentions and links in blue
- **Media** (optional): Images, videos (play button, mute icon, duration), link previews, GIFs
- **"Show more"** (blue link) — Appears on truncated posts
- **Engagement bar** (bottom of post, left to right): Reply (speech bubble), Repost (loop arrows), Like (heart), Views (bar chart), Bookmark (ribbon), Share (upload arrow)

**Important**: The engagement bar position varies per post depending on content length. Always screenshot first and visually locate icons before tapping.

### Post Types

- **Regular posts**: Text with optional media
- **Quote tweets**: Post text + embedded card of the quoted post below
- **Reposts**: "↻ [Name] reposted" label above the post
- **Ads**: "Ad" label + "..." menu in header; may have "Learn more" CTA and "From [Advertiser]" line
- **Automated posts**: Robot icon + "Automated" label below display name

### Menus

- **Repost menu** (tap repost icon): Bottom sheet — Repost, Quote, View Post Interactions
- **Share menu** (tap share icon): Bottom sheet — X Chat area, Copy Link, Share via..., Messages (plus Post Video/Download on applicable posts)
- **Ad "..." menu**: **Popup** (not bottom sheet) — Not interested, Report ad, Why this ad?, View Post Interactions, Request Community Note, @username options. Dismiss by tapping outside.

### Other Elements

- **Compose button**: Blue "+" floating button, always visible at bottom-right
- **Scroll to top**: Tap the Home nav icon when already on Home
- **Pull-to-refresh**: Drag down from top of feed

## Search / Explore

### Layout

- **Search bar** at top center
- **Settings gear** (top-right) — Opens Explore settings (location toggle, location selection)
- **Category tabs**: For You, Trending, News, Sports, Entertainment (active tab has blue underline)

### Tab Content

- **For You**: Promoted ad, "Today's News" section (headline cards with avatars, time, category, post count), trending topics, "Who to follow", "Posts For You"
- **Trending**: "Global Trending" banner (Earth image + "Explore" button), numbered trending topics with rank/category/related terms/"..." menu
- **News**: Clean list of news story cards (headline, avatars, time, category, post count)
- **Sports**: Structured dashboard — league header (NBA), Schedule/Standings/News sub-tabs, live/final game scores, compact scorecards, sports news stories
- **Entertainment**: Clean list of entertainment story cards with high post counts

### Trending Topic "..." Menu

**Popup** (not bottom sheet) with 6 reporting options. Dismiss by tapping outside.

### Global Trending Page (tap "Explore" on banner)

Globe dropdown (country selector), category cards, topic pills, "Popular today" posts. Navigate back by swiping right from left edge (more reliable than back arrow).

### Tapping Content

- **Trending topic** → Search results pre-filled with topic; tabs: Top, Latest, People, Videos, Photos
- **News story card** → Story Detail page with headline, Grok AI summary, disclaimer, Top/Latest tabs, related posts

### Search Flow

1. `copy_text_to_phone("query")`
2. Tap search bar → keyboard appears
3. `long_press` the search field (~1500ms) → tap "Paste" in the tooltip
4. Autocomplete shows suggestions (keywords, topics, accounts)
5. Tap "search" on keyboard for full results
6. Results have tabs: Top, Latest, People, Videos, Photos

### Search Result Tabs

- **Top**: "People" section (scrollable account cards with Follow buttons) + relevance-sorted posts
- **Latest**: Chronological feed with real-time timestamps
- **People**: Vertical list of accounts with Follow buttons
- **Videos**: Posts filtered to video content
- **Photos**: Posts filtered to images/GIFs

### Search Filters (filter icon, top-right of results)

Bottom sheet with: From (Anyone/People you follow/Verified/Custom), Date posted, Language, Post activity (minimum Likes/Replies/Reposts), Near you toggle, Exclude replies toggle, Apply button.

## Grok (AI Assistant)

Accessed via Grok icon in bottom nav. Shows Grok logo, quick action buttons (Create Images, Edit Image, Try Voice Mode), "Ask anything" input, mode selector (Auto/Fast/Expert), and history icon (top-right).

### Grok Modes

- **Auto** (default) — Auto-selects best mode
- **Fast** (lightning bolt) — Quick responses
- **Expert** (lightbulb) — Deeper analysis

## Notifications

Two tabs: **All** (all notification types) and **Mentions** (posts that @mention you). Each notification shows an icon, avatar, name, timestamp, and preview text. Settings gear (top-right) for notification preferences.

## Messages (X Chat)

Requires passcode setup on first access. After setup: conversation list with compose icon for new messages. If passcode isn't set up, sharing posts shows "X Chat Required" prompt.

## Profile Page

Accessed via Sidebar > Profile or tapping your own avatar.

- **Header**: Back arrow, edit icon (pencil), share icon
- **Profile info**: Large avatar, display name + "Get verified" button, @handle, bio text
- **Info row**: Location, website link, join date
- **Stats**: Following count, Followers count (tappable)
- **Content tabs** (horizontally scrollable): Posts, Replies, Highlights, Videos, Photos, Articles
- **"Who to Follow"** section appears below content when Posts tab is empty

## Post Detail View

Tap any post's text to open full detail.

- **Header**: "Post" title, back arrow, "..." menu
- **Full text** (not truncated) + media
- **Exact timestamp** (e.g., "9:41 PM · 1/10/26")
- **Bold view count** (e.g., "624K Views")
- **Engagement bar**: Reply, Repost, Like, Bookmark **with counts** (counts visible here unlike feed), Share — **no Views icon** (view count shown separately above)
- **Sort dropdown**: "Most relevant replies" with chevron
- **Reply thread** below
- **"Post your reply"** field at bottom

### Post Context Menu ("..." or long-press)

Bottom sheet: Not interested, View Post Interactions, Report post, Mark as spam, Request Community Note, @username options (Mute, Block, Follow/Unfollow).

## Compose Post

### Accessing

- **Tap** the blue "+" button (bottom-right) — Opens compose screen
- **Long-press** the "+" button — Radial quick-action menu (compose, GIF, Spaces, close)

### Compose Screen Layout

- **Cancel** (top-left), **Post** button (top-right, blue pill — grayed when empty, blue when text entered)
- Avatar on left, text area ("What's happening?" placeholder)
- **"Everyone can reply"** with globe icon — tap to change reply permissions (Everyone, Accounts you follow, Only mentioned, Verified)
- **Toolbar** above keyboard: Photo library, Camera, Grok, LIVE, GIF, Poll, dimmed moon, character counter, thread "+"

### Toolbar Features

- **Photo library**: iOS picker, select up to 4 items
- **GIF**: Full-screen picker with search and 2-column grid
- **LIVE**: Bottom sheet — Start a Space, Start a live stream
- **Grok**: Bottom sheet — Generate image, Enhance post with Grok
  - **Enhance**: Shows original text, three modes: Proofread, Shorten, As Personality (with personality dropdown — Pirate, Shakespearean, Valley Girl, etc.)
- **Poll**: Activates poll fields (Choice 1/2 with 30-char limit, question with 140-char limit, poll length — default "1 day"). Placeholder changes to "Ask a question...". Remove poll via X button on Choice 1.
- **Thread "+"**: Adds a new connected post below; "Post" changes to "Post all". Only active after text is typed.

### Cancel / Draft Flow

Canceling with content shows a bottom sheet: Delete (red) or Save draft. Empty compose dismisses immediately. Saved drafts accessible via "Drafts" button that appears in top bar.

### Reply Compose (tap reply icon on a post)

Shows original post at top, "Replying to @handle", "Post your reply" placeholder. **Toolbar differs**: No LIVE, no thread "+", but has Location and Flag icons.

### Quote Compose (tap repost icon → Quote)

"Add a comment" placeholder, embedded quoted post card below. **Toolbar**: Like reply toolbar but with thread "+". Canceling always shows draft prompt (even without comment text — the embedded quote counts as content).

## Key Workflows

### Browse the Feed
```
1. open_app("Twitter") → screenshot to verify
2. "For you" tab should be selected by default
3. Swipe up from center of screen to scroll down
4. screenshot → verify new posts loaded
```

### Like a Post
```
1. screenshot → find a post and locate its engagement bar
2. Tap the heart icon on the engagement bar
3. screenshot → verify heart turned red/pink
```

### Repost
```
1. Tap the repost icon (loop arrows) on the engagement bar
2. screenshot → verify repost menu appeared
3. Tap "Repost" for instant repost
4. screenshot → verify
```

### Reply to a Post
```
1. copy_text_to_phone("your reply")
2. Tap the reply icon (speech bubble) on the engagement bar
3. screenshot → verify reply compose with "Replying to @handle"
4. long_press on the reply text field (1500ms) → tap "Paste" in the tooltip
5. Tap "Post" button (top-right)
6. screenshot → verify reply posted
```

### Quote a Post
```
1. copy_text_to_phone("your comment")
2. Tap the repost icon on the engagement bar
3. Tap "Quote" from the menu
4. screenshot → verify quote compose with embedded post
5. long_press on the "Add a comment" field (1500ms) → tap "Paste" in the tooltip
6. Tap "Post" button (top-right)
7. screenshot → verify
```

### Compose a New Post
```
1. copy_text_to_phone("your post")
2. Tap the blue "+" button (bottom-right)
3. screenshot → verify compose screen
4. long_press on the "What's happening?" text area (1500ms) → tap "Paste" in the tooltip
5. Tap "Post" button (top-right)
6. screenshot → verify post published
```

### Create a Thread
```
1. copy_text_to_phone("First post")
2. Tap the blue "+" button
3. long_press on the text area (1500ms) → tap "Paste"
4. Tap the "+" thread button in toolbar
5. screenshot → verify second compose area, button says "Post all"
6. copy_text_to_phone("Second post")
7. long_press on the new text area (1500ms) → tap "Paste"
8. Tap "Post all" (top-right)
```

### Create a Poll
```
1. Tap the blue "+" button
2. Tap the Poll icon (bars) in toolbar
3. screenshot → verify poll fields appeared
4. copy_text_to_phone("Your question") → long_press the question field (1500ms) → tap "Paste"
5. copy_text_to_phone("Option A") → long_press Choice 1 field (1500ms) → tap "Paste"
6. copy_text_to_phone("Option B") → long_press Choice 2 field (1500ms) → tap "Paste"
7. Tap "Post" (top-right)
```

### Search for Content
```
1. copy_text_to_phone("search query")
2. Tap the Search icon in bottom nav
3. Tap the search bar
4. long_press the search field (1500ms) → tap "Paste" in the tooltip
5. Tap "search" on keyboard
6. screenshot → verify results with Top/Latest/People/Videos/Photos tabs
```

### View a Profile
```
1. Tap profile avatar (top-left) to open sidebar
2. Tap "Profile"
3. screenshot → verify profile page loaded
4. Browse content tabs: Posts, Replies, Highlights, Videos, Photos, Articles
```

## Tips and Gotchas

- **"For you" chevron vs tab**: Tapping the text switches feeds; tapping the small chevron to its right opens the topic filter — be precise.
- **Engagement bar positions vary**: Always screenshot and visually locate icons before tapping.
- **Scrolling**: Swipe up to scroll down, swipe down to scroll up.
- **Back navigation**: Back arrow (top-left) or swipe right from left edge.
- **Dismissing sheets/popups**: Tap dimmed area above, or swipe down on sheet handle.
- **Bottom sheets vs popups**: Ad "..." menus and trending "..." menus are popups (no dimmed background); most other menus are bottom sheets.
- **Post truncation**: "Show more" link expands; tap post text for full detail view.
- **App loading**: May take 1-2 seconds after opening or switching tabs.
- **Keyboard dismissal**: Tap non-interactive area above it.
- **Compose toolbar varies**: New post, reply, and quote have different toolbars — check before tapping.
- **Thread "+" button**: Only active after text is typed.
- **Poll keyboard quirk**: After removing a poll, keyboard may still show "@"/"#" keys — dismiss and reopen keyboard.
- **Quote cancel**: Shows draft prompt even with no comment typed (embedded quote counts as content).
- **Swiping in compose**: May trigger keyboard swipe-to-type — avoid swipe gestures while keyboard is active.
