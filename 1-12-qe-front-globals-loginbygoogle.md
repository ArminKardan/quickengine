### `loginbyGoogle`: QE-Integrated Google OAuth Authentication (xwebsite Only)

`loginbyGoogle` is a global front-end function available in the `xwebsite` environment. It facilitates logging in an `enduser` using either QE credentials (if the user is already logged in via QE) or Google OAuth.

---

### 🌐 Availability

- **Scope**: `xwebsite` environment only  
- **Primary Mechanism**: QE login  
- **Fallback Mechanism**: Google OAuth (in a QE-hosted window)  
- **User Perception**: Google will see that the login request originates from QE, not `xwebsite`.

---

```jsx
await loginbyGoogle();
```


### ✅ Example

```jsx
<b-200 class="btn btn-info" onClick={async () => {
  await loginbyGoogle();
}}>
  Login using QE or Google
</b-200>
```

Use this function in `xwebsite` blocks to provide a seamless login experience using QE credentials or fallback to Google OAuth when needed.
