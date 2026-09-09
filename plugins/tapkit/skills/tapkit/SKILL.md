---
name: tapkit
description: This skill should be used when the user wants to "control my iPhone", "take a screenshot of my phone", "tap on the screen", "open an app", "type on my phone", or interact with a physical iPhone through TapKit MCP tools.
---

# TapKit — iPhone Control

You have access to a physical iPhone through TapKit MCP tools. You can see the screen via screenshots and interact through taps, swipes, typing, and other gestures.

## Setup

**Every phone-targeting MCP tool requires a `phone_id`.** Always start by calling `list_phones` to discover available phones. It returns IDs, connection status, Mac connection, and screen dimensions.

MCP tools use named arguments. Examples in this skill may use compact shorthand like `tap(phone_id, x, y)`, but the actual MCP call should pass an args object such as `{"phone_id": "...", "x": 300, "y": 672}`.

```
list_phones() -> choose phone_id -> get_phone_status(phone_id) -> use phone_id on every call
```

### REST API Equivalents

Use the REST API with `https://api.tapkit.ai/v1` and the `X-API-Key` header:

| Intent | MCP call | REST API call |
|--------|----------|---------------|
| List available phones | `list_phones()` | `GET /phones` |
| Check connection status | `get_phone_status(phone_id)` | `GET /phones/{phone_id}/status` |

## Use Direct Tools When Available

- **Going home**: call `press_home(phone_id)` instead of swiping up from the bottom
- **Entering text**: focus the field, call `type_text(phone_id, text)`, then screenshot and verify the rendered text. Stop before submission.
- **Opening apps**: call `press_home`, take a screenshot, and tap the app icon. If the icon is not visible, swipe left through the Home Screen pages to App Library, tap its search field, enter the app name with `type_text`, screenshot and verify it, then tap the matching result.

Use screenshot-guided tap/swipe navigation for everything else.

## Core Loop

Your workflow is always: **screenshot → look → act → screenshot to verify**.

1. Take a `screenshot(phone_id)` to see what's on screen
2. Visually identify the element you need to interact with from its current visible label, icon, and surrounding context
3. Estimate the pixel coordinates of its **center**
4. Call the appropriate tool (`tap`, `swipe`, `type_text`, etc.)
5. Take another `screenshot` to confirm the action worked
6. If it didn't work, try a different approach

**Always screenshot before and after actions.** You have no other way to see the phone — no accessibility tree, no DOM, no element selectors. Everything is visual + coordinates.

**Never reuse remembered tap points or assume the interface is unchanged.** Targets come from the current screenshot, not from earlier ones or from memorized coordinates.

## Coordinate System

Screenshots are resized so you see them at the same resolution as the coordinate space. **Coordinates map 1:1 with screenshot pixels** — if an element is at pixel (300, 672) in the image, tap (300, 672). Screen dimensions are returned by `list_phones` (typically around 618x1344).

- (0, 0) is the top-left corner
- x increases rightward, y increases downward
- Aim for the **center** of UI elements — iOS touch targets can be small
- The status bar is roughly the top 47px, the home indicator bar is the bottom ~37px

## Tools Quick Reference

### Navigation
- `press_home(phone_id)` — Go to home screen

### Touch Gestures
- `tap(phone_id, x, y)` — Single tap. Use for buttons, links, icons, list items
- `double_tap(phone_id, x, y)` — Double tap. Use for zooming or text selection
- `long_press(phone_id, x, y, duration?)` — Tap and hold. Opens context menus. Default 1000ms
- `swipe(phone_id, x, y, direction)` — Fast flick gesture at a point. Direction: "up", "down", "left", "right". Use for dismissing, switching pages, scrolling
- `drag(phone_id, from_x, from_y, to_x, to_y)` — Drag from one point to another. Use for sliders, precise scrolling, moving items
- `hold_and_drag(phone_id, from_x, from_y, to_x, to_y, hold_duration_ms?)` — Long press then drag. Use for drag-and-drop, reordering lists

### Input
- `type_text(phone_id, text)` — Type text into the currently focused field; screenshot and verify the rendered text before any next action

### Device
- `list_phones()` — List all phones with connection status, IDs, and dimensions. **Call this first.**
- `screenshot(phone_id)` — Get current screen as an image
- `get_phone_status(phone_id)` — Get real-time status: connection, screen lock, streaming, dimensions
- `lock(phone_id)` / `unlock(phone_id)` — Lock or unlock the screen

## iOS Navigation Tips

