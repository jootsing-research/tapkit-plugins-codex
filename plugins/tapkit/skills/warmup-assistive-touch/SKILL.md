---
name: warmup-assistive-touch
description: Warm up AssistiveTouch and place the iPhone in a stable state by opening two approved Apple system apps, exercising a drag inside the first app and a slight drag on the Home Screen, returning home between apps, and announcing and verifying progress. Use when the user says "warm up AssistiveTouch", "do the AssistiveTouch warmup", "warm up the phone", or asks to prepare the phone for reliable agent control.
---

# Warm up AssistiveTouch

Run the seven phases in order. Before each phase, give the user a concise progress update such as **Warm-up 3/7: dragging inside Settings**. After each phone action, use `wait` for 1,000 milliseconds, inspect the fresh screenshot, and verify the expected screen before continuing. Announce the phase, not every corrective tool call.

## Approved apps

Prefer **Settings** as the first app and **App Store** as the second app when their icons are visible. Safe alternatives are **Weather**, **Clock**, and **Tips**. The second app must be different from the first.

Do not open communication apps, personal-data apps, Camera, Photos, Wallet, Passwords, Health, or third-party apps during this warm-up.

## Navigation and Home recovery

Use `drag`, never `flick`, for every navigation gesture during the warm-up. Make navigation drags deliberate and long: start in visible open space and travel about 60–75% of the screen in the intended direction. The short drag in phase 5 is an AssistiveTouch exercise, not a navigation gesture.

After any `home` action or the phase 5 drag, inspect the fresh screenshot. A normal Home page must show the dock and an app or widget layout without a keyboard, folder, menu, editing controls, App Switcher, or system overlay.

If a single `home` action does not reach a normal Home page, or the phase 5 drag leaves the phone on another Home surface:

1. Do not issue another `home` action.
2. Load the `tapkit-ios-home-navigation` skill.
3. Follow that skill to classify the visible surface and recover to a normal Home page. Implement its directional flicks with the long `drag` gesture described above, never with `flick`.
4. Verify the normal Home page, then resume the current warm-up phase.

## Sequence

1. Announce **Warm-up 1/7: going to the Home Screen**. Use `home` once, wait, and verify that the Home Screen app grid is visible. If it is not, use **Navigation and Home recovery**.
2. Announce **Warm-up 2/7: opening [first app]**. Tap a visible approved app, wait, and verify that the selected app is open.
3. Announce **Warm-up 3/7: dragging inside [first app]**. Use a vertical `drag` inside the app's content area, near the horizontal center, from about 80% down the screen to about 20% down the screen. Never use `flick`. Wait and verify that the app remains open and settled.
4. Announce **Warm-up 4/7: returning to the Home Screen**. Use `home` once, wait, and verify that the Home Screen app grid is visible. If it is not, use **Navigation and Home recovery**.
5. Announce **Warm-up 5/7: making a slight Home Screen drag**. Use `drag`, never `flick`, for a short horizontal gesture of approximately one app-icon spacing, about 15–20% of the screen width. Keep the gesture within the Home Screen and avoid the screen edges. Wait and verify that the Home Screen is visible and settled. If the gesture changes surfaces or enters editing, use **Navigation and Home recovery**.
6. Announce **Warm-up 6/7: opening [second app]**. Tap a visible approved app different from the first app, wait, and verify that the selected app is open.
7. Announce **Warm-up 7/7: returning home and finishing**. Use `home` once, wait, and verify that the Home Screen app grid is visible. If it is not, use **Navigation and Home recovery**.

Report completion only after all seven phases have been performed and the phone is visibly settled on the Home Screen. Use visible labels and the latest screenshot rather than memorized coordinates.
