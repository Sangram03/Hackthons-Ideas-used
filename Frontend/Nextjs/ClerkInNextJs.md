## **1️⃣ Install Clerk packages**

In your project directory:

```bash
npm install @clerk/nextjs
# or
yarn add @clerk/nextjs
```

---

## **2️⃣ Get your Clerk API keys**

1. Go to [Clerk Dashboard](https://dashboard.clerk.com).
2. Create an application.
3. Copy:

   * **Publishable Key** → `NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY`
   * **Secret Key** → `CLERK_SECRET_KEY`

---

## **3️⃣ Add them to `.env.local`**

```env
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=pk_test_****************
CLERK_SECRET_KEY=sk_test_****************
```

---

## **4️⃣ Wrap your app in `ClerkProvider`**

In **`app/layout.tsx`** (Next.js App Router) or **`pages/_app.tsx`** (Pages Router):

### App Router example (`app/layout.tsx`)

```tsx
// app/layout.tsx
import { ClerkProvider } from '@clerk/nextjs';
import './globals.css';

export default function RootLayout({ children }) {
  return (
    <ClerkProvider>
      <html lang="en">
        <body>{children}</body>
      </html>
    </ClerkProvider>
  );
}
```

---

## **5️⃣ Protect routes (authentication)**

Example with **App Router**:

```tsx
// app/protected/page.tsx
import { currentUser } from '@clerk/nextjs';

export default async function ProtectedPage() {
  const user = await currentUser();

  if (!user) {
    return <div>You must sign in to view this page.</div>;
  }

  return <div>Welcome, {user.firstName}!</div>;
}
```

Example with **Pages Router**:

```tsx
// pages/protected.tsx
import { SignedIn, SignedOut, UserButton } from '@clerk/nextjs';

export default function Protected() {
  return (
    <>
      <SignedIn>
        <UserButton afterSignOutUrl="/" />
        <p>Welcome to the protected page!</p>
      </SignedIn>
      <SignedOut>
        <p>Please sign in to access this page.</p>
      </SignedOut>
    </>
  );
}
```

---

## **6️⃣ Add sign-in and sign-up pages**

```bash
npx clerk add sign-in
npx clerk add sign-up
```

Or create them manually:

```tsx
// app/sign-in/[[...sign-in]]/page.tsx
import { SignIn } from '@clerk/nextjs';

export default function Page() {
  return <SignIn />;
}

// app/sign-up/[[...sign-up]]/page.tsx
import { SignUp } from '@clerk/nextjs';

export default function Page() {
  return <SignUp />;
}
```

---

## **7️⃣ Use Clerk hooks in components**

Example:

```tsx
import { useUser } from '@clerk/nextjs';

export default function Dashboard() {
  const { isLoaded, user } = useUser();

  if (!isLoaded) return <div>Loading...</div>;

  return <div>Hello, {user?.firstName}!</div>;
}
```

---

✅ **That’s it** — now Clerk is integrated and you can use authentication across your Next.js app.

---

