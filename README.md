
# 🇧🇩 Neighborhood Fresh Food Marketplace

A **hyperlocal food marketplace** for Bangladesh where buyers can find  **fresh vegetables, fruits, meats, fish, and eggs within 5 km** — and  **contact sellers directly by phone** (no online payment, no chat).

---

## 🏪 Project Overview
- Focus: Fresh, local, community-based produce
- Location limit: **Maximum 5 km radius**
- Target users: Local farmers, butchers, small growers, nearby buyers
- Contact: Direct phone call to seller
- Payment: Offline (cash or mobile money)
- Backend: **PocketBase** (simple, fast, self-hosted backend)

---

## 🏷️ Name Suggestions

| Type | Name | Style |
|------|------|-------|
| 🇧🇩 Local | TajaBazaar, KachaKena, AmarKrishi, PalliFresh, DeshiFood |
| 🌾 Modern | FarmNearMe, Fresh5KM, FoodCircleBD, KrishiLink |
| 🍅 Bengali Mix | TajaDesh (তাজাদেশ), KachaMarket, PalliKinun, AmarHaat |

---

## 🧭 Main Pages / Sections

### 🏠 Home / Marketplace
- Shows all listings **within 5 km** of user’s GPS
- Product cards:
  - 📸 Photo
  - 🏷️ Name + Price
  - 👤 Seller Name
  - 🏷️ Tags (e.g. "Local Farmer", "Verified Seller")
  - 📍 Distance (e.g. 2.3 km away)
  - 📞 **Call Seller** button
- Filters:
  - Category: Vegetables / Fruits / Meat / Fish / Eggs
  - Sort by: Distance (default), Price, Newest

---

### 📦 Product Details
- Photos + Description
- Price per unit / kg
- Tags (trust + category)
- Seller Info:
  - Name
  - Location
  - Phone number (tap-to-call)
- Distance (auto from GPS)
- “Share” button for WhatsApp / Messenger

---

### 👩‍🌾 Seller Profile
- Seller name + profile photo  
- Tags and badges  
- Location (map pin)  
- Phone number (click-to-call)  
- Seller description (“Small poultry farm in Gazipur”)  
- List of seller’s active products  

---

### 🧑‍🌾 Post a Product
Form fields:
- Product Name  
- Category (Vegetable, Fruit, Meat, Fish, Egg)  
- Description  
- Price (per kg/unit)  
- Stock quantity  
- Photos (max 5)  
- Seller Name  
- Phone Number  
- Auto GPS Location  
- Tags (select multiple)  
- Checkbox: “I confirm the product is fresh and safe.”

---

### ⚙️ Admin Panel (PocketBase Dashboard)
- Approve / reject new listings  
- Manage seller tags and badges  
- Moderate content  
- Basic analytics:
  - Total sellers  
  - Active listings  
  - Top product categories  

---

## 🏷️ Seller Tags

| Tag | Description |
|------|-------------|
| ✅ Verified Seller | Approved by admin |
| 🚜 Local Farmer | Grows or produces own goods |
| 🐄 Livestock Seller | Meat or fish producer |
| 🌿 Organic Produce | Grown without chemicals |
| 🏠 Home Producer | Small-scale home grower |
| 🧺 Wholesale Seller | Sells in bulk |
| 🌾 Village Producer | Sells from rural area |
| 💚 Trusted Seller | Consistently active and rated well |
| 🔁 Regular Supplier | Posts fresh items frequently |
| 🌤️ Fresh Today | Recently harvested or prepared |
| 📦 Bulk Available | Shop or reseller-friendly |

---

## 📍 Location Filtering (5 KM Limit)
- App requests user GPS on open  
- PocketBase stores product lat/lon fields  
- Products filtered using **Haversine distance calculation** on frontend before display  
- Only listings ≤ 5 km shown  

---

## ⚙️ Tech Stack

| Component | Technology |
|------------|-------------|
| **Backend** | PocketBase (Go + SQLite embedded backend) |
| **Database** | Built-in SQLite (fast, local-friendly) |
| **Frontend** | React / Next.js (mobile-first PWA) |
| **Geo Query** | Haversine distance (frontend filtering) |
| **Image Storage** | PocketBase file storage |
| **Authentication** | PocketBase Auth (optional Google login) |
| **Admin Panel** | PocketBase Admin UI |
| **Map Display** | Leaflet.js or Google Maps |
| **Deployment** | Railway / Render / VPS (small self-hosted instance) |

---

## 🧭 User Flow

