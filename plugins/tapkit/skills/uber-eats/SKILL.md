---
name: uber-eats
description: This skill should be used when the user wants to use Uber Eats, order food delivery, reorder a previous meal, search for restaurants, browse menus, add items to cart, place a delivery or pickup order, or interact with the Uber Eats app on their iPhone.
---

# Uber Eats — Food Delivery App

Uber Eats is a food delivery app for ordering from restaurants, grocery stores, and convenience stores. Users browse restaurants, search for food, customize menu items, manage carts, and place delivery or pickup orders. This skill teaches you Uber Eats' UI layout and interaction patterns.

## App Structure

### Tab Bar (bottom of screen)

Uber Eats has 5 tabs along the bottom navigation bar:

1. **Home** (House icon) — Main feed with featured restaurants, categories, and promotions
2. **Browse** (Pin/Location icon) — Map view of nearby pickup spots and restaurants
3. **Search** (Magnifying glass) — Search for restaurants, cuisines, or specific dishes
4. **Cart** (Shopping cart icon, shows badge with item count) — View saved carts from multiple restaurants
5. **Account** (Person icon) — Profile, orders, favorites, wallet, settings

### Home Screen Layout

- **Address selector** at top-left ("Home v" dropdown) — tap to change delivery address
- **Notification bell** top-right (shows badge count)
- **Service tabs**: All, Rides, Grocery, Convenience (horizontal scroll)
- **Category icons**: Dine Out, Pizza, Ice Cream, Comfort Food, Mexican, Healthy (horizontal scroll of emoji icons)
- **Filter pills**: Uber One, Pickup, Offers, Under 30 min (horizontal scroll)
- **Restaurant sections**: "Featured on Uber Eats", "Places you might like", "Order again" — each with horizontal scrolling restaurant cards
- **Promo banners**: Appear as dismissible banners (tap X to close)
- **Active order banner**: When an order is in progress, appears at top with ETA and quick actions (Add items, Edit address, Delivery instructions)

### Restaurant Cards

