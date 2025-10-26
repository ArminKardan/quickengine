### `loginbyemail`: Global Email-Based Enduser Authentication (xwebsite Only)

`loginbyemail` is a global front-end utility available in the `xwebsite` environment. It enables end-users to log in or sign up using their email address. A verification code is sent to the user’s email, and upon entering the correct code, the login completes.

---

### 🌐 Availability

- **Scope**: `xwebsite` environment only  
- **Language/Region Restrictions**: None  
- **Verification**: Email-based code confirmation

---

```jsx
 await loginbyemail();
```

### ✅ Example

```jsx
 <b-200 class="btn btn-info" onClick={async () => {
   await loginbyemail();
 }}>
   Login using email
 </b-200>

```

Use this utility to enable international login flows using email in `xwebsite` blocks.
