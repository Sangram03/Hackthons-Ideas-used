### 🔧 Vercel Backend Configuration (`vercel.json`)

This project uses **Vercel** to deploy the backend Node.js server. The configuration for deployment is specified in the `vercel.json` file.

```json
{
  "version": 2,
  "builds": [
    {
      "src": "server.js",
      "use": "@vercel/node",
      "config": {
        "includeFiles": [
          "dist/**"
        ]
      }
    }
  ],
  "routes": [
    {
      "src": "/(.*)",
      "dest": "server.js"
    }
  ]
}
```

#### 📝 Explanation:

* **version: 2**
  Specifies the version of the Vercel platform being used. Version 2 is required for custom builds and routing.

* **builds:**
  Defines how Vercel should build the backend.

  * `"src": "server.js"` — Entry point for your backend.
  * `"use": "@vercel/node"` — Tells Vercel to treat it as a Node.js serverless function.
  * `"includeFiles": ["dist/**"]` — Ensures all files from the `dist` directory (e.g., compiled frontend or assets) are included in the deployment.

* **routes:**
  Defines custom routing behavior.

  * `"src": "/(.*)"` — Catches all incoming requests.
  * `"dest": "server.js"` — Directs them to `server.js` for handling (e.g., Express app or custom server logic).

---

