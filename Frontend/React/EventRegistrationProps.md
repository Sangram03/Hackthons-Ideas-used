### 📘 `EventRegistrationProps` in React – In Detail

In a React + TypeScript project, `EventRegistrationProps` is a **TypeScript interface or type alias** used to define the **props (input data)** passed into an `EventRegistration` component.

It ensures **type safety**, **auto-completion**, and helps avoid bugs by enforcing which props are allowed and what types they should be.

---

## 🧩 Syntax – Basic Structure

```ts
interface EventRegistrationProps {
  eventId: string;
  eventName: string;
  userId?: string; // Optional
  onRegister: (eventId: string) => void;
}
```

This example defines:

| Prop Name    | Type                  | Description                                       |
| ------------ | --------------------- | ------------------------------------------------- |
| `eventId`    | `string`              | Unique identifier for the event                   |
| `eventName`  | `string`              | Name/title of the event                           |
| `userId`     | `string` *(optional)* | ID of the user registering                        |
| `onRegister` | Function              | A callback function that runs when user registers |

---

## 📦 How to Use It in a Component

### 1. Define the Props Type

```ts
interface EventRegistrationProps {
  eventId: string;
  eventName: string;
  onRegister: (eventId: string) => void;
}
```

### 2. Use It in the Component

```tsx
const EventRegistration: React.FC<EventRegistrationProps> = ({
  eventId,
  eventName,
  onRegister
}) => {
  return (
    <div>
      <h2>{eventName}</h2>
      <button onClick={() => onRegister(eventId)}>Register</button>
    </div>
  );
};
```

---

## ✅ Benefits of Using Props Interfaces

| Advantage                | Explanation                                                      |
| ------------------------ | ---------------------------------------------------------------- |
| 🛡️ Type Safety          | Prevents bugs from incorrect props                               |
| ✍️ Autocomplete Support  | Editors like VS Code show suggestions                            |
| ❌ Prevents Invalid Props | Helps you avoid missing required fields                          |
| 📚 Self-Documentation    | Easy for other developers to know what props a component expects |

---

## 🧪 Usage Example in a Parent Component

```tsx
<EventRegistration
  eventId="123"
  eventName="React Bootcamp"
  onRegister={(id) => console.log("Registered for event:", id)}
/>
```

---

## 🧠 Tip

You can also define it as a `type`:

```ts
type EventRegistrationProps = {
  eventId: string;
  eventName: string;
  onRegister: (id: string) => void;
};
```

---

