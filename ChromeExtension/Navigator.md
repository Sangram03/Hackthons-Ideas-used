### ✅ Common Use of `navigator`

Here are some popular properties and methods:

#### 1. **Browser Info**

```js
console.log(navigator.userAgent);
```

Shows browser and OS info (like Chrome on Windows).

---

#### 2. **Check if Online**

```js
console.log(navigator.onLine); // true or false
```

---

#### 3. **Geolocation**

```js
navigator.geolocation.getCurrentPosition((position) => {
  console.log(position.coords.latitude, position.coords.longitude);
});
```

> 🔐 Requires permission from the user.

---

#### 4. **Language**

```js
console.log(navigator.language); // e.g., "en-US"
```

---

#### 5. **Clipboard API (modern)**

```js
navigator.clipboard.writeText("Hello from clipboard!");
```

---

#### 6. **Check Browser Capabilities**

```js
console.log(navigator.cookieEnabled); // true if cookies are enabled
```

---

### 🧠 Example Use Case

```js
if (navigator.onLine) {
  alert("You're online!");
} else {
  alert("You're offline!");
}
```

---

### 🔐 Security Note:

Some `navigator` properties are **read-only**, and modern browsers restrict access to certain APIs for privacy and security.
