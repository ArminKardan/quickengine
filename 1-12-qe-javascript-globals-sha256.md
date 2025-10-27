
# 🔐 `SHA256`: Front-End Hash Utility

`SHA256` is a globally available function in the QE JavaScript environment (`Admin Panel` and `XWebsite`backend and Nodejs worker) that generates a secure SHA256 hash from a given string or buffer.

This function is useful for securely comparing passwords and other cryptographic purposes.

---

```jsx
function SHA256(input: string | Buffer): string
```

---

## ✅ Basic Usage

```jsx
  console.log(SHA256("Welcome user!"));
```

---

## 📘 Notes

- **Input:** A string or buffer.
- **Output:** A 64-character hexadecimal hash.
- **Use Case:** Password hashing, content integrity verification, and secure hashing comparisons.
- **Security Note:** SHA256 is secure for non-reversible hashing, but it should still be used carefully in security-sensitive applications, especially with salt for passwords.
