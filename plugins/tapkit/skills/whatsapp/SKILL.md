---
name: whatsapp
description: This skill should be used when the user wants to use WhatsApp, send or read messages, message unsaved phone numbers, search existing chats or message text, start calls, manage statuses/channels, or interact with WhatsApp on their iPhone.
---

# WhatsApp - Messaging App

WhatsApp is a private messaging and calling app. On TJ's iPhone 12 Mac Mini, it uses a dark interface and a five-tab bottom bar.

Always use the TapKit loop: screenshot, identify the target, act, then screenshot again. Prefer pasting text via the phone clipboard over tapping individual keyboard keys.

## TapKit Setup Reminder

Before acting in this app, follow the core TapKit setup: `list_phones()` -> choose `phone_id` -> `get_phone_status(phone_id)`. All TapKit examples in this skill assume every MCP tool call includes that `phone_id`.

## Bottom Tabs

The bottom tab bar has five icons, ordered left to right:

| Tab | Relative position | Purpose |
|-----|-------------------|---------|
| Updates | Leftmost icon | Status posts and channels |
| Calls | Second icon from the left | Call history, call links, and number dialing |
| Communities | Center icon | Topic-based group containers |
| Chats | Second icon from the right, speech-bubble icon | Conversation list and new messages |
| You | Rightmost icon, person/profile icon | Profile, QR code, and settings |

Tap the icon glyph rather than the label when switching tabs. The Chats icon is the speech-bubble icon between Communities and You.

## Chats

Chats is the main workflow surface.

Top controls:

- **... top-left**: menu with Select chats and Read all.
- **Camera top-right**: opens capture/media.
- **Green + top-right**: opens New Chat.
- **Ask Meta AI or Search**: global search across chats, message text, and media.

Chat rows show avatar, title, timestamp, and message preview. Unsaved-number chats are titled with the formatted phone number.

## Messaging An Unsaved Number

Use this when the user wants to message someone without saving them as a contact.

```
1. Open WhatsApp.
2. Go to Chats.
3. Tap the green +.
4. Tap Search name or number.
5. Copy the number to the phone clipboard.
6. Long-press near the search-field caret and tap Paste.
7. Under Not in your contacts, verify the formatted number.
8. Tap the green Chat action on the right.
9. Paste the message in the composer.
10. Verify recipient and message text.
11. Tap the green send arrow.
12. Screenshot to confirm the outgoing bubble.
```

Observed number behavior:

- `9544960433` becomes `+1 (954) 496-0433`.
- `+13109683448` becomes `+1 (310) 968-3448`.

Important: Tap **Chat**, not **New contact**, if the user wants to message without saving.

## Adding A Contact

New Chat has a New contact row, and number-search results also show New contact under More.

Only use this when the user explicitly wants the number saved. Saving a contact mutates the iOS address book, so verify the name and number before saving. For normal "message this number" requests, use the unsaved-number Chat result instead.

## Pasting With TapKit

Use clipboard paste for text entry:

```
copy_text_to_phone(phone_id, text)
Tap the target field.
Long-press near the caret.
Tap Paste.
Screenshot to verify.
```

In New Chat, the paste menu was reliable after focusing the search field and long-pressing near the caret at the left side of the field. The Paste option appears in the iOS edit menu just below the search field.

Do not tap individual keyboard keys for phone numbers unless no paste path is available.

## Chat Screen

Header:

- Back arrow.
- Avatar.
- Contact name or phone number.
- Video-call icon.
- Voice-call icon.

Body:

- Date chip such as Today.
- Encryption banner.
- Message bubbles.

Composer:

- `+` attachment button.
- Text field.
- Sticker icon.
- Camera icon.
- Microphone icon.

When text is entered, the microphone changes to a green send arrow. Outgoing messages are green, right-aligned, and show timestamp plus check marks.

## Search

The Chats search field starts with media filters:

- Photos
- GIFs
- Links
- Videos
- Documents
- Audio
- Polls
- Events

To find an existing chat by number:

```
1. Tap Ask Meta AI or Search.
2. Paste a full or partial phone number.
3. Look under Chats.
4. Tap the result row to resume the conversation.
```

Observed search for `954` found `+1 (954) 496-0433` with preview `Emily: TapKit WhatsApp test`.

If no result appears, try fewer digits, remove punctuation, search the formatted number, or search distinctive message text.

## Calls

Calls tab:

- Green + opens New call.
- New Call options: New call link, Call a number, New contact, Schedule call.
- Call a number opens a dial pad.

Do not place calls unless explicitly requested.

## Updates

Updates contains:

- Status section with Add status, camera, and pencil buttons.
- Recent updates.
- Channels, topic chips, and follow suggestions.

Do not post status or follow channels unless requested.

## Communities

Communities has an empty-state screen with:

- Green + top-right.
- See example communities.
- Large green + New community button.

Do not create communities unless requested.

## You

You is profile/settings:

- Search icon.
- QR code icon.
- Profile card.
- Photo-access prompt.
- Settings rows: Lists, Starred, Broadcast messages, Linked devices, Account, Privacy, Chats, Notifications, Storage and data, Help and feedback, Invite a friend, Meta Accounts Center.
