
### 📄 `props` and Lifecycle Functions in QE Frontend

In QE-based frontend development (used in `microservice` and `xwebsite`), the `Page` function receives several parameters that help manage component state, lifecycle, and rendering behavior:

```tsx
const Page: PageEl = (
  props,
  refresh,
  getProps,
  onLoad,
  onConnected,
  dies,
  isFront,
  z
) => { /* ... */ }
```

These parameters are explained in detail below:

---

### `props` (Frontend)

- `props` is a **mutable JavaScript object** used to store backend-supplied data via the `Prosper` function.
- It also acts as the component’s state during rendering and can persist values across refreshes.

Example:

```tsx
props.sayhi = "hello"; // Persisted across refreshes
```

---

### `refresh`

The `refresh` function re-renders the component. It behaves similarly to `setState` in frameworks like Next.js, with `props` acting as the state object.

#### Usage Example (Direct Mutation):

```tsx
<button onClick={() => {
  props.sayhi = "hi";
  refresh();
}}>
  mybtn
</button>
```

#### Usage Example (Object Update):

```tsx
<button onClick={() => {
  refresh({ sayhi: "hi" });
}}>
  mybtn
</button>
```

---

### `getProps`

This function is executed **before** the initial render. It’s ideal for asynchronous setup, such as fetching data or initializing `props`.

#### Example:

```tsx
getProps(async (isFront) => {
  const json = await api("https://example.com/api/test");
  props.sayhi = json.sayhi;
});
```

> ℹ️ `isFront` indicates whether the rendering is happening on the client (i.e., `typeof window !== "undefined"` in Next.js terms).

---

### `onLoad`

Called after the component has fully loaded. It's equivalent to `useEffect(() => {}, [])` in React/Next.js, but accepts an `async` function.

#### Example:

```tsx
onLoad(async () => {
  props.sayhi = "hi";
  refresh();
});
```

> Useful for initializing dynamic or interactive behavior after page load.

---

### `onConnected`

This function triggers once the `nexus` connection is established. It’s essential for making `nexus` API calls from the frontend.

#### Example:

```tsx
onConnected(async () => {
  const r = await nexus.api({ app: "etest", cmd: "ping" });
  refresh({ sayhi: r.sayhi });
});
```

> Used when interacting with real-time or backend-connected services in the frontend.

---

### `dies`

This lifecycle function is triggered when the component is about to be unmounted (similar to the return cleanup in `useEffect`).

#### Example:

```tsx
onLoad(async () => {
  if (!props.counter) props.counter = 0;
  props.c = setInterval(() => {
    props.counter++;
    refresh();
  }, 1000);
});

dies(async () => {
  clearInterval(props.c);
});
```

> Useful for clearing intervals, timeouts, listeners, or other long-running side effects when the component is removed.
