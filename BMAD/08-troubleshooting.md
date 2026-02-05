# Troubleshooting

## Common Issues

### 1. Images not loading
- **Cause**: `VITE_STRAPI_URL` is wrong or missing.
- **Fix**: Check `.env`. Images in Strapi are relative paths (e.g. `/uploads/img.jpg`); the frontend appends the base URL.

### 2. API 403 Forbidden
- **Cause**: Backend permissions.
- **Fix**: Go to Strapi Admin → Settings → Roles → Public. Enable `find` for Product and `createCheckoutSession` for Payment.

### 3. CORS Error
- **Cause**: Backend refusing connection.
- **Fix**: Ensure `config/middlewares.ts` in Backend has `strapi::cors` enabled.

### 4. "Process is not defined"
- **Cause**: Using `process.env` in Vite.
- **Fix**: Use `import.meta.env` instead.

## Debugging Tips

- **Network Tab**: Inspect the HTTP request/response in Chrome DevTools.
- **Console**: Check for red error messages.
- **Env**: Log `import.meta.env.VITE_STRAPI_URL` to verify it's loaded.
