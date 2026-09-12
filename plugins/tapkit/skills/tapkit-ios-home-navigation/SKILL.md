---
name: tapkit-ios-home-navigation
description: Navigate the iPhone Home system, including Today View, Home pages, Spotlight, folders, App Library, and nearby overlays. Use when finding apps, moving between Home surfaces, or escaping a search loop. Do not use for navigation inside an open app.
---

# iOS Home Navigation

## Overview

The iPhone Home experience contains connected surfaces, not one screen. Today View is left of the first Home page, ordinary Home pages occupy the middle, and App Library is on the far right. Spotlight overlays these surfaces and usually returns to the one that opened it. Layouts vary, so navigate by visible interface cues rather than saved page counts, icon positions, or coordinates.

```text
Today View <- first Home page <-> more Home pages -> App Library
```

- Flicking right moves toward earlier pages and Today View.
- Flicking left moves toward later pages and App Library.
- A normal Home page has the dock and an app or widget layout.

## Important Surfaces

**Today View** is widget-focused and usually lacks the normal app grid. Flick left to return to the first Home page. Begin the gesture in a visible outer gutter or other open space; never drag on a widget or Smart Stack when trying to navigate away. A drag that begins or lingers on a widget can enter editing instead of changing surfaces. Widget editing is indicated by minus controls on the widgets and a checkmark in the top-right corner. If those controls appear, tap the top-right checkmark to leave editing before retrying navigation through open space.

**Spotlight** mixes apps with settings, contacts, web suggestions, and other content. It can reopen with an old query. Clear the query before dismissing it because flicking populated results often scrolls them. Dismissal returns to the underlying surface, which might not be a normal Home page.

**App Library** uses grouped category tiles without the normal dock. Large icons open apps, while small clusters expand categories. Search shows an alphabetical, app-only list with Cancel. Cancel search before flicking right to return Home.

**Folders and icon menus** appear as panels over a Home page. Tap outside them to return to the underlying page.

**Home editing** is indicated by jiggling icons, minus controls, or a Done control. Use Done to leave editing, but avoid dragging items or changing page visibility.

**App Switcher** shows overlapping app cards. One Home action returns toward Home. Do not use repeated Home actions as a universal reset.

**Control Center and Notification Center** are overlays. Dismiss them with their normal edge gestures before navigating Home pages.

## Finding and Opening Apps

Prefer App Library search when app locations are unknown. Move left through Home pages until the grouped App Library appears, open its search field, and use the alphabetical app-only results. This avoids assumptions about page count, folders, Focus-specific layouts, or icon positions.

Spotlight is useful for broad search but mixes result types. Mixed results indicate Spotlight; an alphabetical app list and letter rail indicate App Library search.

## Navigation Principles

- Move one surface at a time and use the visible UI to stay oriented.
- Do not assume a fixed number of Home pages or a standard app location.
- Start horizontal flicks in open space when possible.
- If a flick is intercepted, dismiss the visible folder, menu, keyboard, editing layer, or system overlay.
- Do not move apps, edit widgets, alter folders, hide pages, or change Focus-linked layouts unless explicitly requested.
- If the task is only to locate an app, do not open it without authorization.
