
# 🔐 `MD5`: Global Hash Utility

The `MD5` function is globally available in the QE Javascript environment (`microservice` and `xwebsite`) backend and `nodejs-worker`. It computes an MD5 cryptographic hash from a given input string and returns it as a hexadecimal string.

This is especially useful for comparing large strings efficiently—by comparing their hashes instead of the full text.

---

```jsx
function MD5(input: string | Buffer): string
```

## ✅ Basic Usage

```jsx
console.log(MD5("Welcome dear user!"));

```

---

## 📘 Notes

- **Input:** A plain JavaScript string.
- **Output:** A 32-character hexadecimal MD5 hash.
- **Use Case:** Lightweight string comparison, cache keys, content integrity validation, etc.
- **Security Warning:** MD5 is not secure for cryptographic purposes. Use it for utility-level operations only (e.g., non-sensitive hashing).
