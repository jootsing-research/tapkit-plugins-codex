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

## Use Tools First, Navigate Second

Always prefer a direct tool over manual navigation:

- **Opening apps**: call `open_app(phone_id, "Settings")` — don't scroll through home screens looking for the icon
- **Searching the phone**: call `spotlight(phone_id, "calculator")` — don't swipe down and hunt visually
- **Going home**: call `press_home(phone_id)` — don't swipe up from the bottom

Only use tap/swipe navigation for things **inside** an app where no tool shortcut exists.

## Core Loop

Your workflow is always: **screenshot → look → act → screenshot to verify**.

1. Take a `screenshot(phone_id)` to see what's on screen
2. Visually identify the element you need to interact with
3. Estimate the pixel coordinates of its **center**
4. Call the appropriate tool (tap, swipe, copy_text_to_phone, etc.)
5. Take another `screenshot` to confirm the action worked
6. If it didn't work, try a different approach

**Always screenshot before and after actions.** You have no other way to see the phone — no accessibility tree, no DOM, no element selectors. Everything is visual + coordinates.

## Coordinate System

Screenshots are resized so you see them at the same resolution as the coordinate space. **Coordinates map 1:1 with screenshot pixels** — if an element is at pixel (300, 672) in the image, tap (300, 672). Screen dimensions are returned by `list_phones` (typically around 618x1344).

- (0, 0) is the top-left corner
- x increases rightward, y increases downward
- Aim for the **center** of UI elements — iOS touch targets can be small
- The status bar is roughly the top 47px, the home indicator bar is the bottom ~37px

## Tools Quick Reference

### Navigation
- `open_app(phone_id, app_name)` — Open any app by name (e.g. "Settings", "Safari", "Hinge")
- `press_home(phone_id)` — Go to home screen
- `spotlight(phone_id, query?)` — Open Spotlight search, optionally type a query

### Touch Gestures
- `tap(phone_id, x, y)` — Single tap. Use for buttons, links, icons, list items
- `double_tap(phone_id, x, y)` — Double tap. Use for zooming or text selection
- `long_press(phone_id, x, y, duration?)` — Tap and hold. Opens context menus. Default 1000ms
- `swipe(phone_id, x, y, direction)` — Fast flick gesture at a point. Direction: "up", "down", "left", "right". Use for dismissing, switching pages, scrolling
- `drag(phone_id, from_x, from_y, to_x, to_y)` — Drag from one point to another. Use for sliders, precise scrolling, moving items
- `hold_and_drag(phone_id, from_x, from_y, to_x, to_y, hold_duration_ms?)` — Long press then drag. Use for drag-and-drop, reordering lists

### Input
- `copy_text_to_phone(phone_id, text)` — Load text onto the phone's clipboard for pasting into text fields (see **Text Input** section below)
- `activate_siri(phone_id)` — Trigger Siri voice assistant
- `escape(phone_id)` — Dismiss keyboards, alerts, popups, or modal screens

### Device
- `list_phones()` — List all phones with connection status, IDs, and dimensions. **Call this first.**
- `screenshot(phone_id)` — Get current screen as an image
- `get_phone_status(phone_id)` — Get real-time status: connection, screen lock, streaming, dimensions
- `get_phone_info(phone_id)` — *(Deprecated — use `get_phone_status` instead.)* Returns screen dimensions and phone name
- `lock(phone_id)` / `unlock(phone_id)` — Lock or unlock the screen
- `volume_up(phone_id)` / `volume_down(phone_id)` — Volume controls
- `run_shortcut(phone_id, index)` — Run an iOS Shortcut by its index number

## iOS Navigation Tips

- **Scroll down**: `swipe(phone_id, 300, 672, "down")` — flick downward from screen center
- **Go back** in an app: look for a "< Back" arrow in the top-left and tap it, or `swipe(phone_id, 10, 672, "right")` (left-edge swipe)
- **Dismiss a modal/popup**: look for "X", "Cancel", "Done", or tap outside it
- **Pull to refresh**: `drag(phone_id, 300, 200, 300, 600)` (drag down from top of content area)
- **Switch apps**: `swipe(phone_id, 300, 1300, "up")` (swipe up from bottom)
- **Close keyboard**: call `escape(phone_id)`, tap anywhere outside the keyboard, or `press_home(phone_id)`
- **Tab bars** at the bottom of apps are the main navigation — tap the icons to switch sections
- **iOS alerts** (permissions, confirmations) appear as centered popups — tap "Allow", "OK", etc.

## Text Input

TapKit cannot press individual keyboard keys reliably. Instead, typing is done via the **clipboard**: load text with `copy_text_to_phone`, then paste it into a text field using iOS's paste UI.

### Typing into an Empty/Inactive Text Field

1. **Load text onto the clipboard:** `copy_text_to_phone(phone_id, "Your message here")`
2. **Long press on the text field** for ~1500ms. This activates the field, brings up the keyboard, and shows the **Paste** tooltip: `long_press(phone_id, x, y, duration: 1500)`
3. **Tap "Paste"** in the tooltip that appears above the text field
4. **Screenshot to verify** the text was pasted correctly
5. To submit: tap the blue button on the keyboard (it says "Search", "Go", "Send", or "Done" depending on context). It's usually in the bottom-right area of the keyboard

### Replacing Existing Text

To replace text already in a field, use the **Select All + Paste** workflow:

1. **Load new text onto the clipboard:** `copy_text_to_phone(phone_id, "New text")`
2. **Double-tap on any word** in the text field to select it: `double_tap(phone_id, x, y)`
3. **Tap on an unhighlighted part** of the text field (a different spot from the selected word) — this shows the menu with **Select All**: `tap(phone_id, x, y)`
4. **Tap "Select All"** to highlight everything
5. **Tap "Paste"** to replace all selected text with clipboard contents

### Clearing a Text Field

Use **Select All + Cut**:
1. Double-tap a word to select it
2. Tap on unhighlighted text to get the "Select All" option
3. Tap "Select All"
4. Tap "Cut"

### Text Selection Reference

| Action | Result | Menu shown |
|--------|--------|------------|
| `double_tap` on a word | Selects that word | Format, Cut, Copy, Paste, > |
| `tap` on unhighlighted text (while a selection exists) | Deselects, places cursor, shows basic menu | Paste, Select, Select All, AutoFill |
| `long_press` (~1500ms) on inactive text field | Activates field + keyboard, shows paste tooltip | Paste, AutoFill |

### Text Input Pitfalls

- **Don't try to tap individual keyboard keys.** The timing and precision required makes this unreliable. Always use the clipboard approach.
- **Don't simulate triple-tap with three separate `tap` calls.** The calls are too far apart in time. Use the double-tap + tap-on-unhighlighted-text pattern instead.
- **Long-pressing backspace is unreliable.** It deletes characters at an unpredictable rate. Prefer Select All + Cut/Paste.
- **Always screenshot after typing actions** to verify the result before proceeding.

## Common Patterns

**Opening an app:**
```
open_app(phone_id, "Settings") → screenshot(phone_id) to verify it opened
```

**Searching within an app:**
```
copy_text_to_phone(phone_id, "query") → long_press(phone_id, x, y, 1500) → tap "Paste" → tap Search button on keyboard → screenshot
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
- **Apps take 1-2 seconds to load.** If a screenshot looks unchanged after tapping an app icon, take another screenshot — it may still be loading
- **If something doesn't work after 2-3 tries, try a different approach.** Don't keep tapping the same spot
- **You cannot handle Face ID, CAPTCHAs, or biometric prompts.** Tell the user if you encounter these
- **Don't type passwords** unless the user explicitly provided them in their request
