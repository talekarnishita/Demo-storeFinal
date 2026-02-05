# State Management (Cart Context)

We use **React Context API** to manage the shopping cart state globally. This allows the cart data to be accessible from the Header (badge count), Product List (add to cart), and Checkout page.

## Key Components

- **File**: `src/context/CartContext.tsx`
- **State**:
  - `items`: Array of products and their quantities.
  - `totalCount`: Total number of items (derived).
  - `totalAmount`: Total price (derived).

## How it works

The `CartProvider` wraps the app in `main.tsx`.

### Actions

| Action | Description |
|--------|-------------|
| `addItem(product)` | Adds a product. If it exists, increments quantity. |
| `removeItem(id)` | Removes a product completely. |
| `updateQuantity(id, qty)` | Changes the quantity of a specific item. |
| `clearCart()` | Empties the cart. |

### Usage Example

```typescript
import { useCart } from '@/context/CartContext';

function AddButton({ product }) {
  const { addItem } = useCart();
  return <button onClick={() => addItem(product)}>Add</button>;
}
```