1. **Buyer opens app**
   - GPS location requested  
   - Product listings within 5 km loaded  

2. **Browse**
   - See nearby vegetables, fruits, meat, fish, eggs  
   - Filter or sort listings  

3. **View Product**
   - Show description, price, seller info, distance  
   - Tap **📞 Call Seller**  

4. **Offline Transaction**
   - Buyer and seller complete deal directly  

5. **Seller adds new product**
   - Uploads via simple form  
   - Admin approves before listing appears  

---

## 🎯 Core Principles

- 🥦 **Local-first:** Limit view to 5 km radius  
- 🧑‍🌾 **Farmer-friendly:** Simple UI, offline contact  
- 💡 **Low-tech access:** Lightweight PWA, works on low-end Android  
- 💬 **Offline communication:** Direct calls only, no chat system  
- 🌱 **Trust & Transparency:** Verified and organic tags  

---

## 🧩 Future Add-ons (Optional)
- Multi-language (Bangla + English)
- Delivery partner integration (for local cooperatives)
- “Freshness” expiry indicator (auto-hide after 48 hours)
- Tag-based search suggestions (e.g. “organic”, “home grower”)

---

## 💰 Monetization Ideas for Neighborhood Fresh Food Marketplace

A hyperlocal marketplace in Bangladesh connecting **local farmers, butchers, and buyers** for fresh vegetables, fruits, meat, fish, and eggs — **offline payment only**.  

Here are practical monetization options:

---

### 🥇 1. Verified Seller Subscription
- **What:** Sellers pay a monthly fee (৳100–300) to get the ✅ "Verified Seller" badge.
- **Benefits:** Higher trust, top search visibility, “Featured Farmer” badge.
- **Implementation:** Add `is_premium` or `verified_until` field in PocketBase.

---

### 📢 2. Featured Product Promotion
- **What:** Promote one or more listings to appear on top of Home page.
- **Pricing:** ৳30 for 3 days per product.
- **Display:** Highlight with ⭐ “Featured Listing” badge.
- **Payment:** Offline, admin toggles `is_featured = true` in PocketBase.

---

### 🧺 3. Offline Agent Model
- **What:** Local agents register farmers (collect info/photos, verify them).
- **Revenue:** Agents earn commission per seller onboarded (e.g., ৳50 each).
- **Benefit:** Scales rural adoption quickly.

---

### 🪧 4. Local Ads / Sponsor Banners
- **Who:** Fertilizer sellers, seed stores, packaging suppliers.
- **What:** Small banner in app footer or sidebar.
- **Pricing:** Monthly fee (৳500–1000).
- **Implementation:** PocketBase collection `ads` with image + link + duration.

---

### 🚜 5. Wholesale / B2B Lead Service
- **What:** Connect farmers with shopkeepers or restaurants.
- **Revenue:** Buyers pay to access bulk supplier contacts (e.g., ৳200 per list).

---

### 🧑‍🌾 6. Local Co-op / NGO Partnerships
- **What:** Offer dashboards and analytics for cooperatives, NGOs, or government offices.
- **Revenue:** Subscription or project partnership (CSR programs, rural digitization).

---

### 🧭 7. Freshness Badge System
- **What:** Sellers pay to display freshness badges:
  - 🌿 “Fresh Today”
  - 🧺 “Harvested This Morning”
- **Price:** ৳10–20 per badge per listing.
- **Purpose:** Boost visibility like a micro-promotion.

---

### 🧾 8. SMS Notification Service
- **What:** Buyers receive SMS alerts when nearby sellers post new items.
- **Pricing:** Buyers pay subscription (৳30/month) or per-alert fee.
- **Example:** “New organic tomato 2 km away at ৳40/kg.”

---

### 📦 9. Delivery Partner Integration (Later Stage)
- **What:** Partner with local rickshaw/van delivery services.
- **Revenue:** Commission per delivery (10–15%).
- **Flow:** Seller selects “Need delivery” → agent notified.

---

### 💡 10. Data Insights / Analytics (B2B)
- **What:** Sell aggregated, anonymized market data to:
  - NGOs, farmer associations, local government
- **Examples:** “Top 10 crops traded in Gazipur”, “Weekly egg price trends”.
- **Revenue:** Paid reports or subscription.

---

## 💵 Monetization Summary Table

