# API Integration

All backend interactions are centralized in `src/api/`.

## API Client (`client.ts`)

- **Base URL**: Loaded from `VITE_STRAPI_URL` env var.
- **Auth**: Automatically attaches `Authorization: Bearer <token>` if `VITE_API_TOKEN` is set.
- **Error Handling**: Throws standard errors for non-200 responses.

## Endpoints

### Products (`products.ts`)
- `getProducts()`: Fetches list.
- `getProductBySlug(slug)`: Fetches single details.

### Payments (`payments.ts`)
- `createCheckoutSession(amount, ...)`: Calls custom backend route.

## Authentication

Authentication is handled via the **Bearer Token** pattern. The token is stored in `.env` (for public/demo access) or could be implemented with user login logic.

```bash
# .env
VITE_API_TOKEN=your_strapi_api_token
```
