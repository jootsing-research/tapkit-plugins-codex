---
name: uber-eats
description: Use this skill when the user wants to search Uber Eats, reorder a meal, add items to cart, or move through checkout on iPhone.
---

# Uber Eats

Open Uber Eats and screenshot after every major action. Restaurant pages, item sheets, and checkout all use stacked views, so verify whether you are on the feed, a menu, an item detail, or checkout.

Use the `tapkit` skill's clipboard workflow for search and delivery instructions.

## Main Tabs

- `Home`
- `Browse`
- `Search`
- `Cart`
- `Account`

## Common Tasks

### Search for a Restaurant or Dish

1. Open `Search`.
2. Activate the search field.
3. Paste the query and submit it.
4. Open the matching restaurant or result card.

### Add an Item to Cart

1. Open the restaurant page.
2. Tap an item card or a visible `+` button.
3. Complete required customizations.
4. Tap the add-to-cart button.
5. Verify the cart count increased.

### Reorder a Previous Meal

1. Open `Account`.
2. Open orders or past orders.
3. Find the previous order.
4. Tap `Reorder`.
5. Review cart contents before checkout.

### Checkout

1. Open `Cart`.
2. Review delivery address, fees, and item list.
3. Continue to checkout.
4. Confirm delivery time and tip only if the user asked for the final purchase.

## Gotchas

- Required customizations are common and will block add-to-cart.
- Uber Eats often defaults to premium or priority delivery options.
- Pre-checkout upsells and confirmation sheets appear frequently. Read them before tapping through.
