---
name: telegram
description: This skill should be used when the user wants to use Telegram, send or read messages, browse chats, join groups or channels, interact with bots, make calls, search conversations, or interact with the Telegram app on their iPhone.
---

# Telegram — Messaging App

Telegram is a messaging app with chats, groups, channels, and bots. Users send messages, share media, join group conversations, interact with bots, and manage contacts. This skill teaches you Telegram's UI layout and interaction patterns.

## App Structure

### Tab Bar (bottom of screen)

Telegram has 5 tabs along the bottom navigation bar, evenly spaced left to right:

1. **Contacts** — All contacts alphabetically with search, sort, invite friends, and add (+) button
2. **Calls** — Call history with All/Missed toggle filter and "Start New Call" link
3. **Chats** — Main chat list — where 90% of interaction happens
4. **Settings** — Profile, account settings, preferences
5. **Search** (magnifying glass) — Global search across chats, contacts, messages. Shows FAQ when empty

## The Chats Tab (Most Important)

### Top Bar
- **"Edit" button** (top-left) — for bulk editing/selecting chats
- **Camera button** (top-right area) — **THIS IS A CAMERA, NOT NEW MESSAGE!** Opens a quick camera with Live/Video/Photo modes. Do NOT tap this when trying to compose a new message.
- **Compose button** (pen icon, far top-right) — THIS is how you start a new message. Opens a screen with: New Group, New Contact, New Channel, plus a searchable contact list with alphabet scrubber on right edge.

### Chat Filter Tabs (horizontally scrollable, below top bar)

The filter row sits just below the top bar. Swipe left/right to reveal more tabs.
- **All** — shows every conversation (DMs, groups, channels, bots)
- **Personal** — only 1-on-1 DMs (has count badge like "133")
- **Unread Group** — only groups with unread messages (has count badge)
- **Custom folders** — user-created folders (e.g., "Work", "Photobooth"). These vary per account.

**Important:** To switch filters, tap the tab name. If you can't see a tab, swipe left on the tab row to reveal more. There can be 8+ tabs.

### Chat List Items

Each chat in the list shows:
- Avatar (left), chat name, timestamp (right)
- Preview of last message with sender name for groups
- Unread count badge on right — **blue** for unmuted, **gray** for muted
- Heart/reaction emoji if the last message was reacted to
- Muted chats show a speaker-off icon next to the name

## Four Types of Chats (Different UIs!)

### 1. Direct Messages (1-on-1)
- **Header**: "< [count]" back button (left), contact name + "last seen recently/within a week/etc" status (center), their profile photo (right)
- **Messages**: Outgoing = purple bubbles on right side with double checkmarks (single check = sent, double check = read). Incoming = dark bubbles on left side.
- **Bottom bar**: Paperclip (attachments), "Message" text field, timer icon (disappearing messages), **microphone icon** (right — for voice messages)
- Date separators appear between days. An "Unread Messages" divider shows where new messages start.

### 2. Group Chats
- **Header**: "< [count]" back button, group name + "N members, N online" (center), group icon (right)
- **Pinned message banner** may appear at top — shows pinned content with a manage button
- **Messages show sender names** in colored text, plus role badges like "owner"
- Emoji reactions appear below messages with reaction counts
- **Bottom bar**: Paperclip, "Message" field, timer, **camera icon** (NOT microphone — different from DMs!)
- Tap the group name in the header to open **Group Info** page

### 3. Bot Chats
- **Header**: Bot name + "N monthly users" (instead of last-seen), bot icon (right)
- May have a **sponsored ad banner** at the top (dismissible with X)
- Bot messages tend to be rich: formatted text, images, inline links
- **Bottom bar**: Has a unique **"≡ Menu" button** on the left! This opens the bot's command menu. Then paperclip, "Message" field, timer, microphone
- May show "Reply to [BotName]" prompt

### 4. Channels / Restricted Groups (Read-Only)

Channels look like groups in the chat list but are read-only for non-admin users.

**How to identify a channel:** Once you open it, the bottom of the screen shows **"Sending messages is not allowed in this group."** instead of a message input bar. There is NO paperclip, NO message field, NO microphone/camera.

