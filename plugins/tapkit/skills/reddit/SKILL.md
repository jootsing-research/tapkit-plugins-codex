---
name: reddit
description: This skill should be used when the user wants to use Reddit, browse the home or Popular feed, upvote/downvote posts and comments, read or write comments, search for communities or topics, visit subreddits, create posts or polls, manage inbox/chat, or interact with the Reddit app on their iPhone.
---

# Reddit — Community Discussion App

Reddit is a community-driven platform where users browse subreddits ("communities"), upvote/downvote posts and comments, participate in threaded discussions, and share links, images, videos, and polls. The iOS app uses a light theme with a 4-tab bottom bar and distinctive orange branding. This skill teaches you Reddit's UI layout and interaction patterns.

**Always take a screenshot after each action to verify what's on screen.** Use visual landmarks (text labels, icons, positions like "top-left") rather than memorized coordinates.

## App Structure

### Bottom Tab Bar (4 tabs, always visible)

| Position | Icon | Description |
|----------|------|-------------|
| 1 (left) | House (filled when active) | **Home** — Feed of posts from joined communities and recommendations |
| 2 | Square with "+" | **Create** — Opens post composer directly (no intermediate screen) |
| 3 | Bell (with red badge for unread count) | **Inbox** — Notifications and Chat |
| 4 (right) | Snoo avatar (Reddit mascot head) | **You** — Your profile page |

The active tab's icon is filled/bold. A red numeric badge on the bell shows unread notifications.

### Top Bar (Home only)

- **Hamburger menu** (top-left, ≈x=50) — Opens left-side drawer. Red dot indicates new content in subscribed communities.
- **Search bar** — "Find anything" placeholder with orange Reddit snoo icon on the left. Tapping it opens the search screen.

### Top Bar (Post detail / subreddit / other screens)

Dark blue bar with white icons:
- **X close** (top-left) — Returns to previous screen (replaces back arrow in many post detail contexts)
- **Subreddit name / screen title** (center) — May show "N people typing..." under the title in live threads
- **Search icon** (magnifying glass)
- **Sort/filter icon** (sliders icon) — Opens comment sort options
- **"..." three-dot menu** — Opens post-level "More actions" sheet
- **User avatar** (top-right) with green online dot

## Left Sidebar (Hamburger Menu)

Slides in from the left. Dismiss by swiping right or tapping the dimmed area.

Sections (top to bottom):
1. **Feeds**: Popular, News, Latest (each opens a dedicated full-screen feed with back arrow)
2. **Explore Communities**, **Start a Community**
3. **Games on Reddit** (collapsible): Featured games (TapMePlus1, Elevens, Piece of Cake, Sword & Supper), Discover More Games
4. **Recently Visited**: List of subreddits with "See all" link
5. **Resources** (collapsible): Reddit Premium, Earn
6. **Reddit Pro**: Try Reddit Pro
7. **Your Communities** (collapsible): Custom Feeds
8. **About** (collapsible): Reddit Rules, Privacy Policy, User Agreement, Acknowledgements

**Note**: Account settings are **NOT** in the sidebar. Reddit shows a tooltip "NEW: Account settings moved to your profile" pointing to the profile (You tab) hamburger.

## Home Feed

Vertically scrolling list of posts from your joined communities and algorithmic recommendations. No tabs/filters at the top of Home (unlike Popular which is a separate screen).

### Post Card Layout

Each post shows:
- **Header**: subreddit avatar (circle) · `r/subreddit` · relative timestamp (e.g., `4d`) · **Join** button (blue pill, only if not joined) · `...` three-dot menu (far right)
- **Title** (bold, 1-2 lines)
- **Optional flair pill** (small colored pill below title in subreddit pages)
- **Media**: image, video (with mute icon bottom-right, "REPLAY VIDEO" / "SHARE" overlay when finished), or link card. Multi-image posts show "1 / N" indicator top-right and dot page indicators below.
- **Engagement bar** (pill-shaped buttons, left to right):
  | Icon | Action |
  |------|--------|
  | Up arrow + count | **Upvote** (count shown here) |
  | Down arrow | **Downvote** (count merged with upvote) |
  | Speech bubble + count | **Comments** |
  | Award / gift (sometimes with count) | **Awards** (varies per post) |
  | Share arrow (↗) | **Share** — opens iOS share sheet |

