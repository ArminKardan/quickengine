### `loginbyQE`: QE Website-Based Enduser Authentication (xwebsite Only)

`loginbyQE` is a global front-end function in the `xwebsite` environment that allows `enduser` login via the QE platform. It opens a new QE-hosted authentication window and listens for the login response via `window.postMessage`.

---

### 🌐 Availability

- **Scope**: `xwebsite` environment only  
- **Authentication Source**: QE website  
- **Mechanism**: Opens a QE window, provides login options (if needed), and listens for a message-based response

---

```jsx
await loginbyQE();
```

### ✅ Example

```jsx
<b-200 class="btn btn-info" onClick={async () => {
  await loginbyQE();
}}>
  Login using QE
</b-200>
```

Use this function to integrate a centralized login experience via the QE platform in `xwebsite` blocks. If the user isn't already logged in, they will be prompted with available login methods.
