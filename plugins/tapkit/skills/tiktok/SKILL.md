---
name: tiktok
description: This skill should be used when the user wants to use TikTok, browse the For You feed, like or comment on videos, follow creators, search for content, share videos, or interact with the TikTok app on their iPhone.
---

# TikTok — Video App

TikTok is a short-form video platform. Users browse an algorithmic "For You" feed, like/comment/share videos, follow creators, and discover content through explore/search. This skill teaches you TikTok's UI layout and interaction patterns.

## App Structure

### Tab Bar (bottom of screen)

TikTok has 5 tabs along the bottom navigation bar:

1. **Home** (House icon) — Returns to the video feed (For You / Following)
2. **Friends** (People icon) — Friend activity feed with stories row at top
3. **Create** (+ icon, center) — Create a new video
4. **Inbox** (Chat bubble icon) — Messages, notifications, activity, DMs
5. **Profile** (Person icon) — Your own profile, settings, saved content

The tab bar is visible on the main feed but hides when you enter certain sub-views (live streams, full-screen comments, profiles). Navigate back or tap Home to reveal it again.

### Top Bar (Feed Tabs)

When on the Home tab, there are horizontal feed tabs at the top of the screen:

- **LIVE** (far left) — Opens a live stream feed. Swipe up/down between live streams. To exit a live, tap the X in the top-right corner — **aim beyond the visible edge of the screen**. This is critical; tapping at visible positions hits the adjacent toggle button instead.
- **Explore** — 2-column grid of trending/recommended videos with thumbnails, titles, creators, and like counts
- **Local** — 2-column grid of location-based content
- **Following** — Videos from followed accounts only. Has a stories row at top (Create button, then followed creators with colored rings — pink for LIVE, cyan for active)
- **For You** (default, underlined) — Main algorithmic feed with full-screen vertical videos
- **Search** (magnifying glass, far right) — Opens search/discover page

## For You Feed (Main Screen)

The For You feed shows one full-screen vertical video at a time. The video fills the entire screen with UI elements overlaid on top.

### Right Side Action Buttons

A vertical column of action buttons on the right side of the video:

1. **Creator Avatar** (top of column) — Circular profile photo. Has a red **+** button below it if you're not following the creator. Tap to open creator's profile page.
2. **Heart / Like** — White outline when not liked, solid red/pink when liked. Shows like count below. Tap to toggle like/unlike.
3. **Comment** — Speech bubble icon with comment count. Tap to open comment section as a bottom sheet.
4. **Bookmark / Save** — Bookmark icon with save count. Tap to toggle save/unsave.
5. **Share** — Forward arrow icon with share count. Tap to open share sheet.

**Important:** These buttons shift slightly between videos. If a tap doesn't hit the intended button, adjust up or down. The buttons are spaced roughly evenly apart vertically.

### Bottom-Left Info Area

- **Badge** — "Your friend" or "People you may know" (for suggested content from non-followed creators)
- **"↻ Repost to followers"** link
- **Creator name** — Tappable, opens their profile
- **Caption text** — Shows first 2 lines with hashtags. Truncated with "... more" to expand. Tap "more" to see full caption. Tap "less" to collapse.
- **Music/sound ticker** — "♫ [sound name] - [artist]..." Tappable, opens Sound page

### Bottom-Right

- **Music disc** — Small spinning circular avatar at the very bottom-right. Tap to open the Sound page showing all videos using this sound, with "Add to Favorites" and "Use sound" options.

### Bottom Bar (Conditional)

Some videos show additional elements above the tab bar:

- **"Not interested"** / **"Follow"** buttons — Appear for suggested creators you don't follow
- **Search suggestion bar** — "🔎 Search · [related keyword]" with arrow. Tap to search that term.

### Video Overlays

- **Text overlays** from the creator on the video itself
- **"Free Gifts"** promotional badge (top-left, dismissible with X)
- **"Full screen"** button — Appears when a horizontal/non-fullscreen video is shown. The action buttons are positioned differently in this mode — they appear below the video frame rather than overlaid on it.
- **"Sponsored"** badge — Appears on ad videos, along with a CTA button (e.g., "Shop now >")
- **Video progress bar** — Thin line at the very bottom of the video area

## Gestures on the Main Feed

- **Swipe up** — Next video
- **Swipe down** — Previous video (or refresh if at the top)
- **Swipe left** — Opens the creator's profile page
- **Swipe right** (from left edge) — Goes back in navigation
- **Single tap** (center of video) — Pause/play toggle
- **Double tap** (center of video) — Like the video (heart animation appears, heart icon turns red)
- **Long press** (center of video) — Opens context menu bottom sheet

