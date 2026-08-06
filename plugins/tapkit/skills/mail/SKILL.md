---
name: mail
description: Use Apple Mail on an iPhone to search or read relevant email, compose or reply, and manage drafts or messages safely. Use for requests involving Mail inboxes, mailbox search, email drafting, replies, sending, or deletion.
---

# Apple Mail

Use current screenshots and visible labels to navigate. Do not rely on saved coordinates, a particular device, account, mailbox configuration, theme, or previously observed screen state.

## Setup and text entry

Start with `list_phones()`, choose the intended `phone_id`, and call `get_phone_status(phone_id)`. Include that `phone_id` in every phone-targeting tool call.

For every text-entry action:

1. Focus the correct field.
2. Call `type_text(phone_id, text)`.
3. Call `screenshot(phone_id)` and verify the exact rendered text in the intended field.
4. Stop before Search, Send, Save, Return, or any equivalent submission action.
5. Perform that action only as a separate step after the user explicitly authorizes the exact action and visual verification succeeds.

Do not use clipboard or paste workflows for text entry.

## Absolute authentication boundary

- Never open, tap, or follow authentication, login, sign-in, password-reset, magic-link, confirmation, or verification links.
- Never read, copy, transcribe, summarize, reveal, enter, or submit verification codes, one-time passwords, recovery codes, or equivalent authentication secrets.
- Never help complete an authentication or account-verification flow through Mail. If a request reaches this boundary, explain that the action cannot be performed and stop without exposing the sensitive content.

These rules are absolute even when the user asks directly.

## Privacy and scope

- Search only the narrowest mailbox scope necessary for the request. Begin in the current mailbox when appropriate; widen to another named mailbox or all mailboxes only when required by the user's request.
- Use the minimum sender, subject, date, or keyword criteria needed to identify the target message.
- Open only a message that is relevant to the request. If relevance is uncertain, ask the user before opening it.
- Never summarize, transcribe, or mention unrelated senders, subjects, notifications, message previews, search results, or message contents visible on screen.
- Mask email addresses in summaries unless the user specifically needs the full address. For example, render `person@example.com` as `p***@example.com`.
- Do not move, archive, flag, mark, forward, reply to, or otherwise modify a message unless the user explicitly requests that action.

## Open Mail

1. Call `press_home(phone_id)` and then `screenshot(phone_id)`.
2. Locate Mail from the current screenshot by its visible icon or label and tap it.
3. If Mail is not visible, navigate to the App Library, focus its search field, call `type_text(phone_id, "Mail")`, and call `screenshot(phone_id)` to verify the rendered query and intended app result.
4. Tap the verified Mail result and call `screenshot(phone_id)` to confirm that Mail opened.

## Search and read

1. Navigate to the narrowest relevant mailbox using current labels.
2. Check whether a filter is active. Change it only if necessary for the requested search.
3. Focus Mail's search field, call `type_text(phone_id, query)`, and call `screenshot(phone_id)`.
4. Verify the rendered query and selected mailbox scope. Do not report unrelated rows visible in the screenshot.
5. Ask for authorization to run the verified search unless the user has already authorized that exact query and scope after seeing them.
6. Run the search only after authorization, then call `screenshot(phone_id)`.
7. Identify the requested result without describing unrelated results. Open it only when its relevance is clear and opening it does not cross the authentication boundary.
8. Summarize only the content needed to answer the user's request, masking addresses unless the full address is specifically needed.

If no result appears, refine the query within the same scope before widening the mailbox scope. Explain why a wider scope is needed before using it.

## Compose a new message

1. Open a new compose sheet using the currently visible Compose control.
2. Focus **To**, call `type_text(phone_id, recipient)`, and call `screenshot(phone_id)` to verify the rendered recipient.
3. Focus **Subject**, call `type_text(phone_id, subject)`, and call `screenshot(phone_id)` to verify the rendered subject.
4. Focus the body, call `type_text(phone_id, body)`, and call `screenshot(phone_id)` to verify the complete rendered body.
5. Review **To**, **Cc/Bcc** when present, **Subject**, and the final body. Resolve any ambiguity before proceeding.
6. Show the user the exact recipient, subject, and final body, then request final confirmation to send. The user's initial request to send or draft the message is not final send confirmation.
7. Do not tap Send until the user confirms after seeing that final preview.
8. After confirmation, re-check that the composer is unchanged, tap Send, and call `screenshot(phone_id)` to verify the result.

The final send preview may include the full recipient address because the user must verify the exact destination. Continue masking addresses in unrelated summaries.

## Reply to a message

1. Open only the relevant message and choose Reply only when requested.
2. Verify the intended thread and recipient without reporting unrelated visible content.
3. Focus the reply body, call `type_text(phone_id, reply)`, and call `screenshot(phone_id)` to verify the complete rendered reply.
4. Show the user the exact recipient, subject or thread, and final reply body, then request final confirmation to send. An earlier request to reply is not final send confirmation.
5. Do not tap Send until the user confirms after seeing that final preview.
6. After confirmation, re-check that the reply is unchanged, tap Send, and call `screenshot(phone_id)` to verify the result.

## Drafts

- Preserve a draft by default. Do not discard a draft merely because it was opened for inspection.
- Before saving a prepared draft, verify its recipient, subject, and body and obtain authorization for the Save action.
- Before deleting or discarding any draft, show which draft will be affected and request confirmation immediately before deletion. An initial request to delete is not final confirmation.
- If deletion is not confirmed, leave the draft unchanged or save it only with authorization.

## Delete a message

1. Identify the exact message using only the minimum relevant sender, masked address, subject, and date information.
2. Show the user which message will be deleted and request confirmation immediately before deletion. An initial deletion request is not final confirmation.
3. Do not tap Trash, Delete, or an equivalent control until that confirmation is received.
4. After confirmation, delete only the identified message and call `screenshot(phone_id)` to verify the result without reporting unrelated inbox content.

## Guardrails

- Treat Send and Delete as consequential actions that always require the just-in-time confirmations above.
- Treat Reply All and Forward as distinct actions; never infer either from a request to reply.
- Dismiss or leave account-level prompts unchanged unless the user explicitly asks to change that setting and the action does not cross the authentication boundary.
- If the current screen, mailbox scope, recipient, or target message is ambiguous, stop and ask rather than acting on a guess.
