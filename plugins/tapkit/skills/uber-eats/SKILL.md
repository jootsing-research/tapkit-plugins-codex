---
name: uber-eats
description: This skill should be used when the user wants to use Uber Eats, order food delivery, reorder a previous meal, search for restaurants, browse menus, add items to cart, place a delivery or pickup order, or interact with the Uber Eats app on their iPhone.
---

# Uber Eats — Food Delivery App

Uber Eats is a food delivery app for ordering from restaurants, grocery stores, and convenience stores. Users browse restaurants, search for food, customize menu items, manage carts, and place delivery or pickup orders. This skill teaches you Uber Eats' UI layout and interaction patterns.

## TapKit Setup Reminder

Before acting in this app, follow the core TapKit setup: `list_phones()` -> choose `phone_id` -> `get_phone_status(phone_id)`. All TapKit examples in this skill assume every MCP tool call includes that `phone_id`.

For every text-entry action, focus the correct field, call `type_text(phone_id, text)`, then call `screenshot(phone_id)` and visually verify the rendered text. Do not tap Send, Post, Search, Save, Confirm, or an equivalent submission control automatically. Submit only when the user explicitly authorizes the exact action and visual verification succeeds.

## Privacy And Checkout Decisions

- Inspect only the restaurant, cart, order, or account surface needed for the request. Never enumerate, quote, or summarize the user's order history, saved addresses, phone numbers, or payment methods visible on screen.
- Never repeat a complete delivery address, phone number, or payment detail in model output. When one is relevant, mask it (for example, `•••• Main St`, `(***) ***-1234`, or `•••• 4242`) and have the user review the full value on the device. If a reorder requires a prior order, use only the exact order the user identified to prepare the current cart; do not report its historical details.
- Do not silently select a delivery speed, tip, substitution, or response to an upsell. Show the relevant options without unrelated private data and obtain an explicit choice for each consequential decision. A preselected or default option is not user approval.
- At checkout, present an itemized, privacy-safe preview of the restaurant, items and customizations, masked destination, delivery choice and fee, tip, substitutions, upsell choices, taxes/fees, and total. Get explicit confirmation of every unresolved choice, then obtain separate final confirmation immediately before placing the order.
- If an address, phone number, or payment method must be added or changed, stop at its form and let the user review the complete value on the device. Do not repeat the complete value in model output.

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
1. Tap the search bar to focus it
2. `type_text(phone_id, "query")`
3. `screenshot(phone_id)` → verify the rendered query and expected autocomplete results
4. Do not submit automatically. Only if the user explicitly authorized opening a result and verification succeeded, tap a matching restaurant or suggestion
5. `screenshot(phone_id)` → verify the intended result page opened
6. **Full results page** has filter tabs: All, Restaurants, Grocery, Retail, Alcohol
7. Filter pills: Uber One, Offers, Under 30 min, Best overall
8. **Dish suggestion circles** appear at top (e.g., "Pad Thai", "Mango Sticky Rice")
9. Results show as large restaurant cards

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
- Each card: restaurant name, item count, total, masked delivery destination, open/closed status
- **"View cart"** and **"View store"** buttons

### Cart Detail
- Items with photos, names, customization details, prices, quantity controls
- **"+ Add items"** link, **"Offers for you"** section
- **"Go to checkout"** button (black, bottom)

## Checkout Flow

### Step 1: Checkout Page
- Delivery address, instructions, and phone are sensitive. Verify them on-device and refer to them only in masked form.
- **Delivery time options**: Priority, Standard, Schedule. Prices and defaults can vary; preview the current options and get the user's explicit choice before selecting one.
- Order summary, **"Next"** button

### Step 2: Tip Page
- Tip percentages and a Custom option are shown. Preview the current choices and get the user's explicit tip choice; do not accept or infer a default.
- **"Place order"** button

### Step 3: Confirmation
- "Placing order..." with **"Looks good (0:XX)"** countdown button
- The order may auto-confirm after the countdown. Do not enter this state until the privacy-safe checkout preview is complete and the user has explicitly confirmed the final order.

### Step 4: Order Tracking
- Map, status, ETA, progress bar, delivery details

## Reordering

1. Account tab → **Orders** → **Past orders** tab
2. Inspect only the specific order the user identified; do not enumerate or summarize order history
3. Find order → tap **"Reorder"**
4. Opens order detail → scroll down → tap **"Reorder"** button
5. Preview changed or unavailable customizations and get the user's explicit choices
6. If **"Complete your order"** or another upsell appears, show the relevant options and ask whether to accept or decline it
7. Proceed through the decision-gated checkout flow

## Key Workflows

### Place a New Order
```
1. Search for restaurant or browse home feed
2. Tap restaurant card
3. Browse menu (scroll or use category tabs/list icon)
4. Tap item → customize → "Add to cart"
5. If an upsell appears, preview it and get an explicit accept-or-decline choice
6. If a substitution prompt appears, preview its relevant options and get an explicit choice
7. Preview delivery options and get the user's explicit delivery-speed choice
8. Preview tip options and get the user's explicit tip choice
9. Show the privacy-safe checkout preview and resolve every remaining choice
10. Get separate final confirmation immediately before tapping "Place order"
```

### Reorder a Previous Order
```
1. Account tab → "Orders" → "Past orders"
2. Find only the identified order → "Reorder" → scroll down → "Reorder"
3. Preview customizations and any upsell or substitution choices; get explicit decisions
4. Get explicit delivery and tip choices
5. Show the privacy-safe checkout preview and get separate final confirmation before placing the order
```

## Tips and Gotchas

- **Delivery defaults can change** — never treat Priority, Standard, or another preselection as the user's choice
- **"Complete your order" and other upsells** may appear before checkout — do not accept or decline one without the user's explicit choice
- **"Looks good" countdown** on Place Order confirmation can auto-confirm — enter it only after final order confirmation
- **Restaurants can cancel** even after "Order received" (especially near closing)
- **Multiple carts** saved across restaurants — cart badge shows total items
- **Closed restaurants** still appear in search with "Available at X:XX AM"
- **Tab bar hides when scrolling** — scroll up or navigate back to see it
- **Required item customizations** must be selected before "Add to cart" works
- **Search autocomplete** shows both restaurant matches and search suggestions as you type
