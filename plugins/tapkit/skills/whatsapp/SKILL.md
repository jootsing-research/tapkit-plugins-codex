---
name: whatsapp
description: This skill should be used when the user wants to use WhatsApp, send or read messages, message unsaved phone numbers, search existing chats or message text, start calls, manage statuses/channels, or interact with WhatsApp on their iPhone.
---

# WhatsApp - Messaging App

WhatsApp is a private messaging and calling app with a five-tab bottom bar.

Always use the TapKit loop: screenshot, identify the target, act, then screenshot again.

## TapKit Setup Reminder

Before acting in this app, follow the core TapKit setup: `list_phones()` -> choose `phone_id` -> `get_phone_status(phone_id)`. All TapKit examples in this skill assume every MCP tool call includes that `phone_id`.

For every text-entry action, focus the correct field, call `type_text(phone_id, text)`, then call `screenshot(phone_id)` and visually verify the rendered text. Do not tap Send, Post, Search, Save, Confirm, or an equivalent submission control automatically. Submit only when the user explicitly authorizes the exact action and visual verification succeeds.

## Privacy And Permissions

- Use the narrowest chat, conversation, and query that can satisfy the request. If the conversation is known, open it directly and search within it rather than scanning global chat history.
- Do not read, quote, or summarize unrelated chat titles, message previews, participants, phone numbers, or search results visible on screen.
- Mask unsaved phone numbers in confirmations and model output, showing only enough digits to distinguish the intended recipient (for example, `+1 (***) ***-3448`). Keep the full number on-device and ask the user to review it there when needed.
- Never grant Contacts, Photos or photo-library, Camera, or Microphone access automatically. When a permission prompt appears, stop, explain the exact feature and scope requesting access, and ask for explicit approval before choosing an option. Prefer the least-privileged or selected-item option when available.
- Treat approval for one permission, asset, or action as scoped only to that request. Do not infer approval for other permissions or broader access.

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
4. Tap Search name or number to focus the field.
5. Call `type_text(phone_id, requested_full_number)` with the requested number, keeping the complete value on-device.
6. Call `screenshot(phone_id)` and verify the rendered number and matching formatted result under Not in your contacts.
7. Confirm the intended recipient using a masked number only, and ask the user to review the full number on-device.
8. Only if the user explicitly authorized starting a chat with the masked, verified recipient and verification succeeded, tap the green Chat action on the right.
9. Call `screenshot(phone_id)` and verify the intended chat and recipient opened without transcribing the full unsaved number.
10. Tap the composer to focus it.
11. Call `type_text(phone_id, "Your message")`.
12. Call `screenshot(phone_id)` and verify the masked intended recipient and exact rendered message.
13. Only if the user explicitly authorized sending this exact message and verification succeeded, tap the green send arrow.
14. Call `screenshot(phone_id)` to verify the outgoing bubble.
```

WhatsApp may reformat the entered number with country-code punctuation. Compare the complete value on-device, but use only a masked form in model output.

Important: Tap **Chat**, not **New contact**, if the user wants to message without saving.

## Adding A Contact

New Chat has a New contact row, and number-search results also show New contact under More.

Only use this when the user explicitly wants the number saved. Saving a contact mutates the iOS address book, so verify the name and full number on-device, use a masked number in model output, and request confirmation before saving. If a Contacts permission prompt appears, follow the permission gate above. For normal "message this number" requests, use the unsaved-number Chat result instead.

## Text Entry With TapKit

Focus the destination field before typing text directly:

```
tap(phone_id, x, y)
type_text(phone_id, text)
screenshot(phone_id)
```

Do not tap individual keyboard keys. Use `type_text` only after the intended field is visibly focused.
Do not tap a submission control automatically. Only submit after the user explicitly authorizes the exact action and the screenshot confirms the rendered text.

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

Scope search before opening results:

1. If the user names a conversation, open that exact chat and use its in-chat search for the requested term or date range.
2. Use global chat search only when the target conversation is unknown or the user explicitly requests a cross-chat search.
3. Use the narrowest distinctive query and stop once the requested match is found. Do not continue browsing earlier or later messages without a request-specific reason.
4. Ignore and do not report unrelated chat rows, message previews, participants, or media surfaced by search.

The Chats search field starts with media filters:

- Photos
- GIFs
- Links
- Videos
- Documents
- Audio
- Polls
- Events

To find an existing chat by number when the conversation cannot be opened directly:

```
1. Tap Ask Meta AI or Search.
2. Tap the search field to focus it.
3. Call `type_text(phone_id, text)` with the narrowest useful number fragment supplied by the user.
4. Call `screenshot(phone_id)` and verify the rendered query and intended result under Chats without transcribing unrelated results.
5. Confirm the intended result using a masked number only.
6. If the user asked to resume the verified conversation, tap the matching result row.
```

If no result appears, adjust only within the user's requested scope: try fewer digits, remove punctuation, use another user-supplied fragment, or search distinctive requested message text. Do not broaden into an indiscriminate chat-history scan.

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
- Photo-access prompt. Do not grant access without the explicit, scoped permission required above.
- Settings rows: Lists, Starred, Broadcast messages, Linked devices, Account, Privacy, Chats, Notifications, Storage and data, Help and feedback, Invite a friend, Meta Accounts Center.
