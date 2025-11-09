### `loginbyGitHub`: QE-Integrated GitHub OAuth Authentication (XWebsite Only)

`loginbyGitHub` is a global front-end function available exclusively in the `XWebsite` environment. It enables `enduser` login using either QE credentials (if already authenticated) or [GitHub](https://github.com) OAuth as a fallback.

---

### 🌐 Availability

- **Scope**: `XWebsite` only  
- **Primary Authentication**: QE login  
- **Fallback Authentication**: GitHub OAuth (via QE-hosted window)  
- **User Perspective**: GitHub sees the authentication request as coming from QE.

---

```jsx
await loginbyGitHub();
```

### ✅ Example

```jsx
<b-200 class="btn btn-info" onClick={async () => {
  await loginbyGitHub();
}}>
  Login using QE or GitHub
</b-200>
```

Use `loginbyGitHub` in your `XWebsite` blocks to support seamless login with fallback to GitHub if the user is not already logged into QE.
