
```js
chrome.runtime.onMessage.addListener((req, _sender, sendResponse) => {
  if (req.type === "GET_ARTICLE_TEXT") {
    const text = getArticleText();
    sendResponse({ text });
  }
});
```

---

### 🔍 What it does:

| Part                                        | Explanation                                                                       |
| ------------------------------------------- | --------------------------------------------------------------------------------- |
| `chrome.runtime.onMessage.addListener(...)` | This listens for messages sent from other extension parts.                        |
| `req`                                       | The message object sent. It usually includes a `type` field.                      |
| `if (req.type === "GET_ARTICLE_TEXT")`      | Filters only the messages where the `type` is `"GET_ARTICLE_TEXT"`.               |
| `getArticleText()`                          | A function you define elsewhere that likely extracts or reads the page's content. |
| `sendResponse({ text })`                    | Sends the extracted text back to the sender (e.g., popup or background script).   |

---

### ✅ Example Use Case (in a Chrome Extension):

**In your popup.js:**

```js
chrome.tabs.query({ active: true, currentWindow: true }, (tabs) => {
  chrome.tabs.sendMessage(tabs[0].id, { type: "GET_ARTICLE_TEXT" }, (response) => {
    console.log("Article text:", response.text);
  });
});
```

**In your content script (like the one you posted):**

```js
chrome.runtime.onMessage.addListener((req, _sender, sendResponse) => {
  if (req.type === "GET_ARTICLE_TEXT") {
    const text = getArticleText();  // your custom logic
    sendResponse({ text });
  }
});
```

---

### 🛠 Important Note:

If `getArticleText()` is **asynchronous**, you **must return `true`** to keep the message channel alive:

```js
chrome.runtime.onMessage.addListener((req, _sender, sendResponse) => {
  if (req.type === "GET_ARTICLE_TEXT") {
    getArticleTextAsync().then(text => {
      sendResponse({ text });
    });
    return true; // <== Keeps the channel open
  }
});
```

---
