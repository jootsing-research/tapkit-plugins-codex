---
name: weather
description: This skill should be used when the user wants to check the weather, view forecasts, check temperature or conditions for a city, use the weather map, manage saved cities, check air quality, wind, UV index, humidity, or interact with the Weather app on their iPhone.
---

# iOS Weather App — Usage Manual

The Apple Weather app displays current conditions, forecasts, and detailed weather data for saved cities. This skill teaches you the Weather app's UI layout and interaction patterns.

**Always take a screenshot after each action to verify what's on screen.** Use visual landmarks (text labels, icons, positions like "top-left") rather than memorized coordinates.

## App Structure Overview

The Weather app has three main views:

1. **City Detail View** — The main scrollable weather view for a single city
2. **City List View** — A list of all saved cities with summary weather info
3. **Full-Screen Map View** — An interactive weather map with multiple data layers

### Bottom Toolbar (persistent on City Detail View)

| Element | Position | Action |
|---------|----------|--------|
| Map icon | Bottom-left (~75, 1270) | Opens the full-screen weather map |
| Page dots | Bottom-center (~310, 1270) | Indicates which city you're viewing; swipe left/right to switch |
| List icon | Bottom-right (~548, 1270) | Opens the city list view |

---

## City Detail View

The primary view shown when you open the app. A single vertically-scrollable page with multiple sections. Background dynamically reflects current weather conditions.

### Opening the App

```
open_app("Weather")
```

### Header Section (top, no scrolling needed)

- **City name**: Large text, centered (e.g., "New York")
- **Current temperature**: Very large text below city name (e.g., "45°")
- **Feels Like**: Below current temp (e.g., "Feels Like: 35°")
- **High / Low**: Below feels like (e.g., "H:51° L:37°")

When scrolled down, the header collapses to a sticky bar showing: `City Name` / `Temp° | Feels Like: Temp°`

### Forecast Summary

A brief natural-language summary of the forecast (e.g., "Higher temperatures expected tomorrow, with a high of 70°.").

### Hourly Forecast

- **Horizontally scrollable** row of hourly forecasts
- Each entry: **Time**, **Weather icon**, **Temperature**
- Starts with "Now" and extends ~12+ hours
- Swipe left on the row to see more hours

### 10-Day Forecast

- Section header: "10-DAY FORECAST" with calendar icon
- Each row: **Day name**, **Weather icon** (with precipitation % in cyan if applicable), **Low temp**, **Color-coded temperature bar**, **High temp**
- **Tapping any day** opens the detailed **Conditions** modal

### Air Quality

- Section header: "AIR QUALITY"
- Shows: **AQI number**, **Rating** (e.g., "Moderate"), **Color-coded gradient bar**, **Description text**

### Wind Map (inline preview)

- Embedded map showing animated wind patterns
- Shows saved cities with wind speed indicators
- Tapping opens the full-screen map view

### Weather Widgets (scrollable sections)

| Order | Widget | Width |
|-------|--------|-------|
| Feels Like | Half (left) |
| UV Index | Half (right) |
| Wind | Full |
| Sunrise/Sunset | Half (left) |
| Precipitation | Half (right) |
| Visibility | Half (left) |
| Humidity | Half (right) |
| Moon Phase | Full |
| Averages | Half (left) |
| Pressure | Half (right) |

All widgets are tappable — each opens a detailed Conditions modal.

### Navigating Between Cities

- **Swipe left** on the detail view to go to the next city
- **Swipe right** to go to the previous city
- Page dots at the bottom indicate which city is shown

---

## City List View & City Management

Access by tapping the **list icon** (bottom-right, ~548, 1270).

### Layout

- **"Weather" header** at top-left
- **Three-dot menu** (⋯) at top-right (~556, 95)
- **City cards**: Each shows city name, local time, forecast summary, current temperature, H/L
- **Search bar** at bottom: "Search for a city or airport" (~310, 1237)

### Three-Dot Menu (⋯)

| Option | Description |
|--------|-------------|
| **Edit List** | Reorder or delete saved cities |
| **Notifications** | Configure weather alerts |
| **Celsius** | Switch to Celsius |
| **Fahrenheit** | Switch to Fahrenheit |
| **Units** | Configure all measurement units |
| **Report an Issue** | Report weather data problems |

### Adding a City

1. `copy_text_to_phone("San Francisco")` to load the city name onto the clipboard
2. `long_press(260, 1238, duration: 1500)` on the search bar at the bottom — this activates the field and shows the **Paste** tooltip
3. Tap **"Paste"** in the tooltip
4. Results appear as live auto-complete — tap to select
5. City detail view opens — tap **"Add"** (top-right) to save

