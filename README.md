# BMAD Frontend (React + Vite)

This directory contains the React 18 Single Page Application (SPA) for the Demo store. It connects to the Strapi backend for data and Stripe for payments.

**Live Storefront (Vercel):** [https://demo-store-final.vercel.app](https://demo-store-final.vercel.app)
- **Source Code to Backend Repo**: [https://github.com/talekarnishita/demo-backend-final](https://github.com/talekarnishita/demo-backend-final)

## 📂 Project Structure

The codebase is organized by **feature** and **layer**:

```
frontend/
├── src/
│   ├── api/                    # 📡 API Interaction Layer
│   │   ├── client.ts           # Base fetch wrapper (handles URLs & Auth)
│   │   ├── products.ts         # Product fetching functions
│   │   └── payments.ts         # Payment/Checkout endpoints
│   │
│   ├── context/                # 💾 Global State
│   │   └── CartContext.tsx     # Shopping cart state management
│   │
│   ├── hooks/                  # 🎣 Custom React Hooks
│   │   ├── useProducts.ts      # Data fetching logic
│   │   └── useCheckout.ts      # Payment flow logic
│   │
│   ├── pages/                  # 📄 Route Components
│   │   ├── Home.tsx            # Landing page
│   │   ├── ProductList.tsx     # Catalog grid view
│   │   ├── Cart.tsx            # Shopping cart view
│   │   └── CheckoutDemo.tsx    # Payment initiation
│   │
│   ├── services/               # ⚙️ Business Logic
│   │   └── stripe.ts           # Stripe redirection handler
│   │
│   ├── types/                  # 📐 TypeScript Definitions
│   │   ├── product.ts          # Product interfaces
│   │   └── order.ts            # Order interfaces
│   │
│   ├── utils/                  # 🛠️ Helper Functions
│   │   └── strapiMedia.ts      # Image URL resolver
│   │
│   ├── App.tsx                 # Main layout & router setup
│   └── main.tsx                # Application entry point
│
├── .env                        # Environment variables
└── vite.config.ts              # Vite build configuration
```

## 🚀 Quick Start

### Prerequisites
- Node.js >= 18
- npm

### Setup

1. **Install Dependencies**:
   ```bash
   npm install
   ```

2. **Configure Environment**:
   Create a `.env` file (or copy example):
   ```bash
   # .env
   VITE_STRAPI_URL=http://localhost:1337
   # Optional: VITE_API_TOKEN=...
   ```

3. **Start Development Server**:
   ```bash
   npm run dev
   ```
   Access the store at [http://localhost:5173](http://localhost:5173).

## 📚 Documentation

Detailed documentation is available in the `../docs/frontend/` folder:

- [Architecture & Tech Stack](../docs/frontend/01-architecture-tech-stack.md)
- [Application Flow](../docs/frontend/03-application-flow.md)
- [API Integration](../docs/frontend/05-api-integration.md)
- [Deployment (Vercel)](../docs/frontend/07-deployment-vercel.md)

## 🛠 Features

- **Product Catalog**: Fetched dynamically from Strapi.
- **Shopping Cart**: Managed via React Context (add, remove, update quantities).
- **Checkout**: Integrated with backend-driven Stripe Checkout sessions.
- **Responsive Design**: Built with pure CSS/JSX for clarity.
