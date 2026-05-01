---
name: mail
description: This skill should be used when the user wants to use Apple Mail on their iPhone, receive or search email, inspect Craigslist verification or reply messages, compose email, manage drafts safely, or interact with Mail as part of another app workflow.
---

# Apple Mail — iOS Email App

Apple Mail is the default iOS email client. On TJ's iPhone it is configured with an iCloud mailbox and uses the system dark appearance. This skill focuses on workflows needed for Craigslist account/posting verification, receiving mail, finding messages, composing, and avoiding accidental account or send actions.

**Always take a screenshot after each action to verify what's on screen.** Use visible labels, icons, and spatial relationships rather than memorized tap positions.

Do not record or repeat the user's full email address in manuals, logs, or summaries unless the user explicitly asks.

## Current State

Observed configured state:

- Mail opens to an iCloud **Inbox**.
- The inbox initially contained a system-generated iCloud welcome email.
- A one-time prompt appeared asking whether to add the mail address for iMessage and FaceTime. Choose **No** unless the user explicitly asks to change that Apple account behavior.
- Gmail was not installed; Spotlight showed Gmail only as an App Store result.

## Global Safety Rules

- Do not tap the send arrow unless the user explicitly asks to send and the recipient, subject, and body have been verified.
- Do not tap confirmation links, copy verification codes, reveal codes, or open posting-management links unless the user explicitly asks.
- Do not trash, move, flag, mark, reply, reply all, forward, or archive messages unless the user explicitly asks.
- Avoid opening unrelated personal messages. Use sender and subject snippets to identify only the relevant message.
- If a non-empty draft was opened only for inspection, close it and choose **Delete Draft** unless the user asks to keep it.
- If an account-level prompt appears, choose the privacy-preserving or dismissive option unless the user asks to change account behavior.

## Mailboxes Screen

Tap the top-left back button from an inbox to reach **Mailboxes**.

Observed layout:

| Element | Purpose |
|---------|---------|
| **Mailboxes** title | Root mailbox list |
| **Updated Just Now** | Last refresh indicator |
| **Edit** | Customize mailbox list |
| **Inbox** | All inbox mail; badge count shows unread messages |
| **VIP** | Messages from VIP contacts |
| **iCloud** section | Account-specific mailboxes |
| Compose icon | New message |

Only the basic iCloud mailbox structure was visible during this pass.

## Inbox

The inbox screen shows:

- Top-left back button to **Mailboxes**.
- Inbox title, such as **Inbox iCloud**.
- Updated/unread subtitle below the title.
- **Select** button for multi-select actions.
- Top-right **...** menu.
- Message list.
- Bottom controls with filter, search, and compose actions.

Unread messages have a blue dot beside the row.

## Filtering

Tap the bottom-left filter icon.

Observed behavior:

- The icon turns blue.
- A pill appears: **Filtered by Unread**.
- The inbox list changes to show only matching messages.

Tap the filter icon or the filter pill to manage or disable filtering. If an expected verification email is missing, check whether the inbox is filtered to unread only.

## Search

Tap the bottom search control.

Search behavior:

- Keyboard appears.
- Search can scope to **All Mailboxes** or **Current Mailbox** using the segmented control above results.
- Typing a term shows structured suggestions:
  - **Sender contains: [term]**.
  - **Subject contains: [term]**.
  - **Attachment name contains: [term]**.
- Press the keyboard search key or choose a suggestion to run the query.
- If no results are visible, clear the query and check mailbox/filter state.

Useful Craigslist-related search terms:

- `craigslist`
- `robot`
- `confirm`
- `posting`
- `verification`

## Compose

Tap the compose icon in the lower area of the inbox or Mailboxes screen.

Observed compose sheet:

- Title: **New Message**.
- Top-left **X** closes the draft.
- Top-right send arrow is disabled until required fields are populated.
- A **Send Later** tip card can appear; it says touch and hold Send to schedule.
- **To:** row, with a **+** contact picker beside it.
- **Cc/Bcc, From:** row showing the configured iCloud sender.
- **Subject:** row.
- Message body, often prefilled with **Sent from my iPhone**.

If a draft is empty, tapping **X** dismisses it without a discard confirmation. If text has been entered, expect a save/discard prompt.

Do not tap the send arrow unless the user explicitly asks to send and the recipient, subject, and body have been verified.

### Craigslist Reply Drafts

When Craigslist opens Mail from listing **reply -> email**, the compose sheet may already contain:

- A Craigslist relay-style recipient.
- The listing title as the subject.
- The Craigslist listing URL in the body.
- The normal Mail signature.

