---
name: twitter
description: This skill should be used when the user wants to use Twitter/X, browse the feed, like or repost tweets, compose posts, search for topics or people, check notifications, quote tweet, create threads or polls, or interact with the X (Twitter) app on their iPhone.
---

# X (Twitter) — Social Media App

X (formerly Twitter) is a social media platform for short-form posts, news, and conversations. Users browse feeds, post updates, repost/quote content, search for topics, and message contacts. This skill teaches you X's UI layout and interaction patterns.

**Always take a screenshot after each action to verify what's on screen.** Use visual landmarks (text labels, icons, positions like "top-left") rather than memorized coordinates.

## TapKit Setup Reminder

Before acting in this app, follow the core TapKit setup: `list_phones()` -> choose `phone_id` -> `get_phone_status(phone_id)`. All TapKit examples in this skill assume every MCP tool call includes that `phone_id`.

For every text-entry action, focus the correct field, call `type_text(phone_id, text)`, then call `screenshot(phone_id)` and visually verify the rendered text. Do not tap Send, Post, Search, Save, Confirm, or an equivalent submission control automatically. Submit only when the user explicitly authorizes the exact action and visual verification succeeds.

## X Chat Passcode Boundary

- Never enter, configure, change, infer, store, repeat, reveal, or otherwise handle an X Chat passcode.
- If X or iOS presents any passcode creation, entry, recovery, or confirmation screen, stop immediately and hand control to the user. Do not type into the passcode field, inspect the entered value, take a screenshot that exposes it, or narrate it.
- Resume only after the user confirms they completed the passcode step and a screenshot verifies that no passcode or recovery secret is visible. If X Chat remains unavailable, report that limitation without attempting a workaround.

## App Structure

### Bottom Navigation Bar

Five icons always visible at the bottom, left to right:

1. **Home** (house icon) — Main feed
2. **Search** (magnifying glass) — Explore, trending, search
3. **Center slash icon** — Product-specific surface not covered by a supported workflow in this skill; do not use it
4. **Notifications** (bell) — Activity and mentions
5. **Messages** (chat bubble) — Direct messages (X Chat)

### Top Bar

Present on most screens:
- **Profile avatar** (top-left) — Opens sidebar menu
- **X logo** or section title (center)
- **Section-specific icon** (top-right) — Varies by section

### Sidebar Menu (tap profile avatar)

Left-side drawer with: account info, Following/Followers counts, and menu items such as Profile, Premium, Video, Communities, Bookmarks, Lists, Spaces, Creator Studio, Settings and privacy, and Help Center. Dismiss by tapping the dimmed right side.

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
- **News story card** → Story Detail page with headline, an automatically generated summary and disclaimer when available, Top/Latest tabs, and related posts

### Search Flow

1. Tap the search bar to focus it
2. `type_text(phone_id, "query")`
3. `screenshot(phone_id)` → verify the rendered query and expected autocomplete suggestions
4. Do not submit automatically. Only if the user explicitly authorized running the search and verification succeeded, tap "search" on the keyboard
5. `screenshot(phone_id)` → verify results have tabs: Top, Latest, People, Videos, Photos

### Search Result Tabs

- **Top**: "People" section (scrollable account cards with Follow buttons) + relevance-sorted posts
- **Latest**: Chronological feed with real-time timestamps
- **People**: Vertical list of accounts with Follow buttons
- **Videos**: Posts filtered to video content
- **Photos**: Posts filtered to images/GIFs

### Search Filters (filter icon, top-right of results)

Bottom sheet with: From (Anyone/People you follow/Verified/Custom), Date posted, Language, Post activity (minimum Likes/Replies/Reposts), Near you toggle, Exclude replies toggle, Apply button.

## Notifications

Two tabs: **All** (all notification types) and **Mentions** (posts that @mention you). Each notification shows an icon, avatar, name, timestamp, and preview text. Settings gear (top-right) for notification preferences.

## Messages (X Chat)

