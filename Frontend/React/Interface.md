### 📘 `interface` in React (with TypeScript) – Full Explanation

In **React + TypeScript**, an `interface` is used to define **the shape of props, state, context, and other objects** — allowing you to **ensure type safety** and better code maintainability.

---

## ✅ What is an Interface?

An `interface` in TypeScript is a way to describe the **structure of an object** — what properties it has, and what their types are.

---

### 🔹 1. Interface for Component Props

```tsx
interface UserProps {
  name: string;
  age: number;
  isAdmin?: boolean; // optional
}

const UserCard: React.FC<UserProps> = ({ name, age, isAdmin }) => {
  return (
    <div>
      <h2>{name}</h2>
      <p>Age: {age}</p>
      {isAdmin && <p>Administrator</p>}
    </div>
  );
};
```

**Explanation:**

* `name` and `age` are required.
* `isAdmin` is optional (`?`).
* TypeScript will give you errors if props are missing or incorrect.

---

### 🔹 2. Interface for State

```tsx
interface CounterState {
  count: number;
  loading: boolean;
}

const Counter = () => {
  const [state, setState] = useState<CounterState>({ count: 0, loading: false });

  return <div>Count: {state.count}</div>;
};
```

---

### 🔹 3. Interface for Context

```tsx
interface AuthContextType {
  isLoggedIn: boolean;
  login: () => void;
  logout: () => void;
}

export const AuthContext = createContext<AuthContextType | null>(null);
```

---

### 🔹 4. Interface for Event Handling

```tsx
interface FormEvent {
  target: HTMLInputElement;
}

const handleChange = (e: React.ChangeEvent<HTMLInputElement>) => {
  console.log(e.target.value);
};
```

---

### 🔹 5. Interface for Refs

```tsx
const inputRef = useRef<HTMLInputElement>(null);
```

---

### 🧠 Benefits of Using Interfaces in React

| Benefit             | Description                                  |
| ------------------- | -------------------------------------------- |
| ✅ Type Safety       | Catches bugs at compile time                 |
| 🤖 Auto-completion  | Helps with IDEs like VS Code                 |
| 📚 Self-documenting | Makes components easier to understand        |
| 🔄 Reusable         | Can be extended and reused across components |

---

### 🆚 Interface vs Type in React

| Feature             | `interface`                  | `type`                             |
| ------------------- | ---------------------------- | ---------------------------------- |
| Extending           | Easy with `extends`          | Use `&` to combine                 |
| Declaration Merging | ✅ Supported                  | ❌ Not supported                    |
| Use Case            | Objects, classes, components | More flexible (union, tuple, etc.) |

> ✅ **Use `interface` for props & object shapes**, and `type` for unions, tuples, or more complex combinations.

---

### 📌 Example: Full Component Using Interface

```tsx
interface ProductProps {
  title: string;
  price: number;
  onAddToCart: () => void;
}

const ProductCard: React.FC<ProductProps> = ({ title, price, onAddToCart }) => {
  return (
    <div>
      <h3>{title}</h3>
      <p>${price}</p>
      <button onClick={onAddToCart}>Add to Cart</button>
    </div>
  );
};
```

---