Use `swipe` from the center-left area of the screen for next/previous video. Avoid swiping from screen edges to prevent triggering iOS gestures or AssistiveTouch.

## Comment Section

Opened by tapping the comment bubble icon. Appears as a bottom half-sheet.

- **Header**: "[count] comments" with filter/sort icon and **X** close button
- **Comments list**: Each comment shows avatar, username, text, timestamp, like count, reply button
- **Creator comments** are labeled "Creator" in orange/teal
- **Emoji quick reactions row** — 8 emoji shortcuts at the bottom
- **"Add comment..."** text field with user avatar on the left
- **Below text field**: emoji icon, @ mention button, send button (pink/red arrow)
- Keyboard appears when text field is tapped

To post a comment: `copy_text_to_phone("your comment")` → `long_press` on the "Add comment..." field (duration: 1500) → tap **"Paste"** in the tooltip that appears → tap the send button.

To close: tap the **X** in the header, or swipe down on the sheet.

## Share Sheet

Opened by tapping the share/forward arrow icon. Appears as a bottom sheet.

- **Header**: "Send to" with search icon (left) and X (right)
- **Row 1 — Recent contacts**: Horizontal scroll of friend avatars to send directly
- **Row 2 — Share options**: Repost (yellow), Copy link (blue), SMS (green), Messenger, Telegram, Snapchat, Instagram...
- **Row 3 — More actions**: Report, Not interested, Download, Add to Story, Promote, Cast...

To close: tap the **X** or tap outside the sheet.

## Long Press Context Menu

Opened by long-pressing anywhere on the video. Appears as a bottom sheet.

- **Download** — Save video to device
- **Not interested** — Hide similar content
- **Report** — Report the video
- **Speed** — Playback speed: 0.5x, 1.0x (default), 1.5x, 2.0x
- **Clear display** — Removes all overlay UI elements temporarily
- **Auto scroll** — Toggle to automatically advance to next video
- **Captions and translation** — Enable/configure captions
- **Picture-in-Picture** — Watch in PiP mode
- **Background audio** — Toggle to keep audio playing when leaving the app

## Creator Profile Page

Opened by tapping the creator avatar, creator name, or swiping left on a video.

- **Header**: Back arrow (< top-left), bell icon (notifications), share icon (top-right)
- **Profile info**: Large avatar, display name, @username
- **Stats**: Following count | Followers count | Likes count
- **Action buttons**: Follow (red/pink), Message, dropdown for more options
- **Bio**: Text description, website link, custom items (boards, subscriptions)
- **Content tabs**: Grid icon (default), Repost icon. Category filter pills if the creator has organized content
- **Video grid**: 3-column layout. Pinned videos marked with red "Pinned" badge. Each thumbnail shows view count. Recently watched videos show "Just watched" badge.

To go back: tap the **<** back arrow or swipe right from the left edge.

## Sound Page

Opened by tapping the music disc or sound ticker at the bottom of a video.

- **Video preview** at top (small version of the source video)
- **Sound info**: Thumbnail with play button, sound name, creator name (tappable), post count
- **"Add to Favorites"** button
- **Video grid**: All videos using this sound, "Original" badge on the source video
- **Bottom buttons**: "Add to Story" (outlined) and "Use sound" (red/pink)

To go back: swipe right from left edge or swipe down.

## Following Tab

- **Stories row** at top: Create (+), then followed creators with circular avatars
- **LIVE creators** have pink/magenta rings; active creators have cyan/teal rings
- **Video feed** from followed accounts only
- Same gesture controls as For You feed

## Friends Tab

- **Header**: "Friends" + search icon
- **Stories row**: Create, friend avatars
- **Video feed**: Content from friends (mutual follows)

## Inbox Tab (Deep Dive)

### Accessing Inbox
Tap the **Inbox** icon (chat bubble) in the bottom tab bar. Shows unread badge count.

### Inbox Header
- **Create group chat icon** (top-left) — Opens "Create group chat" page with search bar, suggested contacts with circle selectors, and "Create" button
- **"Inbox" title** with green online dot and **dropdown arrow** (top center) — Tapping the dropdown opens an **Activity Status** sheet:
  - **Public** — Anyone on TikTok can see your activity status
  - **Friends** — Only mutual followers see status (default)
  - **No one** — Hidden activity, but you can still see public users
- **Search icon** (top-right) — Opens search page with "Account and messages" placeholder. Searches both contacts and message content. Shows "Suggested" contacts list.

### Promo Banner
A dismissible promotional banner may appear at the top (e.g., "Don't miss out! Hatch a Streak Pet together!" with Invite button and X dismiss).

