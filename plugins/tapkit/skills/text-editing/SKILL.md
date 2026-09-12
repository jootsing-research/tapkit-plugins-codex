---
name: text-editing
description: "Edit text precisely on an iPhone, including cursor placement, selection, replacement, deletion, and recovery from awkward iOS editing states."
---

# iOS Text Editing

Work from the phone's visible state. Inspect before and after each edit because the keyboard, menus, scrolling, and app layout can move the text.

## Approach

- Focus the intended field and confirm whether it shows a caret or a selection.
- Enter text in short chunks, then check the rendered value and caret position.
- Avoid Search, Send, Go, or similar controls unless submission is intended.
- If an action fails or times out, inspect the field before retrying; part of the edit may have succeeded.

## Edit Text

- Double-tap a word to select it.
- Extend a selection by dragging its handles. The starting handle is on the left edge and the ending handle is on the right. Colors vary by app and theme.
- For multiline selections, make small handle adjustments and verify each result.
- When deleting words, include one neighboring space when needed so the remaining text keeps normal spacing.
- Drag a visible caret directly when precise character placement is needed.
- To select everything, long-press an existing caret and choose **Select All**. If the first press only moves the caret, press the new caret again.
- Replace a verified selection by typing. Use **Cut** or an app's **Delete** action to remove it; use **Copy** and **Paste** only after checking the current selection or caret.

## Recover and Verify

- Selection commonly excludes terminal punctuation and may split at hyphens or decimal points, while contractions usually stay together. Always inspect the highlight.
- Double-tapping a misspelling may open a correction suggestion instead of selecting it.
- Some search fields select their whole value when activated or update suggestions as soon as text changes.
- Tapping highlighted text can reopen a hidden editing menu. Double-tap a known word to reset an awkward range.
- If the selection will not clear, dismiss the keyboard and refocus the field.
- When the screen scrolls or reflows, discard old coordinates and locate the text again.
