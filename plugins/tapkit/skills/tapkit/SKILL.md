---
name: tapkit
description: Use this skill when the user wants to control a physical iPhone through TapKit, take phone screenshots, tap or swipe on the screen, open apps, type via clipboard paste, or automate mobile workflows.
---

# TapKit

You can control a physical iPhone through TapKit MCP tools. Treat the phone as a visual environment: you only know what is on screen by taking screenshots and then acting on what you see.

## Setup

- If only one phone is connected, start using TapKit tools directly.
- If multiple phones are connected, call `list_phones` and pass `phone_id` on every tool call.
- Do not rely on `select_phone` persisting across later calls.

## Use Tools First

Prefer direct tools over manual navigation whenever a tool exists:

- Use `open_app("App Name")` instead of hunting for icons.
- Use `press_home` instead of trying to gesture back to the home screen.
- Use `spotlight("query")` instead of manually opening search.
- Use `get_phone_info` when you need screen dimensions.

Only fall back to coordinate-based navigation inside apps.

## Core Loop

Your default loop is:

1. Take a `screenshot`.
2. Identify the element you need.
3. Interact with its center point.
4. Take another `screenshot` to verify the result.

Always capture a screenshot before and after meaningful actions. Do not assume a tap worked.

## Coordinate Model

- Coordinates map 1:1 to screenshot pixels.
- `(0, 0)` is the top-left corner.
- `x` increases to the right and `y` increases downward.
- Aim for the center of buttons, tabs, list rows, and text fields.

## Tool Reference

### Navigation

- `open_app(app_name)`
- `press_home`
- `spotlight(query?)`

### Touch

- `tap(x, y)`
- `double_tap(x, y)`
- `long_press(x, y, duration?)`
- `swipe(x, y, direction)`
- `drag(from_x, from_y, to_x, to_y)`
- `hold_and_drag(from_x, from_y, to_x, to_y, hold_duration_ms?)`

### Input

- `copy_text_to_phone(text)`
- `activate_siri`

### Device

- `screenshot`
- `get_phone_info`
- `lock`
- `unlock`
- `volume_up`
- `volume_down`
- `run_shortcut(index)`

## Text Input

Typing should generally use the clipboard workflow, not individual key taps.

### Standard Paste Flow

1. Call `copy_text_to_phone("text to enter")`.
2. Long-press the target text field for roughly 1500 ms.
3. Tap `Paste` in the iOS text menu.
4. Take a screenshot to verify the text landed correctly.
5. Tap the relevant submit button such as `Search`, `Go`, `Send`, or `Done`.

### Replacing Existing Text

1. Copy the replacement text with `copy_text_to_phone`.
2. Double-tap a word in the field.
3. Tap again in the field to expose text actions.
4. Choose `Select All`.
5. Tap `Paste`.

### Avoid

- Do not rely on typing individual keyboard keys unless there is no other option.
- Do not keep retrying the same failed tap sequence without re-screenshoting.
- Do not type passwords unless the user explicitly gave them to you.

## Common Patterns

- Open an app: `open_app(...)` -> `screenshot`
- Search inside an app: copy text -> long-press field -> `Paste` -> submit -> `screenshot`
- Scroll a feed or list: `swipe` or `drag` -> `screenshot`
- Dismiss a modal: tap `X`, `Cancel`, `Done`, or outside the sheet -> `screenshot`
- Go back: tap a visible back button or try a left-edge rightward swipe

## Safety and Limits

- Tell the user if you hit Face ID, biometrics, CAPTCHAs, or permissions they must handle.
- App screens may take a second to load. If the first verification screenshot looks stale, wait briefly and capture another.
- If an approach fails two or three times, change tactics instead of repeating it.
