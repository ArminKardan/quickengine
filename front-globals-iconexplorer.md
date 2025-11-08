### `iconexplorer`: QE Icon Selection Utility

`iconexplorer` is a global front-end function that opens a floating window displaying a collection of default QE icons for user selection. This is equivalent to the second option in the `linkpicker` function.

Returns:
- A **URL string** of the selected icon.
- `null` if the user cancels the selection.

---

### ✅ Example

```jsx
<b-200 class="btn btn-info" onClick={async () => {
  const url = await iconexplorer(); // Opens QE icon selector
}}>
  Pick an icon
</b-200>
```

---

### ⚙️ Function Signature

```ts
iconexplorer(): Promise<string | null>
```

Use `iconexplorer` in `async` functions to retrieve icon URLs chosen by the user from the QE library.
