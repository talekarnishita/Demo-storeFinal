# Vercel + React + Strapi (Strapi for Context Management)

## Roles

- **Vercel**: Hosts the **React** frontend.
- **Strapi**: Backend CMS and API (content types, auth, custom routes). Deployed on Render/Railway.

## Strapi as “Context” Backend

- **Content types** = your data model.
- **Admin UI** = manage content.
- **REST/GraphQL** = consumed by React.

## Deployment Overview

| Part | Where | Notes |
|------|--------|------|
| React app | Vercel | Build command `npm run build`. Set `VITE_STRAPI_URL` and `VITE_API_TOKEN`. |
| Strapi | Render | Node service. Set `DATABASE_*`, `STRIPE_SECRET_KEY`, `APP_KEYS`, etc. |
| Stripe | Stripe Dashboard | Webhooks point to your Strapi URL. |

## Env per Environment

**Frontend (Vercel)**
- `VITE_STRAPI_URL` – Strapi public URL (e.g. `https://strapi-pf5p.onrender.com`).
- `VITE_API_TOKEN` – Strapi API Token (Bearer token).
- `VITE_STRIPE_PUBLISHABLE_KEY` – optional, for Stripe.js.

**Strapi (Render)**
- Database, `APP_KEYS`, `API_TOKEN_SALT`, `ADMIN_JWT_SECRET`, `TRANSFER_TOKEN_SALT`, `JWT_SECRET`.
- `STRIPE_SECRET_KEY`.

## Quick Commands

- **Local React**: `cd frontend && npm run dev`
- **Local Strapi**: `cd backend && npm run develop`
- **Build for Vercel**: `cd frontend && npm run build`
- **Strapi build**: `cd backend && npm run build` (for production).
