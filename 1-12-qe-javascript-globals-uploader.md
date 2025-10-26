### `uploader`: File Upload Utility

`uploader` is a global javascript function available in all server and browser and nodejs worker. used to prompt users to **upload a file from scratch** (not just select). It opens a floating window for file uploading.

---

### ✅ Return Value

- Returns a **string URL** of the uploaded file if successful.
- Returns `null` if the user cancels the operation.

---

### ⚙️ Function Signature

```ts
uploader(options: {
  title: string,
  text: string,
  max_age_sec?: number,
  maxmb?: number
}): Promise<string | null>
```


### 🛠️ Arguments

It accepts a **JavaScript object** with the following fields:

| Key           | Type     | Required | Description |
|---------------|----------|----------|-------------|
| `title`       | `string` | ✅        | Title of the upload window. |
| `text`        | `string` | ✅        | Instructional message for the user. |
| `max_age_sec` | `number` | ❌        | File lifetime on the server in seconds. `0` or unset means unlimited. |
| `maxmb`       | `number` | ❌        | Maximum file size in MB. Default is 60MB. |

---

### 💡 Example

```jsx
  const url = await uploader({
    title: "Upload Title",
    text: "Please upload your image",
    max_age_sec: 0,
    maxmb: 100
  });
```

---

