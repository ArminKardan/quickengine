### `error`: Global Toast Notification for Error Messages

`error` is a global front-end function used to display a toast indicating a failed operation. The toast appears with a maroon background and white text, and remains visible for approximately 3 seconds.

---

### ✅ Example

```jsx
export default p => Component(p, Page);
const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {
  return (
    <div style={{ direction: z.lang.dir, padding: 10 }}>
      <Window title="Global functions" contentStyle={{ padding: 10 }}>
        <b-200 class="btn btn-error" onClick={async () => {
          error("Operation failed");
        }}>
          Fail button
        </b-200>
      </Window>
    </div>
  );
};
```

---

Use this function to quickly notify users of errors or failed operations in the UI.