- **Header**: Same as groups — "< [count]" back button, channel name + "N members, N online", channel icon
- **Pinned message banner** at top (same as groups)
- **Messages show sender names** with **"admin" badges** (green text) — note: groups use "owner" badges, channels use "admin"
- **System messages** for pin actions: "Edgar pinned 'MTNDAO WEEK 4 R...'" appears as a centered gray system message
- **Link previews** are embedded inline (e.g., X/Twitter card previews with image thumbnails)
- **Emoji reactions** with counts (e.g., fire 8, heart 9) appear below messages
- **Share button** (arrow icon) on the right side of messages — for forwarding
- **Star icon** next to timestamps — indicates channel posts vs regular messages
- **No message input bar** — replaced with "Sending messages is not allowed in this group." text

| Feature | Regular Group | Channel/Restricted Group |
|---------|--------------|-------------------------|
| Can send messages | Yes | No — "Sending messages is not allowed" |
| Bottom bar | Paperclip + Message field + timer + camera | Gray text only |
| Role badges in chat | "owner" | "admin" |
| Info page tabs | Members, Media, Files, Voice, Links | Members, Media, Links, GIFs |
| Timestamp icon | None | Star icon next to time |
| System messages | Join/leave notifications | Pin notifications ("X pinned 'Y'") |

**Important for agents:**
- **Don't try to send messages in channels** — there's no input field. Check for the "Sending messages is not allowed" text before attempting any message actions.
- **Forwarding/sharing is the main interaction** — use the share (arrow) button on messages.
- **Reacting is still possible** — long-press messages to add emoji reactions.

## Group Info Page

Opened by tapping the group name in the header.

- Group avatar, name, member count + online count
- **Action buttons row**: mute, search (within group), leave, more (...)
- **Tabs**: Members, Media, Files, Voice, Links (and possibly GIFs)
- Members list shows names with role badges and last-seen status
- "Add Members" link at top of members list

## Channel Info Page

Opened by tapping the channel name in the header. Similar to Group Info but with different tabs.

- Channel avatar, name, member count + online count
- **Action buttons**: mute, search, leave, more (...) — same as groups
- **Tabs**: Members, Media, Links, GIFs (differs from groups which have Files and Voice instead of GIFs)
- Members list shows **"admin"** and **"owner"** badges (both green)
- "Add Members" link at top of members list

## Saved Messages

Accessible from Settings > Saved Messages. Acts like a personal chat with yourself.

- **Header**: "< [count]" back button, "Saved Messages" title, search icon (magnifying glass, right)
- Has a full message input bar — good for agents to use as a scratch pad or test area
- Has a search icon in top-right instead of a profile photo

## Message Checkmarks

These appear in the chat list preview AND inside chats:
- **Single checkmark** (✓) = sent but not delivered
- **Double checkmark** (✓✓) in gray = delivered
- **Double checkmark** (✓✓) in blue/green = read by recipient

## Context Menus (Long Press)

### Long-press a Chat (from the chat list)

Shows a mini preview of the chat with these actions:
- **Add to Folder** — move to a chat folder
- **Mark as Unread** — toggle read/unread status
- **Pin** — pin chat to top of list
- **Mute** — silence notifications
- **Delete** — remove chat (red, destructive)

### Long-press a Message (inside any chat)

Shows the message highlighted with:
- **Quick emoji reaction bar** at top: heart, fire, crying, thumbs up, thumbs down, love face, clap plus an expand button for more emoji
- Reaction count + who reacted (if any)
- **Reply** — reply to this specific message
- **Copy** — copy message text
- **Pin** — pin message in chat
- **Forward** — forward to another chat/contact
- **Report** — report the message
- **Delete** — delete message (red)
- **Select** — enter multi-select mode for multiple messages

## Settings Menu

Accessed via Settings tab. Profile section at top shows avatar, name, phone number, username. Then:
- My Profile, Wallet (NEW)
- Saved Messages, Recent Calls, Devices, Chat Folders
- Notifications and Sounds, Privacy and Security, Data and Storage, Appearance, Power Saving, Language
- Telegram Premium, My Stars, Telegram Business, Send a Gift
- Ask a Question, Telegram FAQ, Telegram Features

## Search System

Telegram has multiple search entry points and a rich filtering system for finding chats, contacts, messages, and media.

### Search Entry Points

There are 4 ways to search in Telegram:

