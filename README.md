# Online Food Kitchen

A multi-vendor food marketplace that enables home cooks, restaurants, cafés,
bakeries, caterers, chefs, food trucks and other food businesses to create
digital storefronts, sell food online, receive payments and access delivery —
while customers discover, order, pay and track food from vendors around them.

> Not every food seller needs a restaurant. Every food seller needs a market.

## Repository layout

| Folder | Contents |
| --- | --- |
| `frontend/` | Mobile-first React (Vite) customer app — homepage feed, category navigation, nearby vendors, global search, vendor storefronts. See [frontend/README.md](frontend/README.md) for setup, environment variables and how to test location-based features. |
| `backend/` | Node/Express API for discovery, OTP customer auth, cart, wishlist, checkout, orders, and tracking. |

## Quick start (frontend)

```bash
cd frontend
npm install
npm run dev        # http://localhost:3000
```

The frontend consumes these backend endpoints (see `frontend/README.md` for the
full contract and mock-mode details):

- `GET /api/v1/home/feed?lat={lat}&lng={lng}`
- `GET /api/v1/home/categories`
- `GET /api/v1/home/vendors/nearby?lat={lat}&lng={lng}&radius={km}&category_id={id}`
- `GET /api/v1/home/search?q={query}&lat={lat}&lng={lng}`
- `GET /api/v1/vendors/{vendor_id}`
- `POST /api/v1/auth/send-otp` and `POST /api/v1/auth/verify-otp`
- Authenticated cart, wishlist, checkout, order-history, tracking, and cancellation endpoints
