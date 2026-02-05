# Routing & Pages

We use **React Router DOM v6** for client-side routing.

## Configuration

Defined in `App.tsx`:

```tsx
<Routes>
  <Route path="/" element={<Home />} />
  <Route path="/products" element={<ProductList />} />
  <Route path="/cart" element={<Cart />} />
  <Route path="/checkout-demo" element={<CheckoutDemo />} />
</Routes>
```

## Page Breakdown

### 1. Home (`/`)
Landing page. Simple navigation entry point.

### 2. ProductList (`/products`)
- Fetches data using `useProducts()` hook.
- Displays a grid of `ProductCard` components.
- Handles "Loading" and "Error" states.

### 3. Cart (`/cart`)
- Reads `CartContext`.
- Allows updating quantities or removing items.
- Calculates totals dynamically.

### 4. CheckoutDemo (`/checkout-demo`)
- The "Cash Register".
- Calls `useCheckout()` to trigger the Stripe redirect.
