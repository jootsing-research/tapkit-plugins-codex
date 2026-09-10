---
name: agent-setup
description: Configure the iPhone for agent use by setting three AssistiveTouch toggles and opening Devices. Use whenever the user says "do agent setup", "agent setup", or asks to prepare the phone for the agent.
---

# Agent setup

Configure AssistiveTouch and finish on its **Devices** screen:

1. Open Settings and navigate to **Accessibility**.
2. In **Physical and Motor**, tap **Touch**.
3. Tap **AssistiveTouch**, the row at the top of the Touch screen.
4. On the AssistiveTouch screen, use a screen-relative vertical `drag` to reveal the lower settings. Drag near the horizontal center from about 80% down the screen to about 20% down the screen.
   - Treat those percentages as a guide based on the latest screenshot, keeping the gesture inside the scrollable content area.
   - Use `drag`, never `flick`, when navigating Settings screens.
5. Use `wait` for 1,000 milliseconds before locating or changing the toggles.
6. Inspect the fresh screenshot and establish these three states:
   - **Show Onscreen Keyboard**: on
   - **Sound on Click**: off
   - **Always Show Menu**: off
7. Handle the switches one at a time. For each switch:
   - Work only from the latest screenshot.
   - Find the exact label, establish that row's vertical bounds, and then find the pill-shaped switch on the right side of the same row.
   - Determine the current state from both the track color and thumb position. Do not tap when the state is already correct.
   - Estimate the complete switch track's left, right, top, and bottom edges. Tap its geometric center: the midpoint between its left and right edges and the midpoint between its top and bottom edges.
   - Sanity-check that the target's x coordinate aligns with the column of nearby switches and that its y coordinate is at the vertical middle of the intended switch. Never target the label, row center, movable thumb, text baseline, or an edge of the track.
   - Treat an `ok` tool result only as confirmation that the gesture was dispatched, not that the switch changed.
   - After tapping once, use `wait` for 1,000 milliseconds and inspect the fresh screenshot. If the state is unchanged, locate the switch again from the newest screenshot and recompute both x and y from scratch. Do not reuse the same or nearly identical coordinates.
   - Retry only once. After two failed taps on the same switch, stop and report the failure instead of tapping repeatedly.
8. Do not proceed until all three required states have been visually verified.
9. Locate the **Devices** row above these toggles. If it is not visible, use a screen-relative vertical `drag` near the horizontal center from about 20% down the screen to about 80% down the screen to reveal the higher settings. Never use `flick`. After any drag, use `wait` for 1,000 milliseconds before locating the row.
10. Tap the **Devices** row.
11. Use `wait` for 1,000 milliseconds, inspect the fresh screenshot, and verify that the **Devices** screen is open.
12. Report completion only after the three toggle states are correct and the **Devices** screen is visibly open.

At every step, use visible labels and the latest screenshot rather than memorized coordinates.
