### `loginbyGoogle`: QE-Integrated Google OAuth Authentication (XWebsite Only)

`loginbyGoogle` is a global front-end function available in the `XWebsite` environment. It facilitates logging in an `enduser` using either QE credentials (if the user is already logged in via QE) or Google OAuth.

---

### 🌐 Availability

- **Scope**: `XWebsite` environment only  
- **Primary Mechanism**: QE login  
- **Fallback Mechanism**: Google OAuth (in a QE-hosted window)  
- **User Perception**: Google will see that the login request originates from QE, not `XWebsite`.

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

Use this function in `XWebsite` blocks to provide a seamless login experience using QE credentials or fallback to Google OAuth when needed.
