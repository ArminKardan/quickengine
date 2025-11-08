### `fileexplorer`: File Upload and Selection Utility

`fileexplorer` is a global front-end function used to upload or select files. It is functionally equivalent to the first option of `linkpicker`, offering more direct control for file handling.

Returns:
- A **URL string** of the uploaded/selected file.
- `null` if the user cancels the operation.

---

### 🔁 Upload Options

Users can choose one of three file persistence modes:

1. **Permanent** — File stays on the server indefinitely.
2. **One Day** — File auto-deletes after 24 hours.
3. **One Hour** — File auto-deletes after 1 hour.

Temporary uploads are ideal for large, transient data.

---

### ✅ Example

```jsx
<b-200 class="btn btn-info" onClick={async () => {
  const url = await fileexplorer(); // Opens file selection interface
}}>
  Pick an image?
</b-200>
```

---

### ⚙️ Function Signature

```ts
fileexplorer(): Promise<string | null>
```

Use `fileexplorer` in `async` functions and handle the returned URL or cancellation as needed.
