**`EnDigits` Function Documentation**

The `EnDigits` function is a utility used to convert Persian numerals (e.g., `۰۱۲۳۴۵۶۷۸۹`) into standard English numerals (`0123456789`). This is crucial for handling user input in multilingual platforms like QE, where Persian users may accidentally enter numbers using Persian characters—especially during authentication processes like registration or login.

---

### ✅ Purpose

To normalize numeric inputs by converting any Persian digits into their English equivalents.

---

### 📦 Import

```ts
import { EnDigits } from '@/frontend/components/qecomps/FaDigits';
```

---

### 🧠 Behavior

* Accepts a `string` input.
* Scans the string and replaces all Persian digits with the corresponding English digits.
* Returns a cleaned string with only English numerals.

---

### 📌 Use Cases

* Phone number input normalization.
* Validation of numeric fields.
* Ensuring consistent formatting for backend processing or comparison.

---

### 🚀 Example Usage

```jsx
// front-end function:
export default p => Component(p, Page);

const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {
  onLoad(async () => {
    let test = "۱۲۳۴۵"; // Persian digits for 12345
    props.test = EnDigits(test);
    refresh();
  });

  return <div style={{ direction: z.lang.dir, padding: 10 }}>
    {props.test} {/* Output: 12345 */}
  </div>
}
```

---

### 🔁 Related Functions

* `FaDigits`: Converts English numerals to Persian digits.
* `.toLocaleString(z.lang.region)`: Localized numeric display based on user language.

---

### 🌐 Multilingual Consideration

On QE, it’s recommended to sanitize numeric inputs using `EnDigits` before comparison or submission to the backend, especially when targeting Persian-speaking users. Persian keyboards may default to Persian numerals, leading to inconsistencies in validation unless explicitly handled.

---

### 🛡️ Best Practice

Always use `EnDigits` on any user input field expecting numeric values when multilingual support (especially Persian) is in place.

---

### 🧪 Output Example

**Input:** `"۰۱۲۳۴۵۶۷۸۹"`
**Output:** `"0123456789"`

---