Restaurant cards appear throughout the app and show:
- Large photo with badges ("Free item on $40+", "Ordered before", "Most popular")
- Restaurant name, heart/favorite icon
- Uber One badge (green circle), delivery fee, delivery time
- Rating (stars), review count, cuisine ranking (#3 Asian, etc.)
- "Sponsored" label on promoted results

## Search

Tap the Search tab (3rd icon) to open search.

### Search Screen Layout
- **Search bar** at top with back arrow (left) and clear button X (right)
- **Recent searches**: horizontal scrolling pills
- **Order again**: horizontal scroll of restaurant circles with names and delivery times
- **Suggested sections**: "Fire up the grill", "Top categories"
- **Keyboard** appears automatically with blue "search" button

### Search Flow
1. `copy_text_to_phone("query")` to load the search text onto the clipboard
2. `long_press` the search bar (~1500ms) to activate it and bring up the **Paste** tooltip
3. Tap **"Paste"** in the tooltip
4. **Autocomplete results appear immediately** — showing matching restaurants (with icons) and search suggestions
5. Tap a restaurant name to go directly to it, OR tap a suggestion to see full results
5. **Full results page** has filter tabs: All, Restaurants, Grocery, Retail, Alcohol
6. Filter pills: Uber One, Offers, Under 30 min, Best overall
7. **Dish suggestion circles** appear at top (e.g., "Pad Thai", "Mango Sticky Rice")
8. Results show as large restaurant cards

To clear search: tap the X button on the right side of the search bar.

## Restaurant Page

### Header
- Hero photo at top
- **X** (close, top-left), **Search** (magnifying glass), **Heart** (favorite), **...** (more options) — overlaid on hero image
- Restaurant logo (centered, overlapping hero)
- Restaurant name, rating, Uber One badge, distance
- Closing warning if applicable (e.g., "9 min until closing")
- Reorder count ("900+ people reordered")

### Delivery Options
- **Delivery / Pickup** toggle buttons
- **Group order** button (right side)
- Delivery fee info and earliest arrival time
- Uber One promo banner

### Menu Navigation
- **"Explore Menu"** heading with dietary filter pills: Featured, Vegetarian, Pescatarian
- **Horizontal tab navigation** that sticks to top when scrolling: scrolls through menu categories (Picked for you, Free with $X purchase, Appetizers, Soups, etc.)
- **List icon** (three lines, left of tabs) — tap to open a **full menu category overlay** showing all sections with restaurant hours. Tap a category to jump to it. Tap "Dismiss" to close.
- **Featured items** show as horizontal scroll with photos, + buttons, names, prices, badges (#1 most liked)
- **Regular menu items** show in a 2-column grid with photos, + buttons, names, prices, like percentages, and descriptions

### Adding Items
- Tap a **+** button on any item card for quick add (if no required customizations)
- Tap the **item photo or name** to open the full item detail page

## Item Detail Page

Opens as a modal/sheet:
- **Hero photo** at top with X (close, top-left) and share button (top-right)
- **Item name**, price, description
- **Badges**: "#3 most liked", "96% (56)" thumbs up ratings
- **Customization sections** (scroll down):
  - **Required selections** (radio buttons): e.g. "Choose your protein — Required, Choose 1" with options like Veggie, Beef (+$2.00), Chicken, Shrimp (+$4.00), etc.
  - **Required selections**: e.g. "Choose your spice level — Required, Choose 1" with Mild, Level 1-5
  - **Optional selections** (checkboxes): drink choices, sauce choices, etc.
- **Special Instructions**: "Add a note" text field
- **Allergy requests**: expandable section
- **Quantity selector**: - / number / + buttons (bottom-left area)
- **"Add X to cart - $price"** button pinned at bottom (price updates with selections)

## Cart

### Carts Page (Cart tab)
- Shows **multiple saved carts** from different restaurants
- Each card: restaurant name, item count, total, delivery address, open/closed status
- **"View cart"** and **"View store"** buttons

### Cart Detail
- Items with photos, names, customization details, prices, quantity controls
- **"+ Add items"** link, **"Offers for you"** section
- **"Go to checkout"** button (black, bottom)

## Checkout Flow

### Step 1: Checkout Page
- Delivery address, instructions, phone
- **Delivery time options**: Priority (+$3.99, default), Standard (free), Schedule
- Order summary, **"Next"** button

### Step 2: Tip Page
- Tip percentages: 17%, 21% (default), 25%, 29%, Custom
- **"Place order"** button

### Step 3: Confirmation
- "Placing order..." with **"Looks good (0:XX)"** countdown button
- Auto-confirms after countdown

### Step 4: Order Tracking
- Map, status, ETA, progress bar, delivery details

## Reordering

1. Account tab → **Orders** → **Past orders** tab
2. Find order → tap **"Reorder"**
3. Opens order detail → scroll down → tap **"Reorder"** button
4. Confirm customizations if prompted
5. **"Complete your order"** upsell → tap **"No thanks"**
6. Proceed through checkout

## Key Workflows

### Place a New Order
```
1. Search for restaurant or browse home feed
2. Tap restaurant card
3. Browse menu (scroll or use category tabs/list icon)
4. Tap item → customize → "Add to cart"
5. "Go to checkout" → skip upsell ("No thanks")
6. Switch to Standard delivery (saves $3.99)
7. "Next" → select tip → "Place order" → confirm
```

### Reorder a Previous Order
```
1. Account tab → "Orders" → "Past orders"
2. Find order → "Reorder" → scroll down → "Reorder"
3. Confirm customizations → skip upsell
4. Checkout → Standard delivery → tip → place order
```

## Tips and Gotchas

- **Priority delivery is default (+$3.99)** — always switch to Standard unless user wants priority
- **"Complete your order" upsell** always appears before checkout — tap "No thanks"
- **"Looks good" countdown** on Place Order confirmation — tap it or it auto-confirms
- **Restaurants can cancel** even after "Order received" (especially near closing)
- **Multiple carts** saved across restaurants — cart badge shows total items
- **Closed restaurants** still appear in search with "Available at X:XX AM"
- **Tab bar hides when scrolling** — scroll up or navigate back to see it
- **Required item customizations** must be selected before "Add to cart" works
- **Search autocomplete** shows both restaurant matches and search suggestions as you type