X Chat may require passcode setup or entry before showing the conversation list. If any such screen appears, stop and hand control to the user under the passcode boundary above. Do not configure or enter the passcode. If sharing a post produces an "X Chat Required" prompt, do not continue through setup; tell the user that X Chat must be unlocked by them before the requested share can proceed.

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
- **Toolbar** above keyboard: Photo library, Camera, LIVE, GIF, Poll, dimmed moon, character counter, thread "+", plus product-specific controls that are outside this skill's supported workflows

### Toolbar Features

- **Photo library**: iOS picker, select up to 4 items
- **GIF**: Full-screen picker with search and 2-column grid
- **LIVE**: Bottom sheet — Start a Space, Start a live stream
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
1. press_home(phone_id) → screenshot(phone_id) → visually locate and tap the Twitter icon; use App Library if it is not visible
2. screenshot(phone_id) to verify
3. "For you" tab should be selected by default
4. Swipe up from center of screen to scroll down
5. screenshot → verify new posts loaded
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
1. Tap the reply icon (speech bubble) on the engagement bar
2. screenshot → verify reply compose with "Replying to @handle"
3. Tap the reply text field to focus it
4. type_text(phone_id, "your reply")
5. screenshot(phone_id) → verify the rendered reply and target post
6. Only if the user explicitly authorized posting this exact reply and verification succeeded, tap "Post" (top-right)
7. screenshot(phone_id) → verify the reply posted
```

### Quote a Post
```
1. Tap the repost icon on the engagement bar
2. Tap "Quote" from the menu
3. screenshot → verify quote compose with embedded post
4. Tap the "Add a comment" field to focus it
5. type_text(phone_id, "your comment")
6. screenshot(phone_id) → verify the rendered comment and embedded post
7. Only if the user explicitly authorized publishing this exact quote post and verification succeeded, tap "Post" (top-right)
8. screenshot(phone_id) → verify it published
```

### Compose a New Post
```
1. Tap the blue "+" button (bottom-right)
2. screenshot → verify compose screen
3. Tap the "What's happening?" text area to focus it
4. type_text(phone_id, "your post")
5. screenshot(phone_id) → verify the rendered post text
6. Only if the user explicitly authorized publishing this exact post and verification succeeded, tap "Post" (top-right)
7. screenshot(phone_id) → verify the post published
```

### Create a Thread
```
1. Tap the blue "+" button
2. Tap the text area to focus it
3. type_text(phone_id, "First post")
4. screenshot(phone_id) → verify the rendered first post
5. Tap the "+" thread button in toolbar
6. screenshot(phone_id) → verify the second compose area and "Post all" button
7. Tap the new text area to focus it
8. type_text(phone_id, "Second post")
9. screenshot(phone_id) → verify the rendered second post and full thread draft
10. Only if the user explicitly authorized publishing this exact thread and all verification succeeded, tap "Post all" (top-right)
11. screenshot(phone_id) → verify the thread published
```

### Create a Poll
```
1. Tap the blue "+" button
2. Tap the Poll icon (bars) in toolbar
3. screenshot → verify poll fields appeared
4. Tap the question field to focus it → type_text(phone_id, "Your question") → screenshot(phone_id) → verify the rendered question
5. Tap the Choice 1 field to focus it → type_text(phone_id, "Option A") → screenshot(phone_id) → verify the rendered choice
6. Tap the Choice 2 field to focus it → type_text(phone_id, "Option B") → screenshot(phone_id) → verify the rendered choice
7. Only if the user explicitly authorized publishing this exact poll and all verification succeeded, tap "Post" (top-right)
8. screenshot(phone_id) → verify the poll published
```

### Search for Content
```
1. Tap the Search icon in bottom nav
2. Tap the search bar to focus it
3. type_text(phone_id, "search query")
4. screenshot(phone_id) → verify the rendered query and expected autocomplete suggestions
5. Do not submit automatically. Only if the user explicitly authorized running the search and verification succeeded, tap "search" on the keyboard
6. screenshot(phone_id) → verify results with Top/Latest/People/Videos/Photos tabs
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
