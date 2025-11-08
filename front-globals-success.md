### `success`: Global Toast Notification for Successful Operations

`success` is a global front-end function used to display a green toast message indicating a successful operation. The message remains visible for approximately 3 seconds.

---

```jsx
success(text: string);
```

### ✅ Example

```jsx
<b-200 class="btn btn-success" onClick={async () =>{
  success("Operation was successful");
}}>
  Success button
</b-200>
```

---

Use this function to provide quick, positive feedback to users after completing successful actions.