Promoted posts show `u/[advertiser] · Promoted` (not `r/subreddit`) and may have a Download button or CTA.

### Navigation

- **Tap post title/body/media** → Opens post detail
- **Tap subreddit name/avatar** → Opens subreddit
- **Tap user u/handle** (on user-posted promoted content) → Opens user profile
- **Swipe up** to scroll down; **swipe down** to scroll up / pull-to-refresh
- **Tap Home tab when already on Home** → Scrolls to top

## Popular / News / Latest Feeds

Accessed from the sidebar hamburger. Each opens as a separate screen with:
- **Back arrow** (top-left, no search bar) · Title (e.g., "Popular") · no Join button in top bar
- Same post card layout as Home

## Post Detail View

Tap a post to open full detail. Header is **dark blue** and sticks.

### Top Bar
- **X close** (top-left, not a back arrow) — Dismisses back to feed
- **Subreddit name** (center) — When live, shows `N people typing...` below
- **Search**, **Sort/filter**, **"..."**, **User avatar**

### Post Section
- Subreddit avatar + `r/subreddit` + snoo-wave icon (if subscribed) · `u/author` · timestamp · domain (e.g., `v.redd.it`)
- `Join` button (right)
- **Title** (bold)
- **Optional green pill**: `Additional Context Pinned` when the post has pinned context
- **Media**: full-width image/video. Videos play inline; when done, show REPLAY / SHARE overlay buttons.
- **Engagement bar** (same 4 pills) — but the **share icon is replaced by a floating chevron-down button** that jumps to the comments

### Sticky Collapsed Header

When scrolled past the post media, a condensed header appears:
- Truncated title + `upvotes · comments`
- Small play button + media thumbnail (tap to play video in a small overlay)

### Comments Section

**Sort options** (tap the sort/filter icon in top bar): Best (default), New, Top, Q&A, Controversial, Old

Each comment contains:
- Avatar + username + timestamp
- **Badges**: green `MOD` shield for moderators, `Top 1% Commenter` pill, green 📌 pushpin for stickied comments
- Body (text, inline links in blue)
- **Comment action row** (tight horizontal row, right-aligned under each comment):
  | Icon | Action |
  |------|--------|
  | `...` | More actions sheet |
  | ↩ Reply | Opens inline reply composer |
  | Emoji reaction + count | Quick reactions (varies: 🐸, 🎖, 🥇, etc.) |
  | ↑ Vote ↓ (with count between arrows) | Upvote / downvote |
- **`N more replies`** link below a thread collapses/expands children
- Threaded replies have **vertical indent lines** on the left showing depth

### Floating "Jump to Comments" Button

Small circular gray chevron-down in bottom-right while scrolling. Tap to jump to the top of the comments section.

### Bottom Comment Composer

Always visible at the bottom: "Join the conversation" placeholder with `GIF` button on the right.

## Menus

### Post "..." Menu (top bar on post detail)

Bottom sheet titled **"More actions..."**:
- Row of share destinations (iMessage, etc.) with note "Your username stays hidden when you share outside of Reddit."
- Follow post · Save · Turn on captions · Copy text
- **Report** (red) · **Block account** (red) · Hide

### Comment "..." Menu

Bottom sheet titled **"Viewer"**:
- Share · Share as post · Save · Follow comment · Copy text · Collapse thread · Block account · Report

### Sort Comments (top bar filter icon)

Bottom sheet **"Sort comments by"**: Best (✓) · New · Top · Q&A · Controversial · Old · X close

## Search / "Find anything"

### Entry
Tap the "Find anything" pill at the top of Home to open the search screen.

