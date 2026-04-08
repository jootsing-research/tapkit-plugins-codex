---
name: hinge
description: This skill should be used when the user wants to use Hinge, swipe on dating profiles, like or pass on someone, send a rose, message matches, browse Hinge Discover feed, or interact with the Hinge dating app on their iPhone.
---

# Hinge — Dating App

Hinge is a dating app focused on meaningful connections. Users browse profiles, like or pass, add comments to specific photos/prompts, and message matches. This skill teaches you Hinge's UI layout and interaction patterns.

## App Structure

### Tab Bar (bottom of screen)

Hinge has 5 tabs along the bottom navigation bar, evenly spaced left to right:

1. **Discover** (Hinge logo "H") — Main feed — browse and like/pass profiles
2. **Standouts** (Star) — Premium profiles that stand out (requires roses)
3. **Likes You** (Heart) — People who liked you (blurred without premium)
4. **Matches** (Chat bubble) — Your matches and conversations
5. **Profile** (Person icon) — Your own profile, settings, preferences

Take a screenshot and tap the appropriate icon along the bottom edge to switch tabs.

**The tab bar is not always visible.** When you've scrolled down into a profile, a conversation, or any detail view, the tab bar hides to give more screen space. If you need to switch tabs and don't see the tab bar, scroll back up to the top of the current view — the tab bar will reappear at the bottom. Alternatively, you can tap the back arrow (top-left) to return to the parent screen where the tab bar is visible.

## Discover Feed (Main Screen)

The Discover feed shows one profile at a time as a scrollable card. Each profile contains multiple sections stacked vertically — photos, prompts, and basic info.

### Profile Card Layout

- **Profile cards scroll vertically** — swipe/flick up to see more of the current profile
- Each card has a mix of **photos** and **prompt responses** (text cards with a prompt header in small text and the answer in large text)
- The **person's name** appears at the top center of the screen
- A **"..." menu** button is in the top-right corner for reporting/removing

### Interacting with Profile Content

Each photo and prompt has a **heart icon** in the top-right corner of that content piece. Tap it to like that specific photo or prompt — this is more engaging than a generic like.

To **add a comment** on a specific photo or prompt:
1. `copy_text_to_phone("your comment")` to load the text onto the clipboard
2. `long_press(x, y, duration: 1500)` on the **"Add a comment"** text field below the content piece — this activates the field, brings up the keyboard, and shows the **Paste** tooltip
3. Tap **"Paste"** in the tooltip
4. Tap **"done"** on the keyboard or look for a send button

**AI-suggested comment chips**: Hinge sometimes shows suggestion chips below prompts in the like panel (e.g., "Compare debate styles", "Ask her best comeback"). These are tappable shortcuts that auto-fill a comment. You can tap one to use it, or ignore them and type your own comment.

### Like / Pass Actions

At the bottom of the profile card (above the tab bar), you'll see action buttons:

- **Rose button** (left side) — purple/rose icon with a number showing your remaining roses. Tap to send a rose (premium like that gets priority)
- **Send Priority Like** or **Like** button (right side) — pink/rose-colored button to like the profile. **This button's position is dynamic** — its y-coordinate shifts depending on content above it (comment field, suggestion chips, etc.). Always re-check the button position after dismissing the keyboard — it may have shifted.

**Warning: Only tap in the like panel area — do not swipe.** Swiping up near the like panel will dismiss it and scroll the profile instead. If the panel disappears, tap the heart icon on a content piece to re-open it.

To **pass** on a profile:
- Tap the **X button** if visible, OR
- Simply scroll past all their content and the next profile loads automatically
- There is no prominent "pass" button on the content view — passing happens by scrolling through without liking

### Scrolling Through a Profile

- **Swipe up** to see more of the current person's profile (more photos, prompts)
- Keep scrolling past all their content to load the next profile
- Profile sections alternate between photos and prompt responses

## Likes You Tab

- Shows profiles of people who have liked you
- **Without premium**: photos are blurred, you can see the number of likes
- **With premium**: you can see all profiles and choose to match or pass
- Each profile shows a preview — tap to see the full profile

## Matches & Messages Tab

