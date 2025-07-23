## 🔗 `href` vs `src`

| Feature   | `href`                                  | `src`                                                                |
| --------- | --------------------------------------- | -------------------------------------------------------------------- |
| Full Form | **H**ypertext **Ref**erence             | **S**ou**r**ce                                                       |
| Purpose   | Specifies the **location of a link**    | Specifies the **source of a resource** (like an image, script, etc.) |
| Used In   | `<a>`, `<link>`, `<base>`               | `<img>`, `<script>`, `<iframe>`, `<video>`, `<audio>`                |
| Behavior  | Browser **continues loading** the page  | Browser **stops loading** and waits for the resource                 |
| Usage     | Navigational (link to another resource) | Embedding content directly into the document                         |

---

## 🔎 Examples

### ✅ `href` – Used to Link to Other Resources

#### In `<a>` (anchor tag):

```html
<a href="https://example.com">Visit Site</a>
```

#### In `<link>` (external CSS):

```html
<link rel="stylesheet" href="styles.css">
```

---

### ✅ `src` – Used to Embed Resources

#### In `<img>`:

```html
<img src="image.jpg" alt="An image">
```

#### In `<script>`:

```html
<script src="app.js"></script>
```

#### In `<iframe>`:

```html
<iframe src="https://example.com"></iframe>
```

---

## 🧠 Behind the Scenes (Loading Behavior)

### `src`: Blocking

When the browser encounters a `src`, like:

```html
<script src="main.js"></script>
```

it **stops rendering** the page until `main.js` is fully loaded.

### `href`: Non-blocking

When the browser sees:

```html
<link href="style.css" rel="stylesheet">
```

it **continues parsing**, and loads the stylesheet in parallel.

---

## ⚠️ Common Mistake

Using `src` where `href` is needed (and vice versa):

❌ Wrong:

```html
<a src="page.html">Click me</a> <!-- src is invalid for <a> -->
```

✅ Correct:

```html
<a href="page.html">Click me</a>
```

---

## ✅ Summary

| Attribute | Use For                  | Loads As               | Example Use                     |
| --------- | ------------------------ | ---------------------- | ------------------------------- |
| `href`    | Links (navigation, CSS)  | Hyperlinks/Stylesheets | `<a>`, `<link>`                 |
| `src`     | Embeds (image, JS, etc.) | External resource      | `<img>`, `<script>`, `<iframe>` |

---