### Deleting a City

**Method 1 — Swipe-to-delete:**
1. Swipe left on a city card
2. Tap the red trash can button that appears

**Method 2 — Edit List mode:**
1. ⋯ menu → Edit List
2. Tap red minus button on left of city card
3. Tap trash button to confirm
4. Tap checkmark to exit edit mode

### Reordering Cities

1. ⋯ menu → Edit List
2. Use `hold_and_drag()` on drag handles (≡) to reorder
3. Tap checkmark to exit

### Units Settings

Access: ⋯ menu → Units

| Unit | Default | Options |
|------|---------|---------|
| **Temperature** | System setting | Celsius (°C), Fahrenheit (°F), Use system setting |
| **Wind** | mph | mph, km/h, m/s, bft, kn |
| **Precipitation** | in | Inches, Millimeters/centimeters |
| **Pressure** | inHg | mbar, inHg, mmHg, hPa, kPa |
| **Distance** | mi | Miles, Kilometers |

---

## Full-Screen Map View

Access by tapping **map icon** (bottom-left, ~75, 1270).

### Layout

- **X button** (top-left, ~50, 110) — closes map
- **Layer selector** (top-right, ~572, 107) — switch map layers
- **Location button** (~572, 160) — center on current location

### Map Layers

| Layer | What it Shows |
|-------|---------------|
| **Precipitation** | Rain/snow patterns with intensity |
| **Temperature** | Heat map of temperatures |
| **Air Quality** | AQI levels across region |
| **Wind** | Animated wind flow lines (default) |

### Timeline Controls (bottom of map)

- **Play button** (▶) — animate weather data forward
- **Time scrubber** — drag to scrub through hours

---

## Conditions Detail Modal

Access by tapping any **day in the 10-Day Forecast** or any **detail widget**.

- **Day selector**: Scrollable horizontal row of dates
- **Condition type dropdown**: Switch between Conditions, UV Index, Wind, Precipitation, Humidity, Visibility, Pressure
- **24-hour chart** with hourly values, color-coded area/line chart
- **Additional sections**: Chance of Precipitation, Precipitation Totals, Forecast text, Daily Comparison

---

## Key Workflows

### Check Current Weather
```
1. open_app("Weather") → screenshot to verify
2. City detail view shows current temp, feels like, H/L
```

### Get the 10-Day Forecast
```
1. open_app("Weather")
2. swipe(310, 672, "up") — scroll past hourly to 10-day section
3. screenshot
```

### Check if it Will Rain
```
1. Look for precipitation % on 10-day forecast (cyan text like "90%")
2. Or scroll down ~3 swipes to find the Precipitation widget
3. Tap a day to see detailed Precipitation chart
```

### Switch Between Cities
```
# Option 1: Swipe on detail view
swipe(310, 672, "left")   # Next city
swipe(310, 672, "right")  # Previous city

# Option 2: Use city list
tap(548, 1270)  # List icon
screenshot      # See all cities
tap(310, 210)   # Tap desired city card
```

### Add a New City
```
1. tap(548, 1270)                                # Open city list
2. copy_text_to_phone("San Francisco")           # Load city name onto clipboard
3. long_press(260, 1238, duration: 1500)         # Activate search bar, show Paste tooltip
4. Tap "Paste" in the tooltip
5. Tap result from auto-complete
6. Tap "Add" (top-right) to save
```

### Open the Weather Map
```
1. tap(75, 1270)   # Map icon
2. screenshot
3. tap(572, 107)   # Layer selector to switch layers
```

### Change Temperature Units
```
1. tap(548, 1270)   # List icon to go to city list
2. tap(556, 95)     # Three-dot menu
3. Tap "Celsius" or "Fahrenheit"
```

## Tips and Gotchas

- **Background adapts to weather**: Cloudy skies show dark backgrounds, sunny days are brighter. This affects text readability in screenshots.
- **Typing into the search field**: Use the clipboard paste flow (`copy_text_to_phone` → `long_press` the search bar at 1500ms → tap "Paste" in the tooltip). Don't try to tap individual keyboard keys.
- **Precipitation percentage**: Shown in cyan/teal text below weather icon in the 10-day forecast when rain is expected.
- **"My Location"**: If location services are enabled, the first city may show "My Location" instead of a city name.
- **All detail widgets are tappable**: Every section on the main view can be tapped to open a detailed chart/modal.
- **Half-width widgets** are arranged in a 2-column grid.
- **Scrolling**: Swipe up to scroll down. ~4 swipes from top reaches the bottom of the detail view.
- **Health Information banner**: May occasionally appear as a popup — dismiss by tapping X.