### Stories Row
Horizontal scrollable row below the header:

- **"What's good?"** label (above the row) — Tapping this opens a **Thoughts** composer:
  - Full-screen editor with speech bubble + avatar
  - Editable text placeholder "What's good?"
  - "Your Thoughts are visible for 24 hours" disclaimer
  - "Your Story" button to post
  - Gear icon (settings), camera icon, audience icon on right side
  - This is TikTok's ephemeral text status feature
- **Create** (+ button on avatar) — Opens photo picker to create a Story
- **"On this day"** — Shows memories from the same date in prior years (lock icon, pink dot). May not always appear.
- **Friend avatars** with ring colors:
  - **Pink/magenta ring** = Currently LIVE streaming. Tapping opens their LIVE stream directly.
  - **Cyan/teal ring** = Has an active Story. Tapping opens their Story viewer.
  - **No ring** = Active/suggested contact, no current story or LIVE.
  - **Pink speech bubble badge** (bottom-right of avatar) = has unread messages/interactions

### Categories List (Main Inbox Sections)

Each category has an icon, title, subtitle/preview, and optional badge:

1. **Chat with contacts** (green phone icon) — "Find and chat with them" with red "Find" button. Opens a contacts sync prompt asking for full contact access.

2. **New followers** (blue people icon) — Shows latest follower name + badge count.
   - **New followers page**: Follower list with avatar, display name, relationship context, "started following you." + date
   - Action buttons: "Message" (for contacts you follow) or "Follow back" (pink)
   - "View more" dropdown, "Suggested accounts" section below

3. **Activity** (pink heart icon) — Shows latest activity + badge count.
   - **Activity page**: "Priority" section (important notifications) and "Others" section (lower-priority items)
   - "View all" dropdown, "Suggested accounts" section at bottom

4. **TikTok Tako** (TikTok logo speech bubble) — TikTok's built-in AI assistant.
   - Welcome message, suggested question cards, text input ("Type or hold to talk")
   - Bottom tools: "AI Imagine", "Edit image", "Study lens"
   - Image upload, avatar sticker, microphone icons

5. **System notifications** (dark briefcase icon) — Shows latest notification + pink dot.
   - Filter tabs: All, Promote Assistant, LIVE, Account updates
   - Notification cards with category tags, titles, descriptions, timestamps

6. **Message requests** (dark speech bubble icon) — "You have N requests" + badge.
   - Messages from non-friends/non-followers land here

### DM Conversations List

Below categories, individual DM conversations appear with:
- Avatar (optional green dot/cyan ring/LIVE badge)
- Display name (optional blue checkmark, emojis, "+ Follow back" link)
- Message preview/status
- Right side: red badge (unread), wave emoji ("Say hi"), camera (media), pink dot

**Swipe left on conversation**: wave, Delete, Mute, Report buttons

**Suggested accounts** section at bottom with Follow buttons + X dismiss

### DM Chat Interface

**Header:** Back arrow, avatar with online ring, display name, flag icon, three-dot menu

**Chat:** Blue bubbles (sent, right), gray bubbles (received, left with avatar). Timestamps, "Seen" receipts, system messages. Shared videos as thumbnail cards with play/reply/react buttons.

**Quick Reactions Row:** Heart, laugh, thumbs up + Effects, Cards, Streak Pet, more (scrollable)

**Input Bar:** Camera (left), text field, image/gallery, avatar sticker, microphone (right)

**Long-press message:** Emoji reactions, Reply, Forward, Copy, Translate, Delete for me (red), Report (red, received messages only)

**Chat Settings (three-dot):** View profile, Search in conversation, Mute notifications toggle, Pin to top toggle, Report

### TikTok Shop Messages
Orange shopping bag icon. "Shop updates" (order reviews, delivery tracking) + "Messages" (seller conversations)

### Inbox Tips and Gotchas
- Stories row avatars rotate each visit
- **Pink ring = LIVE** (not Story), **cyan ring = Story** — don't confuse them
- "On this day" only appears when memories exist from the same date in prior years
- "What's good?" is interactive — opens Thoughts composer, not just a label
- Swipe left on conversations reveals Delete/Mute/Report actions
- Message requests are separate from main inbox — non-friends land there
- "Keep chatting to unlock a..." = streak gamification
- Streak Pet = daily messaging gamification feature
- TikTok Tako AI assistant lives in Inbox categories

## Sponsored / Ad Videos

Same full-screen format as regular videos but with:
- **"Sponsored"** badge below the caption
- **CTA button** (e.g., "Shop now >") — pink/red, full-width above the tab bar
- **Brand logo** as the creator avatar instead of a person
- **Link icon** below avatar (instead of + follow button)
- Comments and likes are usually from the brand account

