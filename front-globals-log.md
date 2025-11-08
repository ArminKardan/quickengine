### `log`: Global Logging Utility for UI Feedback

`log` is a front-end global function used to display sequential process messages to the user. It's helpful for showing multi-step progress, success, failure, and warning messages in a user-friendly format.

---

### ✅ Example: Displaying Process Logs

```jsx
<b-200 class="btn btn-info" onClick={async () => {
  log({ text: "Starting Process 1." }); // Info (default, blue)
  await sleep(1000);

  log({ text: "Process 1 is completed.", type: "ok" }); // Success (green)
  await sleep(2000);

  log({ text: "Starting Process 2." }); // Info (default, blue)
  await sleep(1000);

  log({ text: "Process 2 failed.", type: "error" }); // Error (red)
  const errDetail = { code: -10, msg: "No such path found" };
  log({ text: JSON.stringify(errDetail), type: "warning" }); // Warning (yellow)
}}>
  Start process
</b-200>
```

---

### ⚙️ Log Entry Options

```ts
log({
  text: string,               // Required message to show
  type?: "ok" | "error" | "warning" // Optional message type
})
```

- **`type: "ok"`** — success (green)
- **`type: "error"`** — failure (red)
- **`type: "warning"`** — additional information or details (yellow)
- **default** — info (blue)

Use `JSON.stringify()` for logging objects when needed.