### Initial Search Screen
- **Search bar** + **Ask** button (orange — Reddit Answers AI) on the right
- **Recent** searches (clock icon, X to remove each)
- **Trending** (trending-arrow icon, each with "Based on your interests" subtitle)

### Autocomplete (while typing)
Two sections:
- **Search suggestions** (magnifying glass icon): `cats`, `cats musical`, etc.
- **Communities**: subreddit avatar + `r/name` + `N weekly visitors`

### Search Results
Tap `search` on the keyboard or select a suggestion.

- **Search bar** (persistent with clear X) + **Ask** button
- **Tabs** (horizontally scrollable): All · Posts · Communities · Comments · Media · People (active tab has underline)
- **Filter pills** below tabs: `Relevance ⇅` (sort) and `All time ⇅` (date)
- **Sections** (on "All"): "Communities" (chevron-right to see all), "Posts" (chevron-right), each with cards showing subreddit avatar, title, upvotes/comments, and thumbnail

## Subreddit Page

Tap a subreddit name/avatar anywhere (or a result card) to open it.

### Header
- **Banner image** across the top (community custom art)
- Over banner: dark circular buttons — **back arrow** (top-left), **search**, **share**, **"..." / Join button** (top-right). Scrolling collapses the banner.
- Below banner: large subreddit avatar + `r/name` + description + `N members` / `N Online`
- Metadata row: **See more** · Wiki · `#1 in [category]`

### Category Tabs
Horizontal scrollable row under the header: filter icon + `All` (default ✓) + post flair tabs (e.g., `Cat Picture - OC`, `Advice`, `Video`).

### Community Highlights
Pinned posts section marked by 📌, collapsible with chevron. Special threads may appear as styled cards (e.g., green "Discussion Thread" pill).

### Posts
Standard post cards (same layout as Home feed). Post titles often include a **colored flair pill** below the title (e.g., pink `Cat Picture - OC`, dark `Mourning/Loss`).

### Collapsed Sticky Header (on scroll)
Shows: back arrow · `r/name` + member count · search · share · **Join** button (green).

## Media Lightbox

Tapping an image in a feed opens a full-screen black lightbox:
- X close (top-left) · avatar + subreddit (center) · "..." (top-right)
- Full-screen image (pinch to zoom)
- Bottom overlay: username · title · body preview · full engagement bar

## Create (Post Composer)

Tapping **Create** in the bottom nav goes **directly into the text composer** (no community prompt first). The default "Post to" target is your profile (`u/yourname`).

### Layout
- **X close** (top-left) · **Post** button (top-right, grayed until valid)
- **Author/community pill** (top, under X): `u/username ⇅` — tap to open "Post to" community selector
- **RULES** text link (top-right, under Post) — shows community rules
- **"What's on your mind?"** title placeholder (large, bold)
- **`Add tags (optional)`** pill — for post flair (requires a community)
- **"Add some details (optional)"** body placeholder
- **Toolbar** (just above keyboard, left to right):
  | Icon | Function |
  |------|----------|
  | 🔗 link chain | Add link |
  | 🖼 picture frame | Add image(s) |
  | ▶ play | Add video |
  | ☰ bullet list | Convert to **Poll** |
  | `ama` | AMA post (grayed unless eligible) |
  | `Aa` | Text formatting |

### "Post to" Community Selector
- X close · "Post to" title
- `Search for a community` search bar
- List: your profile (green ✓ if selected), recently visited communities with avatar, member count, "recently visited" tag, description

### Poll Mode
Tapping the poll toolbar icon replaces the body with a poll container:
- `Poll ends in 3 days ⌄` dropdown · X to remove poll
- `Option 1` and `Option 2` fields (each with drag handles on the left)
- `+ Add Option` button
- Other toolbar icons become disabled

### Discard Flow
Tapping X (close) with any content shows a **"Discard post?"** modal bottom sheet: "Your content and edits will be lost." · `Go Back` · `Yes, Discard` (red).

## Inbox

### Top Bar
- Hamburger (left) · **Inbox** title · mark-all-read envelope icon · `...` menu

