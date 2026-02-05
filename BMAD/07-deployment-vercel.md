# Deployment (Vercel)

The frontend is optimized for deployment on Vercel.

## Deployment Steps

1. **Push to GitHub**: Ensure your code is committed.
2. **Import to Vercel**: Select the repository in Vercel Dashboard.
3. **Configure Build Settings**:
   - **Framework Preset**: Vite
   - **Build Command**: `npm run build`
   - **Output Directory**: `dist`
4. **Environment Variables**:
   - `VITE_STRAPI_URL`: `https://strapi-pf5p.onrender.com`
   - `VITE_API_TOKEN`: (Your Strapi API Token)

## Production Build

To test the production build locally:

```bash
npm run build
npm run start
```
This serves the optimized `dist/` folder using `serve`.