| Idea | Type | Revenue Mode | Stage |
|------|------|--------------|-------|
| Verified Seller Subscription | Recurring | ৳100–300/month | Early |
| Featured Product Boost | Per-listing | ৳30–50/listing | Early |
| Agent Onboarding Program | Commission | Pay per seller onboarded | Growth |
| Local Ads / Banners | Monthly | ৳500–1000/month | Growth |
| Wholesale Contact Access | One-time | ৳200–500 | Growth |
| NGO / Co-op Partnership | B2B | Subscription | Later |
| Freshness Badges | Micro-payment | ৳10–20 | Early |
| SMS Alerts | Subscription | ৳30/month | Mid |
| Delivery Partner Fees | Commission | 10–15% | Later |
| Data Insights | B2B | Paid reports | Advanced |

---

# 📦 PocketBase Schema Design for Neighborhood Fresh Food Marketplace (with Buyers)

This schema supports:
- Hyperlocal listings (≤ 5 km)
- Seller verification and premium subscription
- Featured product boosts
- Badges and freshness indicators
- Ads & promotions
- Buyers tracking (for optional features like SMS alerts, favorites)
- Offline payments

---

## 1. Collection: `sellers`

| Field | Type | Description |
|-------|------|-------------|
| `name` | text | Seller full name or farm/shop name |
| `phone_number` | text | Contact phone number |
| `location` | geopoint | Latitude/Longitude |
| `profile_photo` | file | Profile image |
| `description` | text | Short bio of farm/shop |
| `tags` | text[] | Seller tags (Verified Seller, Local Farmer, etc.) |
| `is_verified` | bool | Admin-approved seller flag |
| `is_premium` | bool | Paid premium/verified subscription |
| `premium_until` | datetime | Expiry of premium subscription |
| `created_at` | datetime | Record creation timestamp |
| `updated_at` | datetime | Record last updated timestamp |

---

## 2. Collection: `products`

| Field | Type | Description |
|-------|------|-------------|
| `name` | text | Product name (Tomato, Egg, etc.) |
| `category` | select | Vegetable / Fruit / Meat / Fish / Egg |
| `description` | text | Product details, origin info |
| `price_per_unit` | number | Price per kg/unit |
| `stock_quantity` | number | Available stock |
| `photos` | file[] | Multiple images (max 5) |
| `seller` | relation | Link to `sellers` collection |
| `location` | geopoint | Auto-fill from seller or custom |
| `tags` | text[] | Product tags (Fresh Today, Organic, Bulk Available) |
| `is_featured` | bool | Paid featured listing flag |
| `created_at` | datetime | Record creation timestamp |
| `updated_at` | datetime | Record last updated timestamp |

---

## 3. Collection: `buyers`

| Field | Type | Description |
|-------|------|-------------|
| `name` | text | Buyer full name |
| `phone_number` | text | Contact number |
| `location` | geopoint | Latitude/Longitude (for 5 km filtering) |
| `favorites` | relation[] | Favorite products (links to `products`) |
| `notifications_enabled` | bool | SMS / push notifications preference |
| `created_at` | datetime | Record creation timestamp |
| `updated_at` | datetime | Record last updated timestamp |

---

## 4. Collection: `ads`

| Field | Type | Description |
|-------|------|-------------|
| `title` | text | Short ad title |
| `image` | file | Banner image |
| `link` | text | Optional URL (website or WhatsApp) |
| `start_date` | datetime | When ad starts showing |
| `end_date` | datetime | When ad stops showing |
| `active` | bool | Admin toggle for display |
| `location` | geopoint | Optional targeting by area |
| `created_at` | datetime | Record creation timestamp |
| `updated_at` | datetime | Record last updated timestamp |

---

## 5. Collection: `transactions` (Optional)

> Tracks boosts, subscriptions, badges, and admin revenue.

| Field | Type | Description |
|-------|------|-------------|
| `seller` | relation | Link to `sellers` |
| `buyer` | relation (optional) | Link to `buyers` (if buyer paid for SMS alerts or subscriptions) |
| `type` | select | Subscription / Featured Listing / Badge / SMS Alert |
| `amount` | number | Amount paid (in BDT) |
| `status` | select | Pending / Confirmed / Expired |
| `start_date` | datetime | Payment or service start |
| `end_date` | datetime | Expiry of service/feature |
| `notes` | text | Optional admin notes |
| `created_at` | datetime | Record creation timestamp |
| `updated_at` | datetime | Last updated timestamp |

---

## 6. PocketBase Relations

- **Products → Sellers:** Many-to-One (`product.seller`)  
- **Products → Buyers:** Many-to-Many via `favorites` (optional)  
- **Ads → Location (optional):** Geo-targeting for local promotions  
- **Transactions → Sellers / Buyers:** Track monetization  
