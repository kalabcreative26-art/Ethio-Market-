# Rework: empty starter marketplace + profile-based messaging
[x] Update types: Conversation keyed by sellerId+productId, add Seller.bio/avatarInitials fields as needed
[x] Empty SELLERS and PRODUCTS mock data (start with zero items), keep CATEGORIES/SUB_CATEGORIES
[x] Empty CONVERSATIONS data (start with zero conversations)
[x] Add MessagesProvider (context) to manage conversations in state, with startConversation(seller, product?) and sendMessage
[x] Create Seller Profile page (route /seller/:sellerId) showing seller info + their listings + "Message Seller" per product/profile
[x] Update ProductCard/ProductDetailSheet to link to Seller Profile page instead of generic seller info block
[x] Update "Message Seller" action to start/open a conversation tied to specific product+seller via MessagesProvider, then navigate to /messages
[x] Update Messages page to read from MessagesProvider (empty state when no conversations yet)
[x] Update Home page empty state copy for buyers/sellers reflecting no listings yet
[x] Update Seller "My Listings" empty state copy (already exists, verify wording)
[x] Wire seller registration feel: Add Product page starts fully empty (already does via context now empty), requires store profile setup first
[x] Lint and fix
