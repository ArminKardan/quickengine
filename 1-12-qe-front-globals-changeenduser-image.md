### `changeenduser.image`: Change Logged-In User's Image Globally

This function is available only in `XWebsite` blocks. It updates the `image` field of the currently logged-in `enduser` across the entire QE ecosystem, including the QE website and all `XWebsite` instances.

---

### ✅ Example Usage

```jsx
<b-200 class="btn btn-info" onClick={async () => {
  if (z.enduser) {
    let newimage = "https://cdn.qepal.com/qepal/1006195.png";
    let json = await changeenduser.image(newimage);
    if (json.code === 0) {
      alerter("Image is changed to " + newimage);
    } else {
      log({ text: "An error occurred while changing image", type: "error" });
      log({ text: JSON.stringify(json), type: "warning" });
    }
  } else {
    alerter("You are not logged in.");
  }
}}>
  Change `enduser`'s image in all QE space
</b-200>
```

---

### 📝 Notes

- Available only in `XWebsite` blocks.
- Requires the user to be logged in (`z.enduser` must be truthy).
- The `image` value must be a valid image URL.
- On success, `json.code === 0`; handle other responses with `log()` and `alerter()` for proper user feedback.

