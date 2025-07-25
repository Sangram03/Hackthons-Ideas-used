To add an **icon inside an HTML input**, you typically use **icon libraries** like:

---

### ✅ Common Icon Libraries

| Library             | CDN Example                                                                    | Usage                                        |
| ------------------- | ------------------------------------------------------------------------------ | -------------------------------------------- |
| **Font Awesome**    | `https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css`    | `<i class="fa fa-user"></i>`                 |
| **Bootstrap Icons** | `https://cdn.jsdelivr.net/npm/bootstrap-icons@1.10.0/font/bootstrap-icons.css` | `<i class="bi bi-person"></i>`               |
| **Material Icons**  | `https://fonts.googleapis.com/icon?family=Material+Icons`                      | `<span class="material-icons">person</span>` |
| **Boxicons**        | `https://unpkg.com/boxicons@2.1.4/css/boxicons.min.css`                        | `<i class="bx bx-user"></i>`                 |
| **Remix Icon**      | `https://cdn.jsdelivr.net/npm/remixicon/fonts/remixicon.css`                   | `<i class="ri-user-line"></i>`               |

---

### ✅ Basic HTML Structure with Icon in Input

Use **relative positioning** to add the icon inside the input:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Input with Icon</title>

  <!-- Font Awesome CDN (you can change to others) -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">
  <style>
    .input-wrapper {
      position: relative;
      width: 300px;
    }

    .input-wrapper i {
      position: absolute;
      top: 50%;
      left: 10px;
      transform: translateY(-50%);
      color: #888;
    }

    .input-wrapper input {
      width: 100%;
      padding: 10px 10px 10px 35px; /* left space for icon */
      box-sizing: border-box;
    }
  </style>
</head>
<body>

  <div class="input-wrapper">
    <i class="fa fa-user"></i>
    <input type="text" placeholder="Enter your username">
  </div>

</body>
</html>
```

---

### ✅ How to Use Other Libraries (Example Snippets)

#### 🔹 **Bootstrap Icons**

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap-icons@1.10.0/font/bootstrap-icons.css">
<i class="bi bi-person"></i>
```

#### 🔹 **Material Icons**

```html
<link href="https://fonts.googleapis.com/icon?family=Material+Icons" rel="stylesheet">
<span class="material-icons">person</span>
```

#### 🔹 **Boxicons**

```html
<link href="https://unpkg.com/boxicons@2.1.4/css/boxicons.min.css" rel="stylesheet">
<i class='bx bx-user'></i>
```

---

### ✅ Tips

* Always place the icon inside a relatively positioned container (`.input-wrapper`).
* Use `padding-left` on input to prevent overlap.
* You can also use `::before` or `::after` in CSS, but using `<i>` or `<span>` is more flexible.

---

