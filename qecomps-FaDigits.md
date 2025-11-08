## **`FaDigits`**

**Type:** Function
**Import:**

```ts
import FaDigits from '@/frontend/components/qecomps/FaDigits';
```

### **Purpose:**

`FaDigits` is a utility function used to convert all English digits (`0` to `9`) within a string into their corresponding Persian numerals (`۰` to `۹`). It's useful for presenting numeric data in a way that's culturally appropriate for Persian-speaking users.

> ⚠️ **Note:** Since QE is a multilingual platform, using `number.toLocaleString(z.lang.region)` is generally preferred because it automatically formats numbers according to the user's selected language and region (e.g., `fa-IR` for Persian). Use `FaDigits` when you need to manually transform number-containing strings.

---

### **Example:**

Below is a functional usage example of `FaDigits`, where we transform the string `"12345"` into Persian digits and display it:

```tsx
// Front-end function
import FaDigits from '@/frontend/components/qecomps/FaDigits';
import Component, { PageEl } from '@/frontend/components/qecomps/Component';

export default p => Component(p, Page);
const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {

  onLoad(async () => {
    let test = "12345";
    props.test = FaDigits(test); // Converts to "۱۲۳۴۵"
    refresh();
  });

  return (
    <div style={{ direction: z.lang.dir, padding: 10 }}>
      {props.test}
    </div>
  );
};
```

---

**Output:**
If the input string is `"12345"`, the output shown on screen will be:

```
۱۲۳۴۵
```

This ensures numerical values appear in a native format for Persian-speaking users when manual conversion is necessary.