1. **Chats tab search bar** — below the "Chats" header and above the chat filter tabs. Tapping it opens the full global search interface.
2. **Search tab** (magnifying glass, rightmost bottom tab) — opens the SAME search interface as #1. They're identical.
3. **In-chat search** — from any chat's Info page. Tap the chat/group name in the header → tap the "search" action button. Opens a "Search this chat" field overlaid on top of the conversation.
4. **Contacts search** — on the Contacts tab (leftmost bottom tab), there's a search bar below the header. Simpler search that only finds contacts and global users.

### Global Search Interface (Entry Points 1 & 2)

**Before typing (default state):**
- A horizontal row of **frequent contacts** (circular avatars, scrollable left/right)
- A **RECENT** section showing previous search items, with a "Clear" link on the right to clear history
- **Filter tabs** at the bottom of the results area

**After typing a query:**
Results appear in organized sections:

1. **RECENT** — previously searched items that match the query
2. **CHATS AND CONTACTS** — local chats and contacts matching the name
3. **GLOBAL SEARCH** — public Telegram channels, bots, and groups from the directory. Each shows:
   - Avatar, name, @handle (in blue), subscriber/member count
   - Verified accounts show a blue checkmark next to name
   - A **"Show More" / "Show Less"** toggle link on the right to expand/collapse results
4. **MESSAGES** — message content matches across all chats. Each shows:
   - Chat avatar, chat name, sender name (for groups), timestamp
   - Message preview with the search term in **bold**
   - Tapping a message result navigates directly to that message in the conversation

### Message Filter Dropdown

In the MESSAGES section header, there's a **"From All Chats"** dropdown (with arrows). Tapping it opens a popover with 4 filter options:
- **All Chats** — messages from everywhere (default)
- **Private Chats** — only DM/1-on-1 messages
- **Group Chats** — only group conversation messages
- **Channels** — only channel messages

The dropdown label updates to reflect the selection (e.g., "From Group Chats").

### Search Filter Tabs (10 total)

Below the search results, there's a horizontally scrollable row of filter tabs. There are **10 tabs total** — swipe left to reveal later ones:

1. **Chats** — default view with all result sections (contacts, global, messages)
2. **Channels** — only GLOBAL SEARCH results for public channels/groups
3. **Apps** — searches for Telegram Mini Apps and bots. Shows a detective duck illustration on empty state.
4. **Posts** (has a "NEW" badge) — searches public channel posts. **Premium-only feature** — non-Premium users see a "Subscribe to Premium" prompt.
5. **Media** — photo/video grid (3 columns) of shared media across chats. Shows ALL recent media when no query is entered.
6. **Downloads** — searches downloaded files
7. **Links** — messages containing URLs. Shows message text, URL in blue, and breadcrumb path like "sender > chat name" to show origin.
8. **Files** — searches shared documents
9. **Music** — searches shared audio/music files
10. **Voice** — searches voice messages

### Chat-Specific Filter Pills

When searching on the Chats tab, small **filter pills** (chips) appear at the bottom of results showing matching chats. Tapping one adds a blue chip inside the search field to narrow all results to that specific chat. The chip has an X button to remove the filter.

### In-Chat Search

Accessible from: open a chat → tap the name in the header → tap "search" action button on the Info page.

- The search field shows **"Search this chat"** as placeholder (different from global search)
- Messages in the chat remain visible behind the search overlay
- Two filter icons appear below the search field on the left:
  - **Calendar + magnifying glass** icon = search by date
  - **Person + magnifying glass** icon = search by specific member/sender
- Results navigate directly to matching messages within the conversation

### Contacts Search

Simpler than global search. Shows only two sections:
1. **CONTACTS** — matching local contacts with name and last-seen status
2. **GLOBAL SEARCH** — matching public Telegram users with name and @handle

No filter tabs, no message search — just people.

### Search Tips and Gotchas

