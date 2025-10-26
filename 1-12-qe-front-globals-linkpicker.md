### `linkpicker`: Image URL Picker Utility

`linkpicker` is a global front-end utility function for Selecting an image or icon or upload it. It opens a floating window offering three methods of image selection / file upload or input the link manually.

1. Select from user's local files.
2. Choose from QE Icon library.
3. Enter a URL manually.

Returns:
- A **URL string** based on the selected method.
- `null` if the user cancels the selection.

---

### ✅ Example

```jsx
<b-200 class="btn btn-info" onClick={async () => {
  const url1 = await linkpicker(); // Without default
  const url2 = await linkpicker("https://cdn.qepal.com/qepal/10005664.png"); // With default input
}}>
  Pick an image?
</b-200>
```

---

### ⚙️ Function Signature

```ts
linkpicker(defaultValue?: string): Promise<string | null>
```

- **`defaultValue`** *(optional)*: Pre-filled value for the "Enter a link" field.

Use `linkpicker` in `async` functions with `await` to handle user input effectively.
