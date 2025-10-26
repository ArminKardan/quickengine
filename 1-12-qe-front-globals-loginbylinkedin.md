### `loginbyLinkedIn`: QE-Integrated LinkedIn OAuth Authentication (xwebsite Only)

`loginbyLinkedIn` is a global front-end function available exclusively in the `xwebsite` environment. It enables `enduser` login using either QE credentials (if the user is already authenticated) or [LinkedIn](https://linkedin.com) OAuth as a fallback.

---

### 🌐 Availability

- **Scope**: `xwebsite` only  
- **Primary Authentication**: QE login  
- **Fallback Authentication**: LinkedIn OAuth (via QE-hosted window)  
- **User Perspective**: LinkedIn sees the authentication request as coming from QE.

---

```jsx
await loginbyLinkedIn();
```

### ✅ Example

```jsx
<b-200 class="btn btn-info" onClick={async () => {
  await loginbyLinkedIn();
}}>
  Login using QE or LinkedIn
</b-200>
```

Use `loginbyLinkedIn` in your `xwebsite` blocks to offer seamless authentication with fallback to LinkedIn if the user is not already logged into QE.