- **The Search tab and Chats search bar are identical** — don't waste time trying both, they open the same interface
- **"Show More" in GLOBAL SEARCH reveals many more results** including international channels — useful for finding niche content
- **The "From All Chats" dropdown is powerful** — use it to narrow message results by chat type (DMs vs groups vs channels)
- **Posts search requires Telegram Premium** — this feature is gated
- **Media tab works without a query** — shows a browsable grid of all shared media even before you type anything
- **Links tab shows breadcrumbs** — "sender > chat name" format makes it easy to trace where a link came from
- **Tapping a search result navigates to it** — message results jump directly to that message in the chat, useful for finding context
- **In-chat search has date and member filters** — the two icons below the search field let you narrow by when something was said or who said it
- **Filter tabs are horizontally scrollable** — only the first 5-6 are visible initially, swipe left to reveal Downloads, Links, Files, Music, Voice

## Key Workflows

### Send a Message to an Existing Chat
```
1. Tap the Chats tab (3rd tab from left in bottom bar)
2. screenshot → verify chat list visible
3. Tap on the desired chat in the list
4. copy_text_to_phone("your message")
5. long_press(x, y, duration: 1500) on the "Message" text field at the bottom
6. Tap "Paste" in the tooltip that appears above the field
7. Tap the send button (appears where microphone/camera was, bottom-right)
8. screenshot → verify message sent
```

### Start a New Message
```
1. Tap the Chats tab
2. Tap the compose button (pen icon, top-right) — NOT the camera button next to it
3. screenshot → verify contact list / compose screen
4. Search for or select a contact
5. copy_text_to_phone("your message") → long_press on the "Message" field (1500ms) → tap "Paste" → tap send
```

### Browse Chat Filters
```
1. On Chats tab, look at the filter row below the top bar
2. Tap "All" for all chats, or "Personal" for DMs only
3. Swipe left on the filter row to reveal more custom folders
4. Tap desired folder tab
5. screenshot → verify filtered chat list
```

### React to a Message
```
1. Inside a chat, long_press on the message you want to react to
2. screenshot → verify reaction bar appears at top
3. Tap desired emoji (heart, fire, thumbs up, etc.)
4. screenshot → verify reaction applied
```

### Reply to a Specific Message
```
1. Inside a chat, long_press on the message
2. Tap "Reply" from the context menu
3. copy_text_to_phone("your reply")
4. long_press on the "Message" field (1500ms) → tap "Paste"
5. Tap send
```

### Search Globally
```
1. Tap the Search tab (5th/rightmost tab in bottom bar)
2. copy_text_to_phone("query")
3. long_press on the search field (1500ms) → tap "Paste" in the tooltip
4. screenshot → verify results
```

### Search Within a Group
```
1. Open the group chat
2. Tap the group name in the header to open Group Info
3. Tap the "search" action button
4. copy_text_to_phone("search query")
5. long_press on the "Search this chat" field (1500ms) → tap "Paste"
6. screenshot → verify results
```

### View Group Info
```
1. Open the group chat
2. Tap the group name in the header (top center)
3. screenshot → verify group info page with members, media tabs
```

## Tips and Gotchas

- **The camera button is NOT compose** — it's a camera! The compose/new message button is the pen icon to the right of it. This will trip up agents who assume the camera icon = new message.
- **Bottom-right icon changes by chat type**: Microphone in DMs, Camera in groups, Microphone in bot chats. When you start typing, all change to a Send arrow.
- **The back button shows unread count** — the "< 689" back button in chats shows the total unread count for the chat list. Useful for knowing how many unreads exist without going back.
- **Muted vs unmuted unread badges** — Blue badges = unmuted unreads (important). Gray badges = muted unreads. Prioritize blue badges.
- **Filter tabs are horizontally scrollable** — "All" and "Personal" are visible by default, but there can be 8+ tabs. Swipe the tab row to find custom folders.
- **Bot chats have a unique "≡ Menu" button** — No other chat type has this. It's specific to bot interactions and opens the bot's command palette.
- **Sponsored ads can appear** in bot chats — They have a "what's this?" label and X dismiss button. Dismiss these to avoid confusion.
- **The Search tab** immediately opens the keyboard and shows FAQ by default. Just start typing — no need to tap the search field first since it auto-focuses.
- **Navigation back**: Tap the "< [count]" back button in the top-left or swipe right from the left edge of the screen.
- **Channels are read-only** — they look like groups in the chat list but have no message input. Check for "Sending messages is not allowed" text before trying to send. Forwarding and reacting are the main interactions.
- **Message checkmarks**: Single ✓ = sent, double ✓✓ gray = delivered, double ✓✓ blue = read. These show in chat list previews and inside chats.
