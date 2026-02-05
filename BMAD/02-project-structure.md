# Project Structure

The frontend codebase is organized by **feature type** rather than file type.

```
frontend/
├── src/
│   ├── api/                    # 📡 API Interaction Layer
│   │   ├── client.ts           # Base fetch wrapper (handles URLs & Auth)
│   │   ├── products.ts         # Product-related endpoints
│   │   └── payments.ts         # Payment-related endpoints
│   │
│   ├── context/                # 💾 Global State
│   │   └── CartContext.tsx     # Shopping cart logic (Add/Remove items)
│   │
│   ├── hooks/                  # 🎣 Custom React Hooks
│   │   ├── useProducts.ts      # Logic to fetch and store products
│   │   └── useCheckout.ts      # Logic to handle payment flow
│   │
│   ├── pages/                  # 📄 Route Components
│   │   ├── Home.tsx            # Landing page
│   │   ├── ProductList.tsx     # Product catalog
│   │   ├── Cart.tsx            # Shopping cart view
│   │   └── CheckoutDemo.tsx    # Payment initiation page
│   │
│   ├── services/               # ⚙️ Business Logic
│   │   └── stripe.ts           # Stripe redirection handler
│   │
│   ├── types/                  # 📐 TypeScript Definitions
│   │   └── product.ts          # Interfaces for Product data
│   │
│   ├── utils/                  # 🛠️ Helpers
│   │   └── strapiMedia.ts      # Image URL formatter
│   │
│   ├── App.tsx                 # Main layout & routing
│   └── main.tsx                # Entry point
│
├── .env                        # Environment variables
└── vite.config.ts              # Build configuration
```
