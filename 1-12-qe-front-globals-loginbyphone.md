### `loginbyphone`: Iranian Phone-Based Enduser Authentication (xwebsite Only)

`loginbyphone` is a global front-end utility available only within `xwebsite` blocks. It opens a floating window that allows end-users to log in or sign up using an Iranian mobile phone number.

---

### 🌐 Availability

- **Scope**: `xwebsite` environment only  
- **Language**: Persian  
- **Phone Support**: Iranian mobile numbers only

---

```jsx
 await loginbyphone();
```

### ✅ Example

```jsx
<b-200 class="btn btn-info" onClick={async () => {
  await loginbyphone();
}}>
  Login using Iranian phone
</b-200>
```

Use this utility to enable localized login flows for Iranian users in Persian-language `xwebsite` applications.
