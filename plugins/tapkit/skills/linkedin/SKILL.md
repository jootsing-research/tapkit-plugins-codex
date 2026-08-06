---
name: linkedin
description: This skill should be used when the user wants to use LinkedIn, browse the professional feed, like or comment on posts, connect with people, search for jobs, send messages, create posts, or interact with the LinkedIn app on their iPhone.
---

# LinkedIn — Professional Networking App

LinkedIn is a professional networking platform. Users browse a feed of professional content, connect with people, search for jobs, message contacts, and post updates. This skill teaches you LinkedIn's UI layout and interaction patterns.

## TapKit Setup Reminder

Before acting in this app, follow the core TapKit setup: `list_phones()` -> choose `phone_id` -> `get_phone_status(phone_id)`. All TapKit examples in this skill assume every MCP tool call includes that `phone_id`.

For every text entry, focus the intended field, call `type_text(phone_id, text)`, then take a screenshot and verify the rendered text. Do not tap **Send**, **Post**, **Search**, **Save**, **Confirm**, **Comment**, Return, or an equivalent submission control unless the user explicitly authorized that submission and visual verification succeeded.

## Privacy-Minimized Previews and Final Confirmation

Before sending a connection request, accepting an invitation, sending any message or shared post, posting a comment or reply, reposting, or publishing or scheduling a post:

1. Prepare the action without activating its final submission control.
2. Take a fresh screenshot of the final state and verify the intended target, audience, and final content as applicable.
3. Present a concise preview containing only the information needed to review the action:
   - Connection request: target display name and final note, if any.
   - Invitation acceptance: inviter display name and the **Accept** action.
   - Message or shared post: recipient or group, final message, and requested attachment.
   - Comment or reply: intended post or comment and final comment text.
   - Repost: intended source post, repost mode, audience, and final commentary, if any.
   - Publication: audience, final text, requested media, and schedule, if any.
4. Ask for explicit confirmation and wait. A request made before this preview is not final confirmation.
5. Only after that confirmation, activate the final control and verify the result. If the target, audience, content, or final screen changes, preview it again and reconfirm.

Confirm each action individually rather than batching unrelated targets. Never quote, transcribe, infer, or summarize sponsored content, unrelated profiles, unrelated feed or notification items, recommendations, message previews, or personal data merely because they appear on screen. Navigate only as broadly as needed for the request and report only the requested target information. When a target is ambiguous, ask a narrow clarifying question without listing unrelated visible people or content.

## App Structure

### Bottom Tab Bar (5 tabs)

1. **Home** (House icon) — Main feed of posts and updates
2. **Video** (Play button icon) — Full-screen vertical video feed (TikTok/Reels style)
3. **My Network** (People icon with plus) — Connection management, invitations, suggestions
4. **Notifications** (Bell icon) — Activity alerts, mentions, engagement notifications
5. **Jobs** (Briefcase icon) — Job listings, applications, career tools

The tab bar is always visible on main screens. It hides inside DM conversations and the post composer.

### Top Bar (Home Feed)

- **Profile avatar** (far left) — Circular photo, tappable to open navigation drawer / profile sidebar
- **Search bar** (center) — Placeholder "Search", tappable to open search interface
- **Create/compose icon** (right of search) — Pencil-in-square icon, opens post composer
- **Messages icon** (far right) — Speech bubble icon with red badge showing unread count. Opens messaging interface.

**Important:** The top bar layout varies by tab. On the Jobs tab, the search bar placeholder changes to "Describe the job you want" with a green "New" badge. On Notifications, a settings gear icon appears instead of the compose icon.

## Home Feed

The Home feed is a vertically scrolling list of posts. Each post is a card with clear sections.

### Post Card Structure

**Context line (above header):**
- Shows why the post appears: "[Name] and [Name] commented on this", "[Name] reposted", etc.
- Has a three-dot menu (...) and X dismiss button on the right side of the context line

**Post Header:**
- **Author avatar** (left) — Circular profile photo, tappable to open their profile
- **Author name** (bold) — Tappable, with optional verification badge (blue "in" square logo)
- **Connection degree** — "1st", "2nd", "3rd+" shown after the name
- **Headline** — Professional title / company (truncated with "...")
- **Time posted** — "1w", "2d", "3h" etc. + optional "Edited" label + globe icon (public visibility)
- **Three-dot menu** (right) — "..." button for post options
- **X dismiss button** (far right) — Removes post from feed