### Sub-tabs
- **Notifications** (active has blue underline) — System/community notifications
- **Chat** — Direct messages

### Notifications Tab
- Black "Turn on notifications" prompt at top (Turn On / Not Now / X)
- Items: avatar/icon · bold title (subreddit or system sender) · preview text · relative timestamp · optional thumbnail
- System notifications use dedicated icons (megaphone for Breaking News, trophy for Achievement unlocked)

### Chat Tab
- Empty state: Reddit snoo illustration + "Welcome to chat!"
- **Floating blue "+" button** (bottom-right) — start a new chat

## You (Profile)

Accessed via the bottom-right tab.

### Top Bar (dark blue)
- **User switcher pill** `u/username ⇅` (left) — switch accounts
- **Search** · **Share** · **Hamburger (≡)** (top-right) — Opens **"My Account"** bottom sheet (this is where settings live, NOT the main sidebar)

### Header
- Large avatar
- **Display name** + `Edit` link
- `u/handle` · `N Followers ›`
- `Add Social Link ›` · achievements badges · `N achievements ›`
- **Stats row** (4 columns): Karma · Contributions · Account Age · Active In

### Content Tabs
- **Posts** (default) · Comments · About
- `Feed options` pill (filter icon)
- `👁 Showing all posts ›` visibility selector

### "My Account" Sheet (from ≡)
- Settings · Profile curation · Drafts (with count) · History · Saved · Online Status (toggle) · Style Avatar · Add to custom feed

## Key Workflows

### Browse the Home Feed
```
1. open_app("Reddit") → screenshot
2. Swipe up to scroll through posts
3. screenshot → find a post to interact with
```

### Upvote a Post
```
1. screenshot → locate engagement bar on a post card
2. Tap the up-arrow (leftmost icon) → arrow turns orange/red and count increments
3. screenshot → verify
```

### Open a Post and Read Comments
```
1. Tap the post title or media
2. screenshot → verify post detail (dark blue top bar, X close)
3. Tap the floating chevron-down button (bottom-right) to jump to comments
4. Swipe up to scroll through comments
5. Tap X (top-left) to return to the feed
```

### Reply to a Comment
```
1. copy_text_to_phone("your reply")
2. In post detail, scroll to the comment → tap its "Reply" arrow
3. screenshot → keyboard and "Join the conversation" composer appear
4. long_press the text field (~1500ms) → tap "Paste"
5. Tap "Reply" button (blue, top-right of composer)
6. screenshot → verify
```

### Comment on a Post (top-level)
```
1. copy_text_to_phone("your comment")
2. Open the post detail
3. Tap the "Join the conversation" field at the bottom
4. long_press the field (~1500ms) → tap "Paste"
5. Tap Reply button
6. screenshot → verify
```

### Change Comment Sort Order
```
1. In post detail, tap the sort/filter icon (sliders) in the top bar
2. screenshot → "Sort comments by" sheet appears
3. Tap: Best / New / Top / Q&A / Controversial / Old
```

### Search for a Community
```
1. On Home, tap the "Find anything" search bar
2. copy_text_to_phone("cats")
3. long_press the search field → tap "Paste"
4. screenshot → autocomplete shows search suggestions + Communities
5. Tap a community row (e.g., `r/cats`) to open it, OR tap "search" on keyboard for full results
```

### Visit a Subreddit
```
1. Tap the subreddit name/avatar anywhere (feed header, search result, etc.)
2. screenshot → subreddit page with banner, description, Join button
3. Use category tabs (All, flairs) to filter posts
4. Tap Join (top-right) to subscribe
```

### Create a Text Post
```
1. copy_text_to_phone("Post title")
2. Tap Create (bottom nav, center-left)
3. screenshot → composer opens with "What's on your mind?"
4. Tap the `u/username ⇅` pill → pick a community in the "Post to" sheet
5. long_press the "What's on your mind?" field → tap "Paste"
6. (Optional) Type/paste body text in "Add some details"
7. Tap Post (top-right, now enabled)
```

