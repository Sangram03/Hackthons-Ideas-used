## **1️⃣ Prerequisites**

Make sure you have:

* **Node.js** (LTS version recommended — check with `node -v`)
* **npm** (comes with Node.js) or **yarn**/**pnpm** as a package manager
* A code editor (VS Code recommended)

---

## **2️⃣ Create a New Next.js App**

You can create a Next.js project using:

**With npm:**

```bash
npx create-next-app@latest
```


<img alt="Image" src="https://github.com/user-attachments/assets/10a97c21-1706-487f-bb2d-95f800b0b2b9" />

**With yarn:**

```bash
yarn create next-app 
```

**With pnpm:**

```bash
pnpm create next-app 
```

---

## **3️⃣ Choose Setup Options**

The CLI will ask:

* **TypeScript**? → `Yes` (recommended)
* **ESLint**? → `Yes`
* **Tailwind CSS**? → `Yes` (if you plan to use it)
* **Src directory**? → `Yes` or `No` (personal preference)
* **App Router** or **Pages Router** → Use **App Router** for Next.js 13+ features

This will auto-install all dependencies.

---

## **4️⃣ Move Into Project**

```bash
cd my-app
```

---

## **5️⃣ Run Development Server**

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
```

Your app will be available at:

```
http://localhost:3000
```

---

## **6️⃣ Project Structure (App Router Example)**

```
my-app/
 ├─ app/
 │   ├─ page.tsx       # Homepage
 │   ├─ layout.tsx     # Root layout
 │   └─ globals.css    # Global styles
 ├─ public/            # Static files
 ├─ package.json
 └─ next.config.js
```

---

## **7️⃣ Build for Production**

```bash
npm run build
npm start
```

---

## **8️⃣ Optional Extras**

* **Tailwind CSS** → If you didn’t enable it at setup:

```bash
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

Add `content` paths in `tailwind.config.js`:

```js
content: [
  "./app/**/*.{js,ts,jsx,tsx}",
  "./pages/**/*.{js,ts,jsx,tsx}",
  "./components/**/*.{js,ts,jsx,tsx}"
]
```

Add Tailwind imports to `globals.css`:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

---