## Search Feature (Deep Dive)

### Accessing Search

From the For You feed, tap the **magnifying glass icon** at the top-right of the top bar. This opens the Search Discovery Page.

### Search Discovery Page (Before Searching)

The discovery page appears when you first enter search, before typing a query.

**Layout (top to bottom):**
- **Back arrow** (`<`) — top-left, returns to For You feed
- **Search bar** — placeholder text (gray, shows a suggested search term), **camera icon** for visual search, red **"Search"** button to the right
- **Recent searches** — Listed with icons: music note for sound searches, clock for text searches. Each has an **X** button on the right to delete. **"See more"** link expands the full list.
- **Promo banner** — TikTok Shop voucher promotion with "Join" button (may not always appear)
- **"You may like" section** — Suggested search terms as a bullet list:
  - **Red bullet + red text** = personalized suggestions (recent activity, "Just watched" label)
  - **Black bullet + black text** = general suggestions
  - **Trend arrow icon + "Trending"** label = trending topics
  - **"Refresh"** button (top-right of section) loads new suggestions
- **"Popular LIVE" / "Viral songs"** toggle tabs at bottom:
  - **Popular LIVE**: List of active live streamers with avatars, names, and colored status bullets (red = live)
  - **Viral songs**: Numbered chart of trending songs with album art, song name, artist, post count. Top entries (#1, #2) have highlighted number backgrounds.
- **Microphone icon** — floating button for voice search (bottom-right area)
- **"Help us improve" | "Learn more"** links at very bottom

**Keyboard** appears automatically with a blue "search" button.

### Typing a Search Query (Autocomplete)

As you type, the page switches to autocomplete suggestions:

- **Search bar** shows typed text with cursor, **X clear button** appears to clear text
- **Suggestion list**: Each row has:
  - Magnifying glass icon (left)
  - Query text — typed portion in **pink/red**, completion text in **black**
  - **Fill arrow** (right side) — tapping this fills the suggestion into the search bar WITHOUT executing the search, allowing further refinement
  - Some suggestions show a **thumbnail image** (for creator accounts)
- **"Press and hold on a suggestion to report it"** hint at bottom
- Tap a suggestion directly to execute that search
- Tap the blue **"search"** button on the keyboard or the red **"Search"** button to search for exactly what's typed

### Search Results Page

After executing a search, results appear with a rich multi-tab interface.

**Header:**
- **Back arrow** (`<`) — returns to search discovery page
- **Search bar** — shows current query with **X clear button** and **three-dot menu** to the right
- Three-dot menu opens a bottom sheet with:
  - **Filters** — opens advanced filter panel
  - **Share feedback** — report issues

**Result Tabs** (horizontal scroll, 9 total):
1. **Top** (default) — Mixed results with AI summary + video grid
2. **Shop** — TikTok Shop product listings
3. **Users** — Creator/account search results
4. **Videos** — Video-only grid
5. **Sounds** — Sound/music results
6. **LIVE** — Active live streams matching query
7. **Places** — Location-based results
8. **Photos** — Photo post results
9. **Hashtags** — Matching hashtags

The tab bar is horizontally scrollable — you won't see all 9 at once. Swipe left on the tab bar to reveal more tabs.

#### Top Tab

- **Sub-filter pills** (horizontal scroll below tabs): Contextual refinements like "Latest", "Easy", "Dinner", "Beginners", "Healthy", etc. Tapping a pill refines results and updates the AI summary. Selected pill gets a bold border.
- **Search Highlights card** (AI-generated):
  - Green checkmark badge + "Search Highlights"
  - "AI summary from [source avatars] +N"
  - AI-generated text summary with recipe/info extracted from videos
  - Three-dot menu (top-right of card)
  - **"See more >"** link — opens a full-page expanded AI summary with structured content (ingredients, methods, numbered steps) and embedded video thumbnails with play buttons and like counts
- **Video grid** (2-column) below the highlights: thumbnail, caption (truncated), creator avatar + name, heart + like count, date posted. Some thumbnails have a **bookmark icon** overlay.

#### Shop Tab

- **Filter pills**: Filter icon, Sort (dropdown), Free shipping, 4 Stars & Up, Clearance, Deals
- **"TikTok Shop Protection Free returns"** banner
- **Product cards** (2-column grid): Product image, name, star rating, sold count, price with original/discount, badges ("Free shipping", "Sponsored", "Most Loved", "OFFICIAL"), coupon info, video play icons for video reviews

#### Users Tab

- **User list** (full-width rows): Avatar, username (bold), display name, follower count + like count, red **"Follow"** button
- Verified accounts have **blue checkmark** badges
- Some show "Followed by [mutual connections]" instead of stats

#### Videos Tab

- **2-column video grid**: Large thumbnails with text overlays, caption/subtitle icons, sound icons. Below: caption, creator avatar + name, date, heart + like count

#### Sounds Tab

- **Sound list** (full-width rows): Album art thumbnail (some with play button), sound name (bold), creator/artist, duration, video count
- Red **video camera icon** on right — tap to create video with that sound

#### LIVE Tab

- **2-column grid** of live stream thumbnails: Red "LIVE" badge + viewer count or thumbs-up count. Stream title and creator avatar + username below.

#### Places Tab

- **Place list** (full-width rows): Map pin icon, place name (bold), category (Restaurant, Bakery, etc.), full address

#### Photos Tab

- **Masonry grid** (2-column, variable height): Photo thumbnails with date stamp overlay, caption below, creator avatar + name, heart + like count

#### Hashtags Tab

- **Hashtag list** (full-width rows): # icon, hashtag name (bold), post count. Red **video camera icon** on right to create video with that hashtag.

### Advanced Filters

Accessed via three-dot menu > Filters on the search results page. Opens as a bottom sheet.

**Sort by** (single-select pills):
- Relevance (default)
- Like count
- Latest

**Video category** (single-select pills):
- All (default)
- Unwatched
- Watched
- Liked
- People you follow

**Date posted** (single-select pills):
- All (default)
- Past 24 hours
- This week
- This month
- Last 3 months
- Last 6 months

**Actions**: "Cancel" (top-left) dismisses without applying, "Apply" (top-right, pink/red) applies selected filters. Swipe down on the sheet also dismisses.

### Search Tips and Gotchas

- **Placeholder text is not real text**: The search bar shows gray placeholder/suggestion text (e.g., a trending topic). Tapping the bar and typing replaces it — no need to clear it first.
- **Camera icon** on the search discovery page opens visual/image search. Only visible before executing a search — replaced by X clear button on results page.
- **Voice search**: Tap the floating microphone icon on the discovery page, or the mic on the keyboard.
- **9 result tabs**: Tab bar scrolls horizontally. Full list: Top, Shop, Users, Videos, Sounds, LIVE, Places, Photos, Hashtags. Swipe left on tabs to reveal hidden ones.
- **AI Search Highlights**: Not available for all queries. Appears on Top tab for queries with enough matching content. "See more" expands to a full article-style page.
- **Sub-filter pills are contextual**: They change based on the search query (e.g., food searches get "Easy", "Dinner"; other queries get different refinements).
- **Filters only apply to current tab**: Changing tabs may reset filter selections.
- **Search history**: Previous searches appear on the discovery page with clock icons. Tap X on each to delete, or "See more" to view full history.
- **The search bar X button**: Can be finicky to tap. If it doesn't respond, try tapping slightly to the left or use the back arrow instead.

## Content Creation & Posting (Deep Dive)

### Accessing the Creation Screen

Tap the **+ button** in the center of the bottom tab bar from any screen. This opens the camera/creation screen.

### Camera Screen Layout

The creation screen has a dark theme with the live camera viewfinder as background.

**Top area:**
- **X close** (top-left) — exits creation, returns to previous screen
- **"Add sound"** button (top center) — music note icon, opens sound picker
- **Flip camera** (top-right) — circular arrow, toggles front/rear camera

**Right-side camera tools** (vertical column on the right edge):
1. **Flash** (top of column) — sparkle icon, toggles flash off/on/auto. Icon changes to lightning bolt when on.
2. **Timer** — clock icon, opens countdown sheet (3s or 10s) with draggable recording limit and "Start countdown" button
3. **Layout** — grid icon, multi-panel recording layouts
4. **Retouch** — sparkle-star icon, beauty/touch-up filters
5. **Filters** — loops/chain icon, color filters
6. **Ratio** — resize arrows icon, changes aspect ratio
7. **Chevron down** (bottom of column) — expands labels on all tools. Tapping again (chevron up) collapses them.

**Mode selector** (horizontal, above record button):
- **10m** — 10-minute video
- **60s** — 60-second video
- **15s** — 15-second video
- **PHOTO** — take a photo (default on open)
- **TEXT** — create text-based image post

The mode selector is **swipeable, not tappable**. Swipe right on the mode bar to move from PHOTO toward video modes. Swipe left to move toward TEXT. The selected mode gets a pill highlight. In video modes (10m/60s/15s) the record button turns **red**. In PHOTO mode it's **white**.

**Bottom area:**
- **Record/capture button** (center) — large circle, tap to capture photo or hold/tap to record video
- **Templates/effects row** — circular thumbnails to the right of record button (scrollable)
- **Gallery** (bottom-left) — shows recent photo thumbnail, tap to upload from gallery. See **Limited Photo Access** below if new photos don't appear.
- **Bottom mode tabs**: **POST** (default), **CREATE**, **LIVE**
  - POST = standard post creation
  - CREATE = similar to POST (may offer different editing tools)
  - LIVE = go live (requires minimum follower count)

### Limited Photo Access

When TikTok has "Limited Access" to photos (not full library access), newly saved photos won't appear in TikTok's gallery automatically. To add them:
1. Open TikTok's gallery (tap gallery thumbnail at bottom-left of camera screen)
2. Tap the **"+" button** at the end of the photo grid — this opens the iOS system photo picker
3. In the iOS picker, select the new photos (they appear with blue checkmarks when selected)
4. Tap the **blue checkmark** (top-right) to confirm
5. Return to TikTok's gallery — the new photos now appear

The iOS picker header says "Select more photos or deselect to remove access." It shows ALL device photos. The count at the bottom (e.g., "9 Items") reflects total photos TikTok can access.

### Add Sound Page

Opened by tapping "Add sound" at the top of the camera screen. Appears as a bottom sheet.

- **Tabs**: Hot, **For You** (default), Favorites, Recent
- **Search icon** (magnifying glass, top-right) — search for specific sounds
- **Sound list**: Each row shows album art, song name (bold, pink/red if currently playing), artist, post count, duration
- **Scissors icon** — trim/edit the sound clip length
- **Bookmark icon** — save to favorites
- Tapping a sound selects it — it appears in the top bar as "[sound name] x" with an X to remove
- Swipe down to dismiss the sound picker

### TEXT Mode

Swiping left past PHOTO opens the text post creator:
- **Header**: "CREATE AN IMAGE OF YOUR TEXT" with back arrow
- **Large text input area** — placeholder: "Share your thoughts or questions to spark discussions"
- **Template examples** — horizontal scroll of styled templates
- **"Next"** button (pink, bottom-right) — proceeds to style selection
- **Keyboard** appears automatically
- May show a promo overlay "Try creating text images" with example templates and "Try now" button (X to close)

### Post-Capture Editing Screen

After capturing a photo (or selecting from gallery), the editing screen appears:

**Top area:**
- **Back arrow** (`<`, top-left) — go back to retake/discard
- **Sound bar** — shows auto-assigned sound with X to remove (e.g., "Nearly Naile... x")
- **Settings gear** (top-right)

**Right-side editing tools** (vertical column on the right edge):
1. **Share/forward** (top of column) — arrow icon
2. **AI Alive** — "NEW" badge, AI animation feature that animates photos
3. **Stickers/overlays** — layered squares icon
4. **Crop/adjust** — crop frame icon
5. **Slideshow/animation** — play icon, opens template editor with categories: Trending, Intro&Outro, Basic, Vibe, Dynamic. Templates include Velocity, Midnight Glow, Always Angry, Portrait, Neon Twin, etc.
6. **Text** — "Aa" icon, add text overlays
7. **Sticker/emoji** — speech bubble face icon
8. **Effects/sparkle** — sparkle icon
9. **Chevron down** (bottom of column) — more tools

**Bottom area:**
- **Chevron** (center) — pull up for more options
- **"Collage"** — grid icon, create photo collage
- **Photo thumbnail** — preview of captured photo
- **"+"** button — add more photos to the post
- **"Your Story"** (left button, outlined with avatar) — post as a Story
- **"Next"** (right button, red/pink) — proceed to publishing page

### Publishing Page

The final step before posting. Reached by tapping "Next" on the editing screen.

**Layout (top to bottom):**
- **Back arrow** (`<`) — top-left, returns to editing screen
- **Cover image** thumbnail with "Cover" label + **"+"** to add more photos
- **"Add a catchy title"** — text input for post title (pink placeholder)
- **Description area** — large text input with placeholder "Writing a long description can help get 3x more views on average."
- **Quick-add tools row**:
  - **#** — insert hashtags
  - **@** — mention users
  - **Trending icon** — add trending sounds/topics
  - **"AI rewrite"** — sparkle pen icon, AI-powered caption rewriting
  - **Expand icon** (right side) — fullscreen text editor
- **Location** — with suggested location pills (e.g., "Salt Lake Valley", "Denver Colorado S...") — tap to add
- **Add link** — attach a URL to the post
- **"Everyone can view this post"** — privacy/visibility setting (tap to change: Everyone, Friends, Only me)
- **More options** — opens detailed settings panel (see below)
- **Share to** — cross-posting options

**Additional details:**
- **Character counter**: Shows at bottom-left (e.g., "144/4000") — max 4000 characters for description
- **Post button in expanded editor**: In the expanded text editor view, the "Post" button moves to the **top-right** corner (red pill button)
- **Keyboard dismiss**: `escape` may not dismiss the keyboard on the publishing page. Tapping outside the text field or using the expand/collapse icon works better.

**Bottom buttons:**
- **"Drafts"** (outlined, left) — save as draft for later
- **"Post"** (red/pink with upload arrow, right) — publish the post

### More Options Panel

Opened from the publishing page. Bottom sheet with toggles and settings:

**Privacy settings:**
- **Allow comments** — toggle (default ON)
- **Allow reuse of content** — "Duet, Stitch, stickers, and add to Story" toggle (default ON)

**Advanced settings:**
- **Content disclosure and ads** — sub-page for branded content/ad disclosures
- **Add alternative text** — accessibility description for screen readers
- **AI-generated content** — toggle (default OFF) — labels content as AI-generated
- **Identify similar products** — toggle (default ON) — enables TikTok Shop product matching
- **Allow visual search** — toggle (default ON) — makes content discoverable via visual search
- **Save to device** — toggle (default OFF) — saves post to camera roll
- **Save posts with watermark** — toggle (default OFF) — adds TikTok watermark to saved content
- **Audience controls** — toggle (default OFF) — limits to 18+ viewers

### Exit Options

When backing out of the editing screen with unsaved content, a menu appears:
- **Discard** (red trash icon) — delete the content permanently
- **Save draft** — save to drafts for later editing
- **Send to friends** — share directly via DM

### Creation Tips and Gotchas

- **Mode selector is swipe-only**: You cannot tap on 10m/60s/15s to select them. You must swipe right/left on the mode bar area.
- **Permissions required**: Camera AND microphone must be enabled in iOS Settings > TikTok for full functionality. If mic is denied, you'll get a persistent overlay asking to grant access via Settings.
- **Auto-assigned sounds**: When you capture a photo, TikTok may auto-assign a trending sound. Tap the X on the sound bar to remove it before posting.
- **LIVE requires eligibility**: The LIVE tab at the bottom may not work for accounts with fewer followers. Tapping it may do nothing.
- **Gallery upload**: Tap the gallery thumbnail at the bottom-left of the camera screen to upload existing photos/videos from the camera roll.
- **"Your Story" vs "Post"**: "Your Story" publishes as an ephemeral Story (disappears after 24h). "Post" publishes permanently to your profile.
- **AI rewrite**: The publishing page has an "AI rewrite" tool that can rewrite your caption using AI — useful for improving engagement.
- **Drafts are local**: Saved drafts appear on your Profile tab in a private Drafts section. They are not published until you manually post them.
- **Don't accidentally post**: The red "Post" button publishes immediately with no confirmation dialog. Double-check all details before tapping it.
- **Publishing page text entry**: Use the standard clipboard paste flow for the title and description fields. `copy_text_to_phone("...")` → `long_press` on the field (duration: 1500) → tap **"Paste"** in the tooltip that appears above the field. This is reliable.
- **Maximum 5 hashtags per post**: TikTok enforces a limit of 5 hashtags. If you include more, extras are auto-removed with a toast message "Maximum 5 hashtags. 2 removed." Plan your hashtags accordingly.
- **Multi-select: tap selector circles, NOT image centers**: In multi-select mode, tapping the center of a photo opens a single-image preview instead of selecting it. You must tap the **circle selector** in the upper-right corner of the thumbnail.
- **Sound picker "For You" tab is contextual**: The For You tab in the sound picker shows personalized/contextual suggestions. The algorithm matches sounds to your content (e.g., bird photos surface "Three Little Birds").

## Key Workflows

### Browse the For You Feed
```
1. open_app("TikTok") → screenshot to verify
2. Tap "For You" tab if not already selected (top bar)
3. Watch current video, swipe up from center-left to advance to next video
4. screenshot → verify new video loaded
```

### Like a Video
```
1. screenshot → verify you're on a video
2. Option A: double_tap center of video
3. Option B: tap the heart icon on the right side
4. screenshot → verify heart turned red
```

### Comment on a Video
```
1. Tap the comment bubble icon on the right side
2. screenshot → verify comment section opened
3. copy_text_to_phone("your comment")
4. long_press on "Add comment..." text field (duration: 1500)
5. Tap "Paste" in the tooltip that appears above the field
6. Tap the send button (pink arrow, bottom-right of input area)
7. screenshot → verify comment posted
```

### Follow a Creator
```
1. Tap the red + button below the creator avatar on the right side
2. OR tap creator avatar → tap Follow button on their profile
3. screenshot → verify Follow button changed to Following
```

### Share a Video
```
1. Tap the share/forward arrow on the right side
2. screenshot → see share options
3. Tap desired option (Copy link, SMS, etc.)
4. screenshot → verify
```

### Search for Content
```
1. Tap the search icon (magnifying glass) in the top bar (far right)
2. screenshot → search page appears
3. copy_text_to_phone("search query")
4. long_press on the search field (duration: 1500)
5. Tap "Paste" in the tooltip that appears above the field
6. screenshot → verify autocomplete suggestions appear
7. Tap blue "search" button on keyboard OR tap a suggestion
8. screenshot → verify results page with tabs
```

### Filter Search Results
```
1. On search results page, tap three-dot menu (right of search bar)
2. Tap "Filters"
3. Select desired Sort by / Video category / Date posted pills
4. Tap "Apply" (top-right of filter sheet)
5. screenshot → verify filtered results
```

### Browse Search Result Tabs
```
1. On search results page, tap desired tab (Top, Shop, Users, etc.)
2. If tab not visible, swipe left on the tab bar to reveal more
3. screenshot → verify tab content loaded
```

### Take and Post a Photo
```
1. Tap the + button (center of bottom tab bar) to open creation screen
2. Ensure PHOTO mode is selected (white capture button)
3. Tap the capture button (center)
4. Edit: add text (Aa), stickers, effects as needed
5. Tap "Next" (bottom-right)
6. Add title, description with #hashtags and @mentions
7. Set location, visibility, other options
8. Tap "Post" to publish OR "Drafts" to save for later
```

### Record a Video
```
1. Tap the + button (center of bottom tab bar)
2. Swipe right on mode bar to select 15s/60s/10m
3. Record button turns red — tap to start, tap again to stop
   OR hold to record, release to stop
4. Edit: add sound, text, effects, stickers
5. Tap "Next" → fill in details → tap "Post"
```

### Add Sound to a Post
```
1. On camera screen, tap "Add sound" (top center)
2. Browse tabs (Hot, For You, Favorites, Recent) or search
3. Tap a sound to select it — appears in top bar
4. Tap scissors icon to trim the clip
5. Tap X on the sound bar to remove it
```

### Create a Text Post
```
1. Tap the + button (center of bottom tab bar)
2. Swipe left on mode bar past PHOTO to TEXT
3. Type your text in the input area
4. Tap "Next" → choose a template style
5. Proceed to publishing page
```

### Visit a Creator's Profile
```
1. Option A: Tap their avatar on the right side of the video
2. Option B: Swipe left from center of video
3. Option C: Tap their name in the caption area (bottom-left)
4. screenshot → verify profile page loaded
5. To go back: tap back arrow (< top-left) or swipe right from left edge
```

### Open Sound Page
```
1. Tap the spinning music disc at the bottom-right of the video
2. screenshot → verify sound page opened
3. To go back: swipe right from left edge
```

## Tips and Gotchas

- **Right-side buttons shift**: The positions of action buttons vary slightly per video depending on the creator info area height. Always screenshot first and adjust if needed.
- **LIVE stream exit**: The X button on live streams requires tapping **beyond the visible screen edge** to the right. Tapping at normal visible positions hits the adjacent toggle button instead. This is a known quirk.
- **Non-fullscreen videos**: Horizontal videos show in a smaller frame with a "Full screen" button. The action buttons are positioned differently in this mode — they appear below the video frame rather than overlaid on it.
- **"Not interested" / "Follow" buttons**: These appear at the bottom for videos from creators you don't follow. They can shift other elements up slightly.
- **Search suggestion bar**: Some videos show a search bar at the very bottom, above the tab bar. This pushes the tab bar down slightly.
- **AssistiveTouch**: Can be triggered accidentally by dragging from certain screen positions. If it appears (a floating menu with Tap, Gestures, Home, etc.), tap outside it to dismiss.
- **Comment section vs heart button**: These are close together on the right side. If you're hitting comments when trying to like, aim higher. If you're liking when trying to comment, aim lower.
- **Single tap pauses/plays**: Tapping the center of the video toggles playback. This means the video may be paused after you tap to dismiss overlays. The video auto-resumes when you swipe to the next one.
- **Swipe from center**: Always swipe up/down from the center-left area of the screen to avoid hitting right-side buttons or triggering edge gestures.
- **Video load time**: After swiping to a new video, it takes 1-2 seconds to load. If the screenshot looks transitional (two videos visible), take another screenshot after a moment.
