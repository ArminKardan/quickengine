### `sleep`: Delay Utility for Async Functions

`sleep` is a cross-environment utility (available everywhere in QE that is javascript based (nodejs and browser)) that creates a delay in `async` functions. It accepts a time duration in milliseconds and returns a `Promise<void>` that resolves after the delay.

---

```jsx
 await sleep(1000);
```

### ✅ Example

```jsx
  console.log("TASK1");
  await sleep(1000); // Waits for 1 second
  console.log("TASK2");
```

Use `sleep(ms)` when you need to pause between asynchronous operations.
