
#### General APIs (GAPIs) in `XWebsite`

You can create backend APIs by duplicating `backend/API/ping.ts` and renaming it (e.g., `getservertime.ts`, `multiply.ts`). These APIs are accessible from frontend, backend, or externally (if published).

---

### 📘 Example 1: Get Server Time

**Backend API (`backend/API/getservertime.ts`):**
```ts
type T = Parameters<typeof F>[0]; type R = ReturnType<typeof F>
declare global { interface API { "getservertime": (T: T) => R } var API: API }

export default async function F(T: null, C: APISession) {
  return { code: 0, time: new Date().toISOString() }
}
```

**Frontend Usage:**
```jsx
let json = await API["getservertime"](null);
if (json.code === 0) alerter(json.time);
```

**Backend Usage (`getServerSideProps`):**
```ts
let json = await API["getservertime"](null);
if (json.code === 0) console.log(json.time);
```

---

### 🧮 Example 2: Multiply Two Numbers

**Backend API (`backend/API/multiply.ts`):**
```ts
type T = Parameters<typeof F>[0]; type R = ReturnType<typeof F>
declare global { interface API { "multiply": (T: T) => R } var API: API }

export default async function F(T: { num1: number, num2: number }, C: APISession) {
  if (typeof T.num1 !== "number") return { code: -10, msg: "num1 is not a number" };
  if (typeof T.num2 !== "number") return { code: -11, msg: "num2 is not a number" };
  return { code: 0, result: T.num1 * T.num2 };
}
```

**Frontend Usage:**
```jsx
let json = await API["multiply"]({ num1: 10, num2: 20 });
if (json.code === 0) alerter(json.result);
```

**Backend Usage:**
```ts
let json = await API["multiply"]({ num1: 10, num2: 20 });
if (json.code === 0) console.log(json.result);
```

---

### 🌐 Example 3: Accessing APIs Externally

Once a block is published, APIs become accessible via public URLs (e.g., `https://etest-utest-uservice.qepal.com/api/multiply`).

```ts
(async () => {
  const res = await fetch("https://etest-utest-uservice.qepal.com/api/multiply", {
    method: "POST",
    body: JSON.stringify({ num1: 10, num2: 6 })
  });
  const json = await res.json();
  if (json.code === 0) console.log(json.result);
  else console.error(json);
})();
```

> Note: The `Content-Type` header is optional for these APIs.

---

### 🧾 Example 4: Understanding the `C` Parameter

Each API receives a second argument `C: APISession`, which contains useful metadata:

```ts
export default async function F(T: { num1: number, num2: number }, C: APISession) {
  let { app, body, cat, enduser, expid, lang, middleuser, origin, req, res, topuser, userip } = C;
  return { code: 0 };
}
```

**Explanation of Fields:**
- `app`: App name.
- `body`: Request payload.
- `cat`: Explore category.
- `expid`: Explore ID.
- `lang`: User language (frontend only).
- `origin`: Browser origin.
- `userip`: IP address of the caller.
- `enduser`, `middleuser`, `topuser`: Available user levels depending on context.