- **Top section**: New matches (profile photos in a horizontal row you can scroll through)
- **Below**: Active conversations sorted by most recent
- Conversations are grouped under collapsible sections like **"Your Turn"** and **"Their Turn"**. If you see "Your Turn (3)" but no messages listed below it, the section is collapsed. Tap on it to expand and reveal the conversations. You can tell if a section is collapsed or expanded by the arrow on that row (pointing down = expanded, pointing up = collapsed)
- Tap a match to open the conversation

### Messaging

- Messages appear in a chat bubble layout (yours on right, theirs on left)
- **Text input** is at the bottom of the screen
- To send a message: `copy_text_to_phone("your message")` → `long_press(x, y, duration: 1500)` on the input field → tap **"Paste"** in the tooltip → tap the **send button** (arrow icon, right side of input)
- You can also send GIFs, photos, and voice notes via icons near the input field
- **To leave a conversation**: call `escape` to go back to the conversations list

### Messaging Tone

When composing messages, **match the vibe of the person you're talking to.** Read their previous messages and mirror their energy, humor, and style. If they're playful, be playful. If they're chill and lowercase, keep it casual.

Rules:
- **Never use em dashes** (—). Use commas, periods, or just break into separate messages instead
- Keep messages short and natural. Nobody sends paragraphs on dating apps
- Use lowercase if they do. Don't over-capitalize or over-punctuate
- Don't be overly formal or stiff. Sound like a real person texting
- Ask questions to keep the conversation going, but don't interrogate

## Profile Tab

- Shows your own profile as others see it
- **Edit** button or tap on sections to modify photos, prompts, basic info
- **Settings** gear icon (top corner) for preferences, filters, account settings
- **Preferences** section lets you set age range, distance, dealbreakers

## Key Workflows

### Browse and Like Profiles
```
1. screenshot → verify you're on Discover tab
2. Scroll through the profile to see photos and prompts
3. To like a specific photo/prompt: tap the heart icon on that content
4. To add a comment: copy_text_to_phone("...") → long_press the "Add a comment" field (1500ms) → tap "Paste" → send
5. To send a rose: tap the rose button (left side)
6. To pass: keep scrolling past all content, next profile loads
7. screenshot → verify next profile loaded
```

### Send a Thoughtful Like (with comment)
```
1. Scroll through profile to find a photo or prompt you want to comment on
2. copy_text_to_phone("your witty comment here")
3. long_press on "Add a comment" below that content (duration: 1500)
4. Tap "Paste" in the tooltip
5. Tap send/done
6. screenshot to verify the like was sent
```

### Check and Respond to Matches
```
1. Tap the Matches tab (4th icon from left in the bottom tab bar)
2. screenshot → see matches and conversations
3. Tap on a conversation to open it
4. copy_text_to_phone("your message")
5. long_press on the message input field at the bottom (duration: 1500)
6. Tap "Paste" in the tooltip
7. Tap send button
8. screenshot to verify
```

## Tips and Gotchas

- **Loading time**: After liking/passing, the next profile takes 1-2 seconds to load. Take a screenshot after a brief pause if the screen looks transitional
- **"We've run out of people"**: If you see this screen, the user has gone through all available profiles. Suggest adjusting distance/age preferences or waiting
- **Premium prompts**: Hinge frequently shows upgrade prompts (Hinge+, HingeX). These appear as full-screen overlays — look for an "X" or "No thanks" to dismiss them
- **Rose limit**: Free users get 1 rose per week. The rose button shows the count. Don't send roses without the user's explicit approval
- **Comment before liking**: Adding a comment to a specific photo/prompt is Hinge's signature feature and leads to better matches. Suggest this to users when appropriate
- **Profile order matters**: The first photo and first prompt are what most people see. When editing profiles, prioritize these
- **Daily limits**: Free users have a limited number of likes per day. If likes run out, Hinge will show a "Come back tomorrow" message
- **Keyboard dismissal**: After typing a comment, if the keyboard blocks action buttons, tap outside the text field or press home and reopen the conversation
- **Unresponsive "Send Priority Like" recovery**: If the "Send Priority Like" button doesn't respond after 2 taps, dismiss the like panel and re-trigger it from a different content piece (another photo or prompt). This is more reliable than repeatedly tapping the same button.
