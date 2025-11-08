### `Copy` Function

The `Copy` function is a utility used to programmatically copy a string to the user's clipboard. It is typically used in UI interactions such as buttons or actions that involve text sharing or reuse.

---

### Import Statement

```ts
import Copy from '@/frontend/components/qecomps/Copy';
```

---

### Parameters

| Parameter | Type   | Description                          |
|-----------|--------|--------------------------------------|
| `text`    | string | Required. The text to be copied.     |

---

### Behavior

When `Copy` is invoked, the provided string is copied directly to the user's clipboard using the browser’s Clipboard API under the hood. It is best used in user-triggered events such as button clicks.

---

### Example

In the following example, a button styled with `btn btn-primary` from DaisyUI will copy the given text to the clipboard when clicked:

```tsx
// front-end function:
export default p => Component(p, Page);

const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {
  return (
    <div style={{ direction: z.lang.dir, padding: 10 }}>
      <b-200
        className="btn btn-primary"
        style={{ width: "100%", minWidth: "200px" }}
        onClick={() => {
          Copy("hi im the text that will copy to the users clipboard.");
        }}
      >
        Click to copy
      </b-200>
    </div>
  );
};
```

This ensures a smooth user experience for copying content, commonly used in forms, token displays, or code snippet sharing.

---