**EJS (Embedded JavaScript Templates)** is a simple templating language that lets you generate HTML markup with plain JavaScript.

---

## 🔹 What is EJS?

**EJS** stands for **Embedded JavaScript**. It allows you to embed JavaScript code into your HTML pages. It’s commonly used in Node.js applications (especially with Express) to render dynamic content on the server side.

---

## 🔧 How EJS Works

### 1. **Syntax**

EJS lets you embed JavaScript code in HTML using special tags:

| Syntax   | Description                                   |
| -------- | --------------------------------------------- |
| `<%= %>` | Outputs the result of the code (HTML-escaped) |
| `<%- %>` | Outputs unescaped raw HTML                    |
| `<% %>`  | Executes JavaScript code (does not output)    |
| `<%# %>` | Comment in EJS                                |
| `<%%`    | Outputs a literal `<%`                        |

---

### 2. **Installation**

```bash
npm install ejs
```

---

### 3. **Basic Example**

#### 🗂️ Folder Structure:

```
project/
├── views/
│   └── index.ejs
├── app.js
```

#### 📄 `index.ejs`

```html
<!DOCTYPE html>
<html>
<head>
  <title><%= title %></title>
</head>
<body>
  <h1>Hello, <%= name %>!</h1>
</body>
</html>
```

#### 📄 `app.js`

```js
const express = require('express');
const app = express();

app.set('view engine', 'ejs'); // Set EJS as the view engine

app.get('/', (req, res) => {
  res.render('index', { title: 'Home Page', name: 'Sangram' });
});

app.listen(3000, () => console.log('Server started on http://localhost:3000'));
```

---

### 4. **How It Works Internally**

* When the user accesses `/`, the Express server renders the `index.ejs` file.
* It injects the values `{ title: 'Home Page', name: 'Sangram' }` into the template.
* EJS processes the `<%= title %>` and `<%= name %>` expressions and returns a fully-formed HTML page.
* That HTML is sent to the browser.

---

## ✅ Use Cases

* Rendering server-side HTML pages in Express
* Creating dynamic content like user dashboards, product listings, etc.
* Easily integrating loops and conditions into HTML

---

## 🔁 EJS with Loops & Conditionals

```html
<ul>
  <% users.forEach(user => { %>
    <li><%= user %></li>
  <% }) %>
</ul>
```

```html
<% if (isLoggedIn) { %>
  <p>Welcome back!</p>
<% } else { %>
  <p>Please log in.</p>
<% } %>
```

---

## 📌 Summary

| Feature        | Details                                      |
| -------------- | -------------------------------------------- |
| Type           | Templating engine                            |
| Used With      | Node.js + Express                            |
| Benefits       | Simple, fast, readable, supports JS directly |
| File Extension | `.ejs`                                       |

