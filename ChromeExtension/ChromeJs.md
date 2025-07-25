## ✅ Chrome Extensions — What Are They?

Chrome extensions are small programs that **enhance the Chrome browser**. Built-in extensions like:

* **Google Docs Offline**
* **Google Translate**
* **YouTube Enhancer**
* **Ad blocker (enterprise setups)**
  use the same **Chrome Extension APIs** that any developer can use.

---

## 🧠 Key Components of a Chrome Extension

Every Chrome extension has these core files:

### 1. `manifest.json` – Extension configuration

```json
{
  "manifest_version": 3,
  "name": "My Extension",
  "version": "1.0",
  "permissions": ["tabs", "storage", "scripting"],
  "background": {
    "service_worker": "background.js"
  },
  "action": {
    "default_popup": "popup.html"
  }
}
```

### 2. JavaScript Files

Logic is written here using the `chrome.*` APIs.

---

## 📦 Chrome Extension APIs (Used in Built-in Extensions)

These are some **key APIs** built-in Chrome extensions use and **you can too**:

### 🔹 `chrome.tabs`

* Open, update, or remove browser tabs

```js
chrome.tabs.create({ url: "https://example.com" });
```

### 🔹 `chrome.runtime`

* Communicate between background and content scripts

```js
chrome.runtime.sendMessage({ greeting: "hello" });
```

### 🔹 `chrome.storage`

* Store key-value data

```js
chrome.storage.local.set({ user: "Sangram" });
```

### 🔹 `chrome.scripting` *(MV3)*

* Inject JS/CSS into pages

```js
chrome.scripting.executeScript({
  target: { tabId: tab.id },
  files: ["content.js"]
});
```

### 🔹 `chrome.contextMenus`

* Add right-click context menu options

```js
chrome.contextMenus.create({
  id: "myMenu",
  title: "Click Me",
  contexts: ["page"]
});
```

### 🔹 `chrome.notifications`

* Show native notifications

```js
chrome.notifications.create({
  type: "basic",
  iconUrl: "icon.png",
  title: "Hello!",
  message: "This is a notification"
});
```

### 🔹 `chrome.identity`

* Login and get Google user data (used in Google Translate, Docs Offline)

```js
chrome.identity.getProfileUserInfo(function(userInfo) {
  console.log(userInfo.email);
});
```

---

## 📥 Chrome Built-In Extensions Use These Too:

| Extension               | APIs                                                 |
| ----------------------- | ---------------------------------------------------- |
| Google Translate        | `tabs`, `scripting`, `identity`, `storage`           |
| Docs Offline            | `identity`, `storage`, `fileSystem`, `notifications` |
| Chrome Password Manager | `identity`, `storage`, `tabs`, `webNavigation`       |

---

## 🔐 Permissions Example (in manifest.json)

```json
"permissions": [
  "tabs",
  "storage",
  "identity",
  "notifications",
  "contextMenus",
  "scripting"
],
"host_permissions": ["<all_urls>"]
```

---

## 📁 Chrome Extension File Structure (Typical)

```
my-extension/
├── manifest.json
├── background.js
├── popup.html
├── popup.js
├── content.js
├── icons/
│   └── icon.png
```

---

## 🧪 View Chrome’s Built-In Extensions

You can **inspect built-in extensions** in Chrome:

1. Go to: `chrome://extensions`
2. Enable **Developer Mode** (top right)
3. Built-in extensions like Docs Offline will be visible
4. Click **“Inspect views”** to open dev tools

---

## 🛠 Want a Starter Template?

I can give you a full working extension template (with tabs, popup, content script).
Just say: `give me a Chrome extension starter with popup and tab actions`.

