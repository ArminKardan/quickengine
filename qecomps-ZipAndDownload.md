
# `ZipAndDownload` – QE Front-End Utility

## Overview

**`ZipAndDownload`** is a front-end utility function in the QE system used for generating and downloading ZIP files dynamically in the browser. It can be used to package any text content into a `.zip` archive, containing a file with the specified name and content.

---

## Import Path

```js
import ZipAndDownload from '@/frontend/components/qecomps/ZipAndDownload';
```

---

## Function Signature

```ts
ZipAndDownload(content: string, fileName: string, zipName: string): void
```

- **`content`** *(string)*: The string content that will be written inside the file.
- **`fileName`** *(string)*: The name of the file inside the zip archive (should include extension, e.g., `example.txt`).
- **`zipName`** *(string)*: The name of the generated zip file (without `.zip` extension).

---

## Example: Basic Usage in a QE Front-End Page

In this example, a `Window` component contains a button labeled **Download**. When the button is clicked, the current time (in ISO format) is captured, and a ZIP file named `time.zip` containing `time.txt` with the timestamp content is generated and downloaded.

```jsx
export default p => Component(p, Page);
const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {
  return <div style={{ direction: z.lang.dir, padding: 10 }}>
    <Window title='Items' contentStyle={{ padding: 10 }}>
      <b-200 class="btn btn-info" onClick={() => {
        ZipAndDownload(new Date().toISOString(), "time.txt", "time")
      }}>
        Download
      </b-200>
    </Window>
  </div>
}
```

---

## Behavior

- When the user clicks the button:
  1. `new Date().toISOString()` gets the current time as a string.
  2. `ZipAndDownload(...)` wraps this string in a `.txt` file.
  3. A ZIP file is generated on the fly with that `.txt` inside.
  4. The ZIP is downloaded automatically to the user’s system.

---

## Notes

- This function runs entirely on the client-side (in the browser).
- It does not require any backend support or server API.
- File creation and download happen immediately after the function call.

---

## Use Cases

- Exporting logs or snapshots of data.
- Downloading content created dynamically by the user.
- Offering file bundles in controlled formats.
