# API Creation for Production (React + Strapi + Vercel)

## Stack

- **Frontend**: React (Vite), deployed on **Vercel**.
- **Backend / CMS**: **Strapi** (Node 20). Deployed on **Render** (or Railway).
- **Payments**: Stripe.

## Production API Checklist

1. **Base URL from env**
   - Frontend: `VITE_STRAPI_URL=https://strapi-pf5p.onrender.com` (or your production URL).
   - All API calls use this base (see `frontend/src/api/client.ts`).

2. **API Tokens (Authentication)**
   - If your API requires authentication (or for safety), generate an **API Token** in Strapi Admin (Settings → API Tokens).
   - Add to Frontend Env: `VITE_API_TOKEN=<your_token>`.
   - The frontend client (`client.ts`) automatically adds `Authorization: Bearer <token>` if this variable is set.

3. **CORS**
   - Strapi: In `config/middlewares.ts`, ensure `strapi::cors` is enabled (default is `*`, which works).
   - If you restrict CORS, add your Vercel domain (e.g. `https://demo-store-final.vercel.app`).

4. **Stripe**
   - **Backend**: Set `STRIPE_SECRET_KEY` in Render Dashboard.
   - **Frontend**: Does not need the secret key.

## Where APIs Live

- **Strapi REST**: Auto-generated from content types.
  - e.g. `GET /api/products`
- **Custom Strapi route**: `POST /api/payments/create-checkout-session` in `backend/src/api/payment/`.

## Learning Path (1–2 Hours)

1. **0–20 min**: Run Strapi + React locally; call `GET /api/products`.
2. **20–40 min**: Add content type `payment` (or `order`); add types in frontend.
3. **40–60 min**: Add Stripe route; frontend “Pay” button calls it.
4. **60–90 min**: Deploy frontend to Vercel (set `VITE_STRAPI_URL`, `VITE_API_TOKEN`); Deploy Strapi to Render (set `STRIPE_SECRET_KEY`).
5. **90–120 min**: Test end-to-end; verified images load and checkout redirects.

Use [04 – Modular context window](../04-modular-context-window.md) so each step stays in one module for Cursor.
