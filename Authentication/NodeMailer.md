### Docs :- https://nodemailer.com/

`nodemailer` is a **Node.js module** that allows you to **send emails directly from your backend server**—without relying on a third-party email service dashboard.

---

### 📬 Why Use Nodemailer?

If you're building a web app and need features like:

* Sending verification or welcome emails 📩
* Sending password reset links 🔐
* Sending contact form submissions or notifications 📥

…then **Nodemailer** is one of the easiest and most popular tools for doing this in Node.js.

---

### ✅ Basic Installation:

```bash
npm install nodemailer
```

---

### 📦 Basic Example (Gmail):

```js
import nodemailer from 'nodemailer';

const sendMail = async () => {
  // 1. Create a transporter
  const transporter = nodemailer.createTransport({
    service: 'gmail',
    auth: {
      user: 'your-email@gmail.com',
      pass: 'your-app-password', // Not your Gmail password! Use an app password or OAuth
    },
  });

  // 2. Set up email options
  const mailOptions = {
    from: 'your-email@gmail.com',
    to: 'receiver@example.com',
    subject: 'Hello from Node!',
    text: 'This is a test email sent from Node.js using Nodemailer.',
  };

  // 3. Send the email
  try {
    const info = await transporter.sendMail(mailOptions);
    console.log('Email sent:', info.response);
  } catch (err) {
    console.error('Error sending email:', err);
  }
};

sendMail();
```

---

### 🛡️ Important Notes:

* Gmail requires **App Passwords** (if 2FA is enabled) or **OAuth2**.
* For production apps, you can use services like **SendGrid**, **Mailgun**, **Postmark**, or **SMTP providers** with Nodemailer.

---

### ✨ Features:

| Feature                                | Supported |
| -------------------------------------- | --------- |
| HTML emails                            | ✅         |
| Attachments                            | ✅         |
| Embedded images                        | ✅         |
| Templating (via tools like Handlebars) | ✅         |

---

### 📌 Summary:

* **nodemailer** = Node.js library for sending emails.
* Supports **SMTP**, **OAuth2**, attachments, HTML, templates, etc.
* Commonly used in **backend APIs** for notifications, verification, and more.