**Post Body:**
- **Text content** — Shows first few lines, truncated with "...more" link to expand. Tap "...more" to see full text.
- **Hashtags** — Shown in blue as clickable links (e.g., #vibecoding)
- **Media** — Images, documents, polls, articles, link previews embedded in the card. Link previews show as embedded cards with image, title, and domain.

**Engagement Stats (below body):**
- **Reaction icons + count** — Small emoji icons (like, celebrate, love, insightful, etc.) with total count (e.g., "25")
- **Comments count** — "4 comments" — tappable to open comments
- **Reposts count** — "1 repost"

**Action Buttons (bottom of card, full-width row of 4):**
1. **Like** (thumbs up icon + "Like" label) — Tap to like. Long press for reaction picker.
2. **Comment** (speech bubble icon + "Comment" label) — Opens comment section as bottom sheet.
3. **Repost** (circular arrows icon + "Repost" label) — Opens repost options bottom sheet.
4. **Send** (paper plane icon + "Send" label) — Opens share/send sheet.

### Inline Comments on Feed

Some posts show a highlighted comment directly in the feed below the action buttons:
- Avatar, name, connection degree, headline
- Comment text
- "Like" button with reaction count + "Reply" link

### Promoted/Sponsored Posts

Appear in the feed with:
- **Company logo** as avatar instead of a person
- **Follower count** (e.g., "22,744 followers")
- **"Promoted"** label below the company name
- Three-dot menu only (no X dismiss button)
- Same action buttons (Like, Comment, Repost, Send)

## Reaction Picker

Long-pressing the **Like** button reveals a floating reaction bar with 6 options (left to right):

1. **Like** (thumbs up, blue) — default reaction
2. **Celebrate** (clapping hands, green)
3. **Support** (hands holding heart, purple)
4. **Love** (heart, red)
5. **Insightful** (lightbulb, yellow)
6. **Funny** (laughing face, teal)

The reactions are animated emoji icons in a horizontal row. Slide finger to desired reaction and release, or tap one directly. Tap outside to dismiss without reacting.

## Comment Section

Opened by tapping the Comment button on a post. Appears as a bottom half-sheet that can be pulled to near-full screen.

- **Handle bar** (top center) — drag to resize or dismiss
- **Sort dropdown**: "Most relevant" with down arrow — tap to change sort order
- **Comments list**: Each comment shows:
  - Avatar (left)
  - Name (bold) with optional LinkedIn badge + connection degree + timestamp + three-dot menu
  - Headline/title (truncated)
  - Comment text (including #hashtags in blue, links as embedded cards)
  - **"Like"** button + reaction icons/count + **"|"** separator + **"Reply"** button + reply count
  - **"Author" badge** (teal/green pill) next to the poster's own comments
- **Comment input** (bottom, always visible):
  - User avatar (left)
  - "Leave your thoughts here..." text field
  - Below text field: Image/media icon, @ mention icon
  - **"Comment"** button (right, grayed out when empty, active when text entered)
- Keyboard appears when text field is tapped

To prepare a comment, tap the text field, call `type_text(phone_id, "your comment")`, then take a fresh screenshot and verify the intended post and exact comment. Present the privacy-minimized preview and request explicit final confirmation. Only after that confirmation, tap the "Comment" button.

To dismiss: swipe down on the handle bar, or tap outside the sheet (above it on the post).

## Repost Options

Opened by tapping the Repost button. Appears as a bottom sheet with 2 options:

1. **Repost with your thoughts** (pencil-in-square icon) — "Create a new post with [Author]'s post attached" — opens the post composer with the original post embedded as a quote repost
2. **Repost** (repost arrows icon) — "Instantly bring [Author]'s post to others' feeds" — direct repost, no additional comment needed

Treat the direct **Repost** option as a final submission control. Do not tap it until the source post and repost mode have been freshly previewed and the user has explicitly confirmed.

## Send / Share Sheet

Opened by tapping the Send button on a post. Appears as a bottom sheet.

- **"Send as message"** header
- **Search field** — Search contacts to send the post to
- **Recent contacts row** (horizontal scroll): Circular avatars with names. The post author has an "Author" badge. Selecting a contact prepares the share; it does not bypass the message preview and final-confirmation gate.
- **External sharing row** (horizontal scroll at bottom):
  - **Share via** (iOS share sheet icon)
  - **Copy link** (chain link icon)
  - **Messages** (green, iMessage)
  - **Mail** (blue, email)
  - **Facebook** (blue, Facebook logo)
  - (scrollable for more options)

## Post Options Menu (Three-Dot)

Opened by tapping "..." on a post. Appears as a bottom sheet:

- **Save** (bookmark icon) — Save the post for later
- **Share via** (share icon) — Share externally via iOS share sheet
- **Not interested** (eye-slash icon) — Hide similar content
- **Unfollow** (X icon with arrow) — Stop seeing their posts without disconnecting
- **Report post** (flag icon) — Report the post
- **Unfollow [Author Name]** (X icon) — Specifically unfollow the named author

## Video Tab

Full-screen vertical video feed, similar to TikTok/Instagram Reels. One video fills the entire screen at a time.

### Video Feed Layout

**Top area:**
- If the video is a repost, the original creator's avatar, name (with optional blue checkmark), and @username appear at the top-left

**Right side action buttons** (vertical column):
1. **Like** (thumbs up icon + count, e.g., "6.9K") — Tap to like
2. **Comment** (speech bubble icon + count, e.g., "83") — Opens comment section
3. **Share** (forward arrow icon) — Opens share options
4. **Bookmark/Save** (ribbon icon) — Save the video

**Bottom-left info area:**
- **Author avatar** (circular) with "Follow" button (outlined pill)
- **Author name** with optional LinkedIn verification badge
- **Headline** (truncated)
- **Caption text** with "...more" to expand
- **Three-dot menu** (right of author info)

**Bottom:**
- Progress bar (thin line at the very bottom)

### Gestures

- **Swipe up** — Next video
- **Swipe down** — Previous video
- **Tap** (center) — Pause/play toggle

## My Network Tab

### Sub-tabs

Two tabs at the top below the top bar:

1. **Grow** (default, selected with green underline) — Invitations and suggestions
2. **Catch up** — Life events of connections

### Grow Tab

**Invitations section:**
- Header: "Invitations (N)" with right arrow to see all
- Each invitation: Avatar, name (with optional blue "in" badge), headline, mutual connections count, time ago
- Action buttons: **X** (decline, circular outline) and **checkmark** (accept, circular outline, blue)
- Treat the checkmark as the final acceptance control; preview the requested invitation and obtain explicit final confirmation before tapping it.

**Promotional section:**
- LinkedIn puzzle/games feature: "Need a 30 second break?" with "Solve" button

**"Manage my network"** — Link with right arrow

**"People you may know" section:**
- Grouped by context (e.g., "People you may know from Florida State University")
- 2-column card grid: Large photo, X dismiss button, name with optional verification badge, headline, mutual connections info, "Connect" button (green/blue, outlined)

### Catch up Tab

**Filter pills** (horizontal scroll): All (selected, green), Job changes, Birthdays, Work anniversaries

**Event cards** (list):
- Blue dot (left) = unread/new
- Avatar, Name (bold), Event description ("Started a new position as...", "Completed X years at...", "Celebrate X's birthday today")
- Quick action button: **"Congrats..."** (green, send icon) for job/anniversary events, **"Wishing you a very happy birthday!"** (red, send icon) for birthdays
- Engagement: Like count (thumbs up icon), Comment count (speech bubble icon)
- Three-dot menu (right)

Treat any quick action that sends a prepared message as a message: preview its recipient and final text, then obtain explicit final confirmation before tapping its send control.

## Notifications Tab

### Top Bar
Profile avatar, Search bar, **Settings gear icon** (unique to this tab), Messages icon

### Filter Pills
All (selected, green), Jobs, My posts, Mentions

### Notification List
Each notification shows:
- **Blue dot** (left) = unread
- **Avatar(s)** of person(s) involved
- **Notification text** — Bold names, truncated description of activity
- **Timestamp** (right) — "4m", "1h", "2h", "3h", "6h" etc.
- **Three-dot menu** (right)
- Some show engagement stats: "5 reactions · 1 comment"

**Types of notifications:**
- "Suggested for you" — recommended content
- "People are engaging with [Name]'s post" — trending content from connections
- "[Name] reposted [Name]'s post" — repost activity
- "[Name] commented on [Name]'s post" — comment activity
- "[Name] posted" — new post from connection
- "[Name] spoke at this live video event" — event activity

## Jobs Tab

### Top Bar
Profile avatar, Search bar with placeholder **"Describe the job you want"** + green **"New"** badge, Messages icon

### Action Pills
Preferences, Job tracker, Post a free job

### "Top job picks for you" Section
Subtitle: "Based on your profile, preferences, and activity like applies, searches, and saves"

**Job cards** (list):
- Company logo (left)
- Job title (bold) with optional verification badge
- Company name
- Location + work type (On-site, Hybrid, Remote)
- Salary range (e.g., "$307K/yr - $427K/yr" or "$70/hr - $120/hr") — $/yr, $/hr, $/month formats all appear
- Optional: inline benefits (e.g., "401(k), +1 benefit" or "Vision, 401(k), +2 benefits")
- Social proof: Stacked avatar icons + "X connections work here" or "X school alumni work here"
- Badges: "Promoted" (gray), "Be an early applicant" (green), "You'd be a top applicant" (orange folder icon), "Actively reviewing applicants" (green checkmark + green text), "Easy Apply" with LinkedIn "in" icon
- **Time posted** in green text (e.g., "2 hours ago", "6 days ago")
- **"Viewed"** label (gray) appears on cards after you've viewed the job detail
- **X dismiss button** (right)

"Show all" link at bottom of section

### "Explore companies that hire for your skills" Section
Horizontal scroll of company cards (Promoted). Each card shows:
- Large company logo on promotional background image
- Three-dot menu, company name (bold), employee count + location
- School alumni badge + count, "Who We Are" description snippet

### "More jobs for you" Section
Below Explore companies. Same subtitle as "Top job picks". Infinite scroll of additional job recommendations.

### Job Detail Page

Tapping a job card opens a detail page as a **bottom sheet** that can expand to full screen.

**Initial State (Half-Sheet):**
- **Handle bar** (top center) — drag to expand or dismiss
- **Three-dot menu** (top-right)
- Company logo + name, job title (large, bold), location · time posted · applicant info
- **Posting context** — "Responses managed off LinkedIn" (external) or "Actively reviewing applicants" (green, Easy Apply)
- **Info pills**: Salary range, Work type (On-site/Remote/Hybrid), Employment type (Full-time/Part-time/Contract)

**Two Application Types:**
- **External Apply:** "Apply" button (blue) with external link icon — redirects to company website
- **Easy Apply:** "Easy Apply" button (blue) with LinkedIn "in" icon — application within LinkedIn
- Both have a **"Save"** button (outlined) next to the Apply button

**Sticky Bottom Bar:** Apply/Save buttons persist when scrolled.
**Sticky Header (When Scrolled):** X close, compact job title + company + location, three-dot menu.

**Sections (top to bottom):**
1. **Premium AI Assessment** — "Show match details", "Create cover letter" (external) or "Help me stand out" (Easy Apply)
2. **People you can reach out to** — Contact cards with email/phone, send icon
3. **Meet the hiring team** (Easy Apply only) — Job poster info with send icon
4. **About the job** — Description with "...more" to expand
5. **Featured benefits** (Easy Apply only) — Comma-separated list
6. **Requirements** (Easy Apply only) — Bulleted list
7. **Set alert for similar jobs** — Toggle (default Off)
8. **Resume writer promo card** (dismissible)
9. **Premium: "See how you compare"** — Applicant count, seniority level bar, education breakdown
10. **Premium: Company Insights** — Powered by Bing. Focus areas, hiring trends, growth chart, median tenure, competitors
11. **About the company** — Logo + follower count + Follow button
12. **"Interested in working with us?"** — "I'm interested" button
13. **Company photos** — Horizontal scroll
14. **More jobs** — Related listings

### Job Tracker

Full-screen page accessed via "Job tracker" pill.

- **Header**: X close, "Job tracker" title
- **Filter pills**: Stage dropdown (green), Date posted dropdown
- **5 pipeline stages**: Saved, In Progress, Applied, Interview, Archived
- **"Update"** button at bottom of stage dropdown
- **Empty state**: Illustration + "No jobs here" + "Find more jobs" button

### Preferences

Full-screen page accessed via "Preferences" pill.

**My interests:** Open to work, Job alerts, AI trainer project alerts, Pay
**My qualifications:** Resumes and application data
**My verifications:** Verifications

### AI Job Search ("Describe the job you want")

Tapping the search bar on the Jobs tab opens a natural language job search.

- Suggested prompt pills (2-column grid) with emoji icons
- Welcome text explaining the feature
- **Results:** Filter pills (Jobs, Date posted, Easy Apply, Company), auto-detected location with pin icon, result count, job cards, "Get job alerts for this search" toggle

## Search

### Accessing Search
Tap the **Search bar** in the top bar on any tab.

### Search Page (Before Typing)

- **Back arrow** (left) — returns to previous screen
- **Search bar** — text input with cursor, placeholder "Search"
- **"Recent" section** — "Recent" label + "Clear all" link (right) + QR/scan icon (far right)
  - Recent profile searches: Avatar + name
  - Recent text searches: Clock icon + search term
- **"Try searching for" section** — Trending/suggested searches with magnifying glass icons
  - News headlines and trending topics
- **Keyboard** — Appears automatically with blue "search" button

### Autocomplete (While Typing)

- Search bar shows typed text with cursor, **X clear button** appears (right)
- **Suggestion list**: Each row has:
  - Magnifying glass icon (left) for text suggestions, or brand/product logo for specific items
  - Query text — typed portion in regular weight, **completion in bold**
  - **Fill arrow** (top-right corner of row) — tapping fills the suggestion into the search bar WITHOUT executing, allowing further refinement
  - Some show category context: "in Jobs" (gray text after suggestion)
  - Product/brand results show logo icon with metadata
- **"Show all results"** link (green) at the bottom — executes the full search
- Tap a suggestion directly to execute that search

### Search Results Page

**Header:**
- Back arrow (left) — returns to search/autocomplete page
- Search bar showing current query

**Result Category Tabs** (horizontal scroll):
People, Posts, Jobs, Courses, Groups, Products (and possibly more, scrollable)

**Default view shows mixed results with sections:**

#### People Section
- "People" header (bold)
- **Filter pills**: 1st, 2nd, 3rd+, "Actively hiring" (orange folder icon)
- **People cards** (list): Avatar, name (bold) with verification badge + connection degree, current title, location, matching text highlighted in bold, mutual connections (stacked avatars + count), **Connect button** (person+ icon, right)
- "Show all people results" link at bottom

#### Posts Section
- "Posts" header (bold)
- **Filter pills**: "From my network", "Past 24 hours", "Past week"
- Post cards showing author info, "+ Follow" button, headline, time, post text, embedded job cards with "View job" buttons
- Standard engagement and action buttons (Like, Comment, Repost, Send)
- "Show all post results" link at bottom

#### Jobs Section
- "Jobs" header (bold)
- **Filter pills**: Remote, Easy apply, < 10 applicants
- **Job cards** (list): Company logo, job title (bold), company name, location + work type, salary range, school alumni badge + count, "Be an early applicant" (green), time posted, **Bookmark/save icon** (right)
- "Show all job results" link at bottom

## Messaging

### Accessing Messaging
Tap the **Messages icon** (speech bubble with badge) in the top-right of the top bar.

### Message List Screen

**Header:**
- Back arrow (left)
- "Search messages" field (center)
- Three-dot menu
- Compose/new message icon (pencil-in-square, right)

**Filter pills** (horizontal scroll):
"Focused" (selected, green with dropdown arrow), Jobs, Unread, Drafts, InMail

**Focused dropdown** opens a **"Folders"** bottom sheet with 4 folders: Focused (default), Other, Archived, Spam.

**Filter pill behavior:** Selected pills move to second position and turn green. InMail filter removes the "InMail · " prefix from previews. Sponsored messages appear under InMail filter.

**Three-dot menu:** Manage conversations, Set away message, Manage settings.

**Conversation list** (vertically scrolling):
Each row shows:
- Avatar (left) — profile photo or company logo, **green dot** for online contacts
- Name (bold)
- Message preview (truncated) — shows "InMail · " prefix for InMail messages, "Sponsored · " prefix for sponsored messages
- Timestamp (right) — "12:43 pm", "Feb 25", "Jan 12", etc.
- Unread badge — blue circle with number

**Types of messages:**
- Regular DMs: avatar + name + preview
- InMail: "InMail · [subject]" prefix — messages from non-connections
- Sponsored: "Sponsored · [content]" prefix with company/institution logo

### Compose New Message

Accessed via compose icon (pencil-in-square) in message list header.

- **Header**: X close, "New message" title
- **"To:" field** — "Type a name or multiple names" (supports group messaging)
- **Suggested contacts list** — avatars with headlines, shows recent/frequent contacts
- Message body field appears after recipient is selected

### DM Chat Interface

**Header:**
- Back arrow (left)
- Contact name (bold)
- Online status: green dot + "Mobile · 30m ago" or similar
- Three-dot menu (right)
- Star/favorite icon (far right)

**Chat area:**
- Messages appear left-aligned (both sent and received)
- Received messages have avatar + name + LinkedIn badge + timestamp
- Link previews appear as embedded cards (image, title, subtitle, domain)
- Emoji reaction button (smiley face with +) below messages — opens **full iOS emoji picker** (NOT the 6 LinkedIn feed reactions)
- **Read receipt**: Small avatar thumbnail in bottom-right below last message indicates it was seen

**Quick reply suggestions:**
Contextual pill buttons appear at the bottom of the chat based on the last message (e.g., "Home", "At home", "At the office" in response to "Where are u?")

**Input area (bottom):**
- Attachment icon (paperclip, left) — expands 5 options: Send a document, Take a photo or video, Select media from library, Send a GIF, Mention a person. Paperclip changes to X to dismiss.
- "Write a message..." text field (center)
- Microphone icon (right) — voice message

**Conversation three-dot menu** (10 options): Move to Other, Label as Jobs, Mark as unread, Star, Mute, Archive, Create group chat, Report/Block, Delete conversation, Manage settings.

**Tab bar is NOT visible** in the DM chat interface.

### InMail Conversations

InMail has significant UI differences from regular DMs:

- **No online status** in header (senders are typically non-connections)
- **Subject line** displayed in bold above message body
- **Pronouns** shown after name (e.g., "She/Her")
- **Date separators** in centered uppercase
- **Legal fine print** at top (privacy, opt-out, accommodations)
- **Quick reply templates** instead of contextual suggestions: "Yes, interested..." and "No thanks..." (with pencil icons for editing)
- **Send arrow** replaces the microphone icon in input area

## Post Creation

### Accessing the Composer
Tap the **create/compose icon** (pencil-in-square) in the top bar. Opens a full-screen post composer.

### Composer Layout

**Header:**
- **X close** (left) — exits composer. If content was entered, shows action sheet: "Save this post for later?" with Save, Discard (red), Cancel buttons.
- **Profile avatar** — your photo
- **"Anyone" dropdown** — visibility selector, tappable to change audience
- **Clock/schedule icon** — schedule the post for later (see Scheduling below)
- **"Post" button** (right) — grayed out when empty, blue when content is entered

**Text area:**
- Placeholder: "Share your thoughts..."
- Full-screen text editor
- Keyboard appears automatically

**Bottom toolbar** (above keyboard):
- **"Rewrite with AI"** button (sparkle icon) — AI-powered caption rewriting (see below)
- **Hashtag counter** (e.g., "0/20") — tracks hashtags used out of 20 max
- **Image/photo icon** — add media
- **"+" icon** — opens content type picker (replaces keyboard; tapping text area brings keyboard back)

### Rewrite with AI (Full Flow)

1. Type text in the composer
2. Tap "Rewrite with AI" — AI rewrites text in-place (subtle rewording)
3. Below the rewritten text: **"Undo"** button (left) + **thumbs up/down** feedback (right)
4. Can tap "Rewrite with AI" again for another variation
5. Undo reverts to original text

### Scheduling Feature (Clock Icon)

If text was AI-rewritten, tapping the clock icon first shows a warning: **"Schedule without editing?"** with "Schedule" and "Keep editing" buttons.

**Schedule bottom sheet:**
- Date field (pre-filled with today), Time field (pre-filled with nearest time)
- Timezone info (e.g., "UTC-04:00, Eastern Time")
- "View all" link to see scheduled posts
- "Next" button

### Content Type Picker (+ Button)

Grid of circular icons with labels (3 columns):
- **Media** (landscape photo icon) — Add photos/videos
- **Event** (calendar icon) — Create an event
- **Celebrate** (starburst badge icon) — Celebration post (see below)
- **Job** (briefcase icon) — Post a job listing
- **Poll** (bar chart icon) — Create a poll (see below)
- **Document** (document icon) — Upload a document/carousel
- **Services** (storefront icon) — Offer services

### Poll Creation

- "Create a poll" screen: Your question (0/140 chars), Option 1 (0/30 chars), Option 2 (0/30 chars)
- "+ Add option" button for more options
- Poll duration dropdown (default "7 days")
- "Done" button activates when required fields filled

### Celebrate Post Types

Opens "Select an option" screen with 5 types:
1. **Project Launch** — Share a new project milestone
2. **Work Anniversary** — Celebrate a career milestone
3. **New Position** — Share a job update
4. **New Educational Milestone** — Share an educational milestone
5. **New Certification** — Celebrate a new certification

### Visibility Settings

Tapping the "Anyone" dropdown opens a bottom sheet: **"Who can see your post?"**

- **Anyone** (globe icon) — "Anyone on or off LinkedIn" — default, selected with green radio button
- **Connections only** (people icon) — Limit to 1st-degree connections
- **Group** (people icon with arrow) — Post to a specific group

**Additional settings below:**
- **Comment control** — "Anyone" with forward arrow to change who can comment
- **Brand partnership** (info icon) — Toggle, default Off — for sponsored/branded content disclosures

## Profile Page

### Accessing Profiles
Tap an author's avatar or name from a post, comment, search result, or notification.

### Profile Layout (top to bottom)

**Header:**
- Back arrow (left)
- Search field: "I'm looking for..." (center)

**Banner/Cover image** — Full-width photo across the top

**Profile info overlay:**
- **Profile photo** — Large circular avatar, overlapping the bottom of the banner
- **LinkedIn premium badge** (blue "in" icon, right of banner area)
- **Bell/notification icon** (right of banner area) — toggle follow notifications

**Below banner:**
- **Name** (bold, large) with verification badge + connection degree ("1st", "2nd", "3rd+")
- **Headline** — Full professional title/description
- **Company · Education** line
- **Location** (city, state, country)
- **Connection count** — "500+ connections" (green/blue link, tappable)
- **Mutual connections** — Stacked avatars + "[Name], [Name] and N other mutual connections"

**Action buttons:**
- **"Message"** (blue, full-width, paper plane icon) — Primary CTA for 1st-degree connections
- **"..."** more options button (circular, to the right of Message)
- For non-connections: **"Connect"** button appears instead of or alongside Message

### Profile Sections (scrollable)

1. **Highlights** — Career milestones. May include **"Ask about experience"** button (sparkle icon) — AI-powered conversation starter.

2. **Activity** — Follower count. Filter pills: Posts (selected, green), Comments, Images. Shows recent posts with full engagement cards. "Show all" link.

3. **Experience** (count in header) — Each entry: Company logo, job title (bold), company name · employment type, date range · duration, location. "Show all" link.

4. **Education** — Each entry: Institution logo, school name, degree type · field of study, date range.

5. **Licenses & certifications** — Each entry: Issuer logo, certification name, issuer organization, issue date.

6. **Volunteering** — Each entry: Organization logo, title, organization, date range · duration, cause category.

7. **Skills** (count in header) — Each skill: Skill name (bold), endorsement count with people icon, "Endorse" button (outlined). "Show all" link.

8. **Interests** — Filter pills: Top Voices (selected, green), Companies, Groups, Newsletters. Each shows avatar, name, badge, connection degree, title, follower count, "+ Follow" button.

## Navigation Drawer / Profile Sidebar

Opened by tapping the **profile avatar** in the top-left of the top bar. Slides in from the left.

**Layout (top to bottom):**
- **Profile photo** (large circular avatar)
- **Name** (bold) with LinkedIn premium/verification badge
- **Headline** (professional title)
- **Location**
- **"Experience"** button (outlined, dashed border)

Divider

- **"N profile viewers"** (number in green/blue) — tappable
- **"View all analytics"** link

Divider

- **"Puzzle games"** link
- **"Saved posts"** link
- **"Groups"** link

Divider

- **"Settings"** (gear icon) — at the very bottom

**To dismiss:** Tap outside the drawer (on the visible main content) or swipe left.

## Key Workflows

### Browse the Home Feed
```
1. `press_home(phone_id)` → screenshot
2. If **LinkedIn** is visible, tap it; otherwise, swipe left to the App Library and tap its search field to focus it
3. If using App Library search, call `type_text(phone_id, "LinkedIn")`
4. If using App Library search, take a screenshot and verify **LinkedIn** rendered correctly and the intended app result is visible
5. Only if the user explicitly authorized opening LinkedIn and visual verification succeeded, tap that App Library result
6. screenshot → verify LinkedIn opened
7. Home tab should be selected by default
8. Scroll by swiping up from center of screen
9. screenshot → verify the feed loaded without transcribing or summarizing incidental feed, sponsored, profile, recommendation, or personal data
```

### Like a Post
```
1. screenshot → find a post with the Like button visible
2. Tap the "Like" button (thumbs up, bottom-left of action row)
3. screenshot → verify like registered (thumbs up turns blue/filled)
```

### React to a Post (Beyond Like)
```
1. Long press the "Like" button for ~1.5 seconds
2. screenshot → verify reaction picker appeared (6 emoji options)
3. Tap desired reaction (Celebrate, Support, Love, Insightful, Funny)
4. screenshot → verify reaction applied
```

### Comment on a Post
```
1. Tap "Comment" button on the post
2. screenshot → verify comment section opened as bottom sheet
3. Tap the "Leave your thoughts here..." text field to focus it
4. Call `type_text(phone_id, "your comment")`
5. Take a fresh screenshot and verify the intended post and exact comment rendered correctly
6. Present a privacy-minimized preview containing only the intended post or comment and the final comment text
7. Ask for explicit final confirmation and wait
8. Only after confirmation, tap the "Comment" button
9. Take a screenshot and verify the comment appeared
```

### Repost Content
```
1. Tap "Repost" button on the post
2. screenshot → verify repost options appeared
3. Option A: For an instant repost, do not tap the final "Repost" option yet; take a fresh screenshot and verify the intended source post and mode
4. Option B: Tap "Repost with your thoughts", focus the commentary field, call `type_text(phone_id, "your commentary")`, then take a fresh screenshot and verify the exact commentary and attached source post
5. Present a privacy-minimized preview containing only the source post, repost mode, audience, and final commentary, if any
6. Ask for explicit final confirmation and wait
7. Only after confirmation, tap the final "Repost" or "Post" control
8. Take a screenshot and verify the repost appeared
```

### Share a Post via DM
```
1. Tap "Send" button (paper plane) on the post
2. screenshot → verify "Send as message" sheet appeared
3. If the intended recipient is visible, select only that contact
4. Otherwise, tap the recipient search field to focus it, call `type_text(phone_id, "recipient name")`, take a screenshot, verify the intended name and result, and select only that result
5. Take a fresh screenshot and verify the target post, intended recipient, and final message, if any
6. Present a privacy-minimized preview containing only that recipient, post, and final message
7. Ask for explicit final confirmation and wait
8. Only after confirmation, tap the control that sends it
9. Take a screenshot and verify delivery
```

### Create a Text Post
```
1. Tap the compose icon (pencil-in-square) in the top bar
2. screenshot → verify composer opened
3. Tap the text area ("Share your thoughts...") to focus it
4. Call `type_text(phone_id, "your post content")`
5. Set the requested visibility and schedule, if any, without activating the final publication control
6. Take a fresh screenshot and verify the final content, requested media, audience, and schedule
7. Present a privacy-minimized preview containing only those final publication details
8. Ask for explicit final confirmation and wait
9. Only after confirmation, tap the final "Post" or scheduling control
10. Take a screenshot and verify the post was published or scheduled as requested
```

### Search for People
```
1. Tap the Search bar in the top bar
2. screenshot → verify search page appeared
3. Tap the search field if it is not already focused
4. Call `type_text(phone_id, "search query")`
5. screenshot → verify the intended query rendered correctly and autocomplete suggestions appeared
6. Only if the user explicitly authorized running that query and visual verification succeeded, tap a suggestion or "Show all results"
7. If submitted, take a screenshot and verify results with People/Posts/Jobs tabs
8. Tap "People" tab if needed, use filter pills (1st, 2nd, 3rd+)
```

### Search for Jobs
```
1. Tap the Jobs tab in the bottom bar
2. Browse "Top job picks for you" section
3. OR: tap the search bar to focus it
4. Call `type_text(phone_id, "job title or company")`
5. Take a screenshot and verify the intended query rendered correctly and the expected live job results appeared
6. Only if the user explicitly authorized opening a result and visual verification succeeded, tap the intended job card
```

### Connect with Someone
```
1. Find a person (via search, My Network suggestions, or profile)
2. Treat every "Connect" control as potentially sending immediately; do not tap it yet
3. Take a fresh screenshot and verify the intended target
4. If adding a note is available and requested, open only a non-sending review screen, focus the note field, call `type_text(phone_id, "your note")`, then take another fresh screenshot and verify the note
5. Present a privacy-minimized preview containing only the target display name and final note, if any
6. Ask for explicit final confirmation and wait
7. Only after confirmation, tap the control that sends the connection request
8. Take a screenshot and verify the request was sent
```

### Accept Connection Invitations
```
1. Tap "My Network" tab
2. "Grow" sub-tab should be selected by default
3. Locate only the requested invitation; do not summarize other invitations or suggestions
4. Do not tap its checkmark yet
5. Take a fresh screenshot and verify the intended inviter
6. Present a privacy-minimized preview containing only the inviter display name and the "Accept" action
7. Ask for explicit final confirmation and wait
8. Only after confirmation, tap the checkmark for that invitation
9. Take a screenshot and verify it was accepted
```

### Send a Message
```
1. Tap Messages icon (top-right) or "Message" button on a profile
2. If in the message list, open only the intended conversation; for a new message, tap compose, focus the "To:" field, call `type_text(phone_id, "recipient name")`, take a screenshot, verify the intended result, and select only that recipient
3. Tap the "Write a message..." text field to focus it
4. Call `type_text(phone_id, "your message")`
5. Take a fresh screenshot and verify the intended recipient or group and exact message
6. Present a privacy-minimized preview containing only the recipient or group, final message, and requested attachment, if any
7. Ask for explicit final confirmation and wait
8. Only after confirmation, tap send or press return
9. Take a screenshot and verify the message was sent
```

### View a Profile
```
1. Tap an author's avatar or name from a post, search result, or notification
2. screenshot → verify profile page loaded
3. Navigate only to the profile section needed for the user's request
4. Report only the requested profile information; do not summarize unrelated profile, sponsored, recommendation, contact, location, or personal data
5. To go back: tap back arrow (top-left)
```

### Browse Videos
```
1. Tap "Video" tab in the bottom bar
2. Full-screen video appears
3. Swipe up for next video, swipe down for previous
4. Locate the requested right-side action; follow the fresh preview and final-confirmation gate before any comment, message, repost, or publication
```

## Tips and Gotchas

- **Tab bar visibility**: The tab bar hides in DM conversations, post composer, and some full-screen views. Navigate back to reveal it.
- **Dark mode**: LinkedIn uses a dark theme (dark gray/black backgrounds). UI elements are white/gray text with green and blue accent colors.
- **Verification badges**: The blue "in" square badge indicates LinkedIn premium/verification. It appears next to names throughout the app.
- **Connection degrees**: "1st" = direct connection, "2nd" = connected to your connections, "3rd+" = further removed. These appear next to names everywhere.
- **"...more" expansion**: Post text and captions are truncated. Tap "...more" to see full content. There is no "...less" to collapse — once expanded, you'd need to scroll past.
- **Comment section as bottom sheet**: The comment section slides up as a half-sheet. You can drag the handle bar to expand it to near-full screen, or swipe down to dismiss.
- **Reaction picker timing**: Long press the Like button for about 1.5 seconds. The 6 reactions appear as animated emojis in a floating bar. Tap outside to dismiss without reacting.
- **Search context varies by tab**: On the Home tab, search searches everything. On the Jobs tab, the search bar is tailored for job searches. On Notifications, filters like "Jobs" and "My posts" are available.
- **Profile sidebar vs profile page**: Tapping your own avatar opens the left sidebar drawer. Tapping someone else's avatar/name opens their full profile page.
- **InMail messages**: Messages from non-connections appear with "InMail · [subject]" prefix. These are separate from regular DMs.
- **Quick reply suggestions**: In DM conversations, LinkedIn suggests contextual quick-reply pills based on the last message received.
- **Send button = share via DM**: The "Send" action on posts opens a "Send as message" sheet with contact search and external sharing options.
- **Post composer "Rewrite with AI"**: Available in the bottom toolbar of the post composer. AI can rewrite your caption.
- **Video tab layout**: Very similar to TikTok — full-screen vertical video with right-side action buttons. Like uses thumbs up (not heart). No music/sound ticker at the bottom like TikTok.
- **Promoted content**: Sponsored posts and job listings are labeled "Promoted" throughout the app. They appear in the feed, search results, and job recommendations.
- **"Ask about experience" AI feature**: Appears on profile highlights sections. Provides an AI-powered conversation starter about the person's career changes.
- **Multiple message types**: LinkedIn distinguishes between regular DMs, InMail (paid messages to non-connections), and Sponsored messages (from companies/institutions).
