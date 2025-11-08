# Activating REST API on `nodejs-worker`

In `nodejs-worker`, the `App.Init(...)` method controls whether the REST API is enabled. By default, passing `false` disables the API, but you can enable it by using either of the following two methods:

---

## 🔧 Method 1: Pass `true`

```ts
await App.Init(true);
```

- Enables the REST API and binds it to **port 3000**.
- Suitable for standard local development.

---

## 🔧 Method 2: Pass a Custom Port

```ts
await App.Init(8000); // Example port number
```

- Enables the REST API and sets the server to listen on port `8000` (or any port from `2000` to `20000`).
- Ideal for avoiding port conflicts or when running multiple workers.

---

## 🔒 Method 3: Pass `false`

```ts
await App.Init(false);
```

- Disables the REST API.
- Best used for Nexus-only or isolated systems.


---

## ✅ Enabling REST API on Port 8000

```ts
import { App } from './libs/bridge';
(async () => {
    console.clear()
    await App.Init(8000);
    await App.initUDB();

    await App.Connect({
        resource: process.env.RESOURCE || "default",
        image: "/files/app/robot.webp",
    })

    App.rest.get('/', (req, res) => {
        res.json({ code: 0 });
    });

    console.log("[nexus] connected.")

    App.on("ping", async (specs) => {
        console.log("ping request from:", specs.uid)
        return { code: 0, pong: true }
    })
})();
```

---

## 📮 Handling POST Requests

```ts
App.rest.post('/', (req, res) => {
    res.json({ code: 0 });
});
```

---

## 🌐 Deployment Note

When published, workers are placed behind a CDN and served via HTTPS (port 443). For example, if your worker’s URL is:

```
https://published-worker-example.qepal.com
```

Then this code will handle a GET request to that endpoint:

```ts
App.rest.get('/', (req, res) => {
    res.json({ code: 0 });
});
```

---

## 🧰 Sending Requests with QE `api` Function

From any QE block (e.g. another `nodejs-worker`), you can call the REST API with:

```ts
let res = await api("https://published-worker-example.qepal.com")
console.log(res)
```