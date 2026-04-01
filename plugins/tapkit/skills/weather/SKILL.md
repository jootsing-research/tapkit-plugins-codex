---
name: weather
description: Use this skill when the user wants to check weather conditions, forecast details, saved cities, or the weather map in the iPhone Weather app.
---

# Weather

Open `Weather` directly when possible. The app is highly scrollable and sometimes switches between city detail, city list, and map views, so confirm the current mode before acting.

Use the `tapkit` skill's clipboard workflow for city search.

## Main Views

- `City Detail`
- `City List`
- `Map`

## Common Tasks

### Check Current Conditions

1. Open the city detail screen.
2. Read the temperature, condition, and hourly summary.
3. Scroll down for cards such as precipitation, wind, UV, and air quality.

### Switch Cities

1. Open the city list view or swipe between saved cities.
2. Tap the target city card.
3. Verify the city name at the top of the detail screen.

### Add a City

1. Open the city list view.
2. Tap the add or search control.
3. Paste the city name.
4. Tap the matching result.

### Open the Map

1. Tap the map control from the city detail view.
2. Switch layers only if needed.
3. Use screenshots to verify the active layer and region.

## Gotchas

- The city list and map controls are small and easy to miss near the lower edge.
- Weather cards are scrollable and can be mistaken for separate screens.
- Search can show multiple similar cities; confirm the state or country before adding one.
