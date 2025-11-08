### `signout`: Enduser Sign-Out Utility (XWebsite Only)

The `signout` function is a global front-end utility available **only within `XWebsite` blocks**. It logs out the current `enduser` session.

---

```jsx
await signout();
```


### ✅ Example Usage

```jsx
<b-200 class="btn btn-info" onClick={async () => {
  await signout();
}}>
  Signout enduser
</b-200>
```

This button, when clicked, will trigger the `signout` process and log the current enduser out of the session.
