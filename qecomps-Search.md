
# `Search` Component

The `Search` component is a reusable **Next.js UI element** designed for interactive text-based search. It provides a minimal and intuitive interface for capturing user queries.

## Example

```tsx
export default p => Component(p, Page);

const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {
  return (
    <div style={{ direction: z.lang.dir, padding: 10 }}>
      <Search
        title="Searching among products"
        defaultValue={props.search}
        on={(txt) => {
          props.search = txt;
          refresh();
          alerter("جست و جو به دنبال:" + txt);
        }}
        onclose={() => {
          refresh({ search: "" });
        }}
      />
    </div>
  );
};
```

## Props

- **`title`**: `string`  
  A label or heading displayed above the search box.

- **`defaultValue`**: `string`  
  Pre-filled text value (e.g., from props or external state).

- **`on`**: `(text: string) => void`  
  Callback triggered when the user confirms a search by clicking the **arrow button** or pressing **Enter**.

- **`onclose`**: `() => void`  
  Callback triggered when the user clicks the **X** icon to clear the input.

---

# `SerialGenerator` Utility

The `SerialGenerator` function is used to generate alphanumeric codes, suitable for use as secrets, string-based IDs, and more. It ensures consistent format across all environments (frontend, backend, Node.js workers, and Python services).

## Usage (JavaScript/TypeScript)

To use this utility in a JavaScript/TypeScript project:

```ts
import SerialGenerator from '@/frontend/components/qecomps/SerialGenerator';
```

The function signature is:

```ts
SerialGenerator(length: number): string
```

## Usage Example

```tsx
export default p => Component(p, Page);

const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {
  return (
    <div style={{ direction: z.lang.dir, padding: 10 }}>
      {SerialGenerator(10)}
    </div>
  );
};
```

This call will render a random 10-character alphanumeric serial.

---

## Usage (Python Workers)

In Python-based workers:

```python
from libs.bridge import serial_generator

serial = serial_generator(12)  # Generates a 12-character serial
```

> ✅ `SerialGenerator` is also globally available in Node.js workers without the need for import.

---

Let me know if you'd like these two component docs added to a shared documentation set.
