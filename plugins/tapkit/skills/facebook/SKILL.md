---
name: facebook
description: Use this skill when the user wants to browse Facebook, react to posts, use Marketplace, or send messages from the Facebook app on iPhone.
---

# Facebook

Open Facebook with `open_app("Facebook")`, then take a screenshot before acting. Facebook changes often, so trust icon shapes and visible labels over memorized coordinates.

Use the `tapkit` skill's text-entry flow for comments, searches, and messages.

## Main Navigation

Common bottom tabs include:

- `Home`
- `Reels`
- `Marketplace`
- `Notifications`
- `Menu` or profile-related tabs

The exact order can vary by app version.

## Common Tasks

### Browse the Feed

1. Go to `Home`.
2. Scroll with short upward swipes.
3. Tap a post to open details if needed.

### React or Comment

1. Open the post.
2. Tap the reaction or comment control.
3. Paste comment text if the user wants to reply.
4. Confirm the comment posted.

### Use Marketplace

1. Open `Marketplace`.
2. Tap the search field or category shortcuts.
3. Paste the search query if needed.
4. Open a listing and inspect price, location, and seller details.

### Open Messages

1. Look for `Messenger`, `Chats`, or a message icon from the top bar or menu.
2. Open the conversation.
3. Use clipboard paste to send a message.

## Gotchas

- Facebook uses many sheets and overlays. Always verify whether you are still inside a composer or a modal.
- Marketplace and comments frequently trigger iOS text popovers before the field is truly active.
- Tabs can be replaced by shortcuts depending on account state or experiments.
