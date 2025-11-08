
### 🔓 `decryptor(encrypted: string, password: string): Promise<string>`

Decrypts an encrypted base64 string using the same password. Returns the original string if the password is correct.

---

### ✅ Example

```jsx
let text = "hello";
let password = "turing";
let encrypted = await encryptor(text, password);
let original = await decryptor(encrypted, password);
alerter(original);
```

This example encrypts `"hello"` using `"turing"` as the password, and then decrypts it back to the original using `decryptor`, finally showing it with `alerter`.