The body field is usually focused, and the send arrow may already be available. To inspect safely, tap **X** and choose **Delete Draft**. Choose **Save Draft** only if the user asks to keep it.

After sending from a Craigslist compose sheet, Mail may return to a previously open Mail message instead of returning to Craigslist. If the user wants to keep browsing or replying to listings, reopen Craigslist directly.

### Craigslist Listing Replies

Incoming replies can show in the iCloud inbox as `craigslist [listing id]` or from a Craigslist relay-domain sender. Reply subjects can use `Re: [listing title]`.

Search alert emails can look similar but are labeled **CL Search Alerts** and use subjects like `(# new results) [saved search name]`.

If a poster asks for screening details such as direct email address, pets, number of residents, or current housing status, summarize the ask for the user. Do not provide direct personal contact details or extra screening details unless the user approves the reply content.

## Message Detail

Tap a message row to open a message.

Observed controls:

| Control | Purpose |
|---------|---------|
| Top-left back | Return to inbox |
| Top-right up/down arrows | Previous/next message |
| Trash icon | Delete message |
| Folder icon | Move message |
| Reply arrow | Opens action sheet |
| Compose icon | New message |

### Reply Action Sheet

Tap the reply arrow at the bottom.

Observed options:

- Reply.
- Reply All.
- Forward.
- Trash.
- Remind Me.
- Flag.
- Mark as Unread.
- Move Message.
- Move to Junk.

Do not choose any action from this sheet unless the user explicitly asks.

## Craigslist Verification Email Workflow

Use this flow when Craigslist sends a confirmation, account signup, posting, or verification email.

```
1. Open Mail -> screenshot to verify current screen
2. If in a message or compose sheet, close/back out to the inbox
3. Turn off filters if the expected email is missing
4. Tap search and search All Mailboxes for craigslist
5. If there are no results, try robot, confirm, posting, or verification
6. Open only the Craigslist-related email
7. Look for a confirmation link, code, or posting-management link
8. Stop unless the user explicitly asked to tap the link, use the code, or continue the verification flow
```

### Observed Craigslist Account Signup Email

Observed during Craigslist posting exploration:

- The email arrived immediately after tapping **send me a link** in Craigslist.
- Sender was a Craigslist automated sender.
- Subject/snippet indicated **craigslist account sign-up** and **complete account sign-up**.
- Message contained a prominent **complete account sign-up** button.
- Tapping that button returned to Craigslist and opened the next account setup screen.
- The message also included **didn't request this link?**; do not tap it unless the user wants to cancel/report the signup.

## Key Workflows

### Find A Craigslist Email

```
1. open_app("Mail") -> screenshot
2. Navigate to Inbox if needed
3. Disable unread filtering if active
4. Tap search
5. Search All Mailboxes for craigslist
6. Open only a matching Craigslist sender/subject row
7. screenshot -> verify the message is relevant before acting
```

### Inspect A Craigslist Reply Draft Safely

```
1. From Craigslist, tap reply -> email only when the user wants email contact
2. screenshot -> verify Mail compose opened
3. Review recipient type, subject, and body without recording private details
4. Tap X
5. Choose Delete Draft unless the user asks to send or save
6. Reopen Craigslist if Mail does not return automatically
```

### Compose A New Email

```
1. Tap compose
2. Fill To, Subject, and Body with user-approved content
3. screenshot -> verify recipient, subject, and body
4. Tap send only after explicit user instruction
5. screenshot -> verify the compose sheet closed or message sent
```

### Reply To A Message

```
1. Open the relevant message
2. Tap the reply arrow
3. Choose Reply only if the user asked to reply
4. Paste user-approved reply content
5. screenshot -> verify recipient/thread and body
6. Tap send only after explicit user instruction
```

## Tips And Gotchas

- Apple Mail may show account-level prompts, such as adding the address to iMessage/FaceTime. Avoid changing those settings unless requested.
- A bottom-left filter can hide messages; check for **Filtered by Unread** if a message seems missing.
- The send button is an arrow in the top-right of compose and may become active as soon as Mail thinks required fields are valid.
- Empty compose drafts close immediately, but non-empty drafts may prompt to save or discard.
- Search suggestions are not final results. Press the keyboard search key or choose a suggestion to run a search.
- Craigslist replies and search alerts can share the same Craigslist icon in the inbox; use sender and subject snippets to avoid opening the wrong item.
- Avoid opening unrelated personal messages. Search narrowly and verify sender/subject before opening.