### Create a Poll
```
1. Tap Create
2. Paste/type your poll question in "What's on your mind?"
3. Tap the bullet-list icon in the toolbar
4. screenshot → Poll container appears with Option 1, Option 2
5. Tap each Option field and type
6. (Optional) Tap `+ Add Option`, or change "Poll ends in 3 days"
7. Tap Post
```

### Open Account Settings
```
1. Tap You (bottom-right nav tab)
2. Tap the ≡ hamburger in the TOP-RIGHT (NOT the one on Home)
3. screenshot → "My Account" sheet
4. Tap "Settings"
```

### Check Notifications
```
1. Tap Inbox (bell icon, bottom nav)
2. Notifications tab is active by default
3. Swipe down to pull-to-refresh
4. Tap a notification to open the related post/comment
5. Tap Chat sub-tab for DMs
```

## Tips and Gotchas

- **Create tab skips community selection**: Tapping Create in the bottom nav drops you directly into the composer with `u/yourname` as the default target. To post to a community, tap the author pill at the top.
- **Two hamburger menus**: The ≡ on the **Home** top-left opens the community/feed sidebar; the ≡ on the **You** top-right opens the "My Account" sheet (settings live here). They look identical but do different things.
- **Post detail uses X, not back arrow**: The top-left on post detail is an **X** (dismiss). Subreddit pages use a **back arrow** in a dark circle over the banner.
- **Chevron-down on post engagement bar**: This floating button jumps to the comments section — it's not a share button. Share is in the post "..." menu or via the engagement bar in feed cards.
- **Comment reply is one tap**: Tapping the "Reply" text next to a comment opens the composer immediately; there is no intermediate menu.
- **Emoji reactions vary per comment**: The icon between Reply and Vote is a contextual emoji reaction (🐸, 🎖, 🥇, etc.) chosen by the community. The count is how many people reacted.
- **Vote button layout**: In comments, the vote control is a single pill `↑ N ↓` with the count between arrows, not two separate buttons like on post cards.
- **Sticky header on post detail**: When you scroll past the post media, a condensed header with a play button reappears — tapping the play icon plays the video in a floating window.
- **"N people typing..." indicator**: Live comment activity shows as a green dot with "N people typing..." under the subreddit name in the post detail top bar.
- **Promoted posts**: `u/[brand] · Promoted` instead of `r/subreddit`. May have a `Download` CTA (app ads) and appear in-feed and mid-comments.
- **Video playback**: Videos autoplay muted in feed. When finished, an overlay with `REPLAY VIDEO` and `SHARE` appears — don't mistake the SHARE button inside the video for the engagement bar's share icon.
- **Subreddit flair pills**: Under post titles in subreddit views, a colored pill shows the post's flair (e.g., `Cat Picture - OC`). Tapping flair filter tabs at the top of a subreddit filters posts by flair.
- **Sidebar is a drawer, not a tab**: Swipe right (or tap the dimmed area) to dismiss. Scrolling inside the sidebar works independently of the main feed.
- **Trending topic subtitle**: All trending suggestions include "Based on your interests" — this is decoration, not a filter state.
- **Account age on new accounts**: The profile stats row shows `Account Age` in days/months; brand-new accounts show `2d`, etc. — useful for gauging account freshness.
- **"Ask" button**: Next to the search bar, the orange Ask icon launches Reddit Answers (AI summary) — not a normal keyword search.
- **Notification permission banner**: The black "Turn on notifications" card at the top of Inbox is dismissible with X — ignore it if you don't need push notifications.
- **No tab underline on Home**: Home doesn't have sub-tabs like "For you"/"Following" (unlike X/Twitter). Popular/News/Latest are separate full screens reached via the sidebar.
- **Keyboard dismissal**: Tap above the keyboard (on the body of the screen) or use `escape` to dismiss.
- **Discarding a draft**: The X on composer always prompts "Discard post?" if any content exists; empty composers dismiss silently.
