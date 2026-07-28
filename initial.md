# Requirements
## Summary
Ethio Market is an internal marketplace management web app (inspired by AliExpress/Jiji marketplaces) built as a UI Bakery Custom App, using the Ethio Market brand (sky blue #33B3FF / deep navy #001D48 palette, rounded card-based "glass" styling, light/dark theme). It gives Sellers a dashboard to manage product listings, inventory, store location, and sales analytics, and gives Buyers a catalog experience to browse, search/filter, chat with sellers, and place orders through a multi-option checkout (Chapa/Telebirr, Cash on Delivery, In-Person Payment). Authentication, user roles (Buyer/Seller), and invitations are handled by UI Bakery's built-in auth system. All data is mock data for now.

## Use cases
- App Shell & Navigation
  1) User logs in via UI Bakery built-in auth and lands on the main dashboard
  2) User sees a responsive shell with top bar (logo, theme toggle, search) and a bottom/side navigation adapted to their role (Seller: Home, Messages, Add Product, Profile; Buyer: Home, Messages, Cart, Profile)
  3) User switches between Buyer and Seller view via a role switcher, confirming a warning dialog about resetting active session/draft context
  4) User navigates between pages (Home, Messages, Cart/Add Product, Profile) using the nav, with the active tab highlighted

- Buyer Product Browsing & Search
  1) Buyer lands on Home page showing category chips and a grid of product cards (image, title, price, seller)
  2) Buyer uses the search bar to filter products by keyword in real time
  3) Buyer uses a dual-thumb price range slider and category chips to filter the product grid
  4) Buyer clicks a product to view its detail page (photos, description, specifications, price, delivery/pickup availability, seller info)
  5) Buyer adds product to cart or starts a chat with the seller from the detail page
  6) Buyer sees an empty-state message when no products match filters

- Buyer Cart & Checkout
  1) Buyer opens Cart page listing added products with quantity controls and subtotal
  2) Buyer proceeds to checkout, entering a delivery address (or choosing pickup)
  3) Buyer selects a payment method: Chapa/Telebirr, Cash on Delivery (disabled if seller has no delivery), or In-Person Payment
  4) Buyer confirms the order and sees an order confirmation summary

- Seller Product Management
  1) Seller opens "Add Product" page and fills a form (title, description, specifications, photos, price, category/sub-category, delivery vs pickup toggle)
  2) Seller saves the product, which appears in their product list
  3) Seller edits an existing listing or marks it as "Sold Out" from their product list
  4) Seller sets/updates their store's pinned location on a simple map placeholder for buyer trust

- Seller Analytics Dashboard
  1) Seller opens their Profile/Dashboard page
  2) Seller views summary cards for Store Views, Clicks, and Monthly Revenue
  3) Seller views a chart showing store growth and sales trends over recent months

- In-App Messaging
  1) User (Buyer or Seller) opens Messages page showing a list of conversations
  2) User selects a conversation and views the message thread
  3) User sends a new text message within the thread (mock real-time behavior)

## Plan
### App Shell & Navigation
1. [x] Create app shell layout with top bar (Ethio Market logo, light/dark theme toggle, global search input) using brand colors (sky blue #33B3FF, deep navy #001D48)
2. [x] Implement bottom/side navigation component with role-based tabs (Seller: Home, Messages, Add Product, Profile; Buyer: Home, Messages, Cart, Profile) and active-tab highlighting
3. [x] Add a Buyer/Seller role switcher control in the top bar or profile menu, backed by mock state
4. [x] Implement a confirmation dialog shown when switching roles, warning that active session/draft context will reset
5. [x] Set up client-side routing/page structure for Home, Messages, Cart or Add Product, Profile pages
6. [x] Build the Home page shell with placeholder content area ready to host the product grid (from next use case)
7. [x] Apply consistent card-based rounded styling (rounded corners, soft shadows) across the shell to match brand look

### Buyer Product Browsing & Search
1. [x] Create mock product dataset (name, price, category, sub-category, images, description, specifications, delivery/pickup flag, seller info) with a reasonable variety of items and categories
2. [x] Build category chips row for filtering by category
3. [x] Build a real-time keyword search bar filtering the mock product list
4. [x] Build a dual-thumb price range slider component filtering products by min/max price
5. [x] Build a responsive product grid/card component showing image, title, price, and seller name
6. [x] Build a product detail page/modal showing photos, description, specifications, price, delivery/pickup badge, and seller info with "Add to Cart" and "Message Seller" actions
7. [x] Implement an empty-state view (message + icon) shown when filters return no products

### Buyer Cart & Checkout
1. [x] Build a Cart page listing items added to cart (mock state) with quantity increment/decrement and remove actions, showing subtotal
2. [x] Build a checkout flow step for entering delivery address or choosing store pickup
3. [x] Build a payment method selection step with three options: Chapa/Telebirr, Cash on Delivery (disabled when item has no delivery), In-Person Payment
4. [x] Build an order confirmation summary screen showing selected items, address/pickup choice, payment method, and total
5. [x] Wire cart state so items added from product detail page appear correctly in the Cart page

### Seller Product Management
1. [x] Build "Add Product" form with fields: title, description, specifications, photo upload placeholders, price, category/sub-category selects, and delivery-vs-pickup toggle
2. [x] Implement form validation and a mock save action that adds the product to the seller's mock product list
3. [x] Build a Seller product list page showing all their listings with edit and "Mark as Sold Out" actions
4. [x] Build an edit-product view reusing the Add Product form pre-filled with existing values
5. [x] Build a simple store location section with a static map placeholder and a "Set/Update Location" action (mock pin coordinates)

### Seller Analytics Dashboard
1. [x] Create mock analytics dataset (views, clicks, revenue by month) for the seller
2. [x] Build summary metric cards for Store Views, Clicks, and Monthly Revenue
3. [x] Build a chart (line or bar) showing store growth/sales trend over recent months using the mock analytics dataset
4. [x] Place the analytics section within the Seller Profile/Dashboard page

### In-App Messaging
1. [x] Create mock conversations dataset (contact name/role, last message, timestamp) per user role
2. [x] Build a Messages list page showing conversations with avatar, name, last message preview, and timestamp
3. [x] Build a conversation thread view showing message bubbles distinguishing sent vs received messages
4. [x] Implement a message input allowing the user to add a new message to the mock thread (appended to local state)