- **Scroll down**: `swipe(phone_id, 300, 672, "down")` — flick downward from screen center
- **Go back** in an app: look for a "< Back" arrow in the top-left and tap it, or `swipe(phone_id, 10, 672, "right")` (left-edge swipe)
- **Dismiss a modal/popup**: look for "X", "Cancel", "Done", or tap outside it
- **Pull to refresh**: `drag(phone_id, 300, 200, 300, 600)` (drag down from top of content area)
- **Switch apps**: `swipe(phone_id, 300, 1300, "up")` (swipe up from bottom)
- **Close keyboard**: tap a visible keyboard-dismiss control or an area outside the text field. Use "Done" only when it clearly dismisses the keyboard without submitting the field.
- **Tab bars** at the bottom of apps are the main navigation — tap the icons to switch sections
- **iOS alerts** (permissions, confirmations) appear as centered popups — tap "Allow", "OK", etc.

## Text Input

Use this contract for every text-entry workflow:

1. **Focus the correct field.** Tap it and screenshot to verify focus.
2. **Enter the text.** Call `type_text(phone_id, text)`.
3. **Verify the rendered text.** Take a screenshot and inspect the complete value, destination field, and any truncation or autocorrection.
4. **Stop before submission.** Do not automatically tap Search, Send, Post, Save, Done, or any equivalent control. Submission must be a separate step that the user explicitly authorized, and only after the rendered text is correct.

### Typing into an Empty/Inactive Text Field

1. **Tap the text field:** `tap(phone_id, x, y)`
2. **Screenshot** to verify the field is focused and the keyboard is visible
3. **Type the text:** `type_text(phone_id, "Your message here")`
4. **Screenshot** to verify the text was entered correctly
5. **Stop before submission.** Only use the keyboard action or app submit control as a separate, explicitly authorized step after verification.

### Replacing Existing Text

To replace text already in a field:

1. **Double-tap a word** in the text field: `double_tap(phone_id, x, y)`
2. **Tap an unhighlighted part** of the text field to show the menu with **Select All**: `tap(phone_id, x, y)`
3. **Tap "Select All"** to highlight everything
4. **Type the replacement:** `type_text(phone_id, "New text")`
5. **Screenshot** to verify the selected text was replaced
6. **Stop before submission.** Do not confirm or save the change automatically.

### Clearing a Text Field

Use **Select All + Cut**:
1. Double-tap a word to select it
2. Tap on unhighlighted text to get the "Select All" option
3. Tap "Select All"
4. Tap "Cut"
5. Screenshot to verify the field is empty
6. Stop before confirming or saving the change

### Text Selection Reference

| Action | Result | Menu shown |
|--------|--------|------------|
| `double_tap` on a word | Selects that word | Format, Cut, Copy, and more |
| `tap` on unhighlighted text (while a selection exists) | Deselects, places cursor, shows basic menu | Select, Select All, AutoFill |
| `tap` on an inactive text field | Activates the field | Keyboard appears |

### Text Input Pitfalls

- **Don't try to tap individual keyboard keys.** The timing and precision required makes this unreliable. Use `type_text`.
- **Don't simulate triple-tap with three separate `tap` calls.** The calls are too far apart in time. Use the double-tap + tap-on-unhighlighted-text pattern instead.
- **Long-pressing backspace is unreliable.** It deletes characters at an unpredictable rate. Prefer Select All, then `type_text` or Cut.
- **Always screenshot after typing actions** to verify the result before proceeding.

## Common Patterns

**Opening an app:**
```
press_home(phone_id) → screenshot(phone_id) → tap the Settings icon → screenshot(phone_id) to verify
```

**Searching within an app:**
```
tap(phone_id, x, y) on the search field → screenshot to verify focus → type_text(phone_id, "query") → screenshot and verify rendered query → stop before Search unless explicitly authorized
```

**Scrolling through a list:**
```
swipe(phone_id, 300, 672, "down") → screenshot(phone_id) → look for target → repeat if needed
```

**Handling a popup/alert:**
```
screenshot(phone_id) → identify the popup → tap(phone_id, x, y) on the appropriate button (Allow, OK, Cancel, etc.)
```

## Important

- **Be precise with coordinates.** Off by 50px can mean tapping the wrong element
- **Always verify with screenshots.** Never assume an action succeeded
- **Never combine text entry with submission.** Verify rendered text first; submit only as a separate, explicitly authorized action
- **Apps take 1-2 seconds to load.** If a screenshot looks unchanged after tapping an app icon, take another screenshot — it may still be loading
- **If something doesn't work after 2-3 tries, try a different approach.** Don't keep tapping the same spot
- **You cannot handle Face ID, CAPTCHAs, or biometric prompts.** Tell the user if you encounter these
- **Don't type passwords** unless the user explicitly provided them in their request
