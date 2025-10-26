# 🌐 `api`: Global Front-End and Back-End REST API Utility

The `api` function is a global utility available in both the front-end and back-end environments for making REST API requests. It supports both GET and POST methods (with JSON body).

> **Note:** `api` is designed for interactions where the server responds with JSON.

---

### ✅ Basic Example

```tsx
  let json = await api("https://example.com/api/test");
```

---

### ⚙️ Usage Modes

```ts
api(url: string, body?: object)
```

#### Mode 1: Single Argument (GET Request)

When only the `url` is provided, a GET request is sent.

#### Mode 2: Multiple Arguments (POST Request)

If both `url` and `body` are provided, a POST request with a JSON body is sent.

---

### 📦 Example

```jsx
let json1 = await api("https://example.com/api/test"); // GET request
let json2 = await api("https://example.com/api/test", {name: "armin"}); // POST request
```