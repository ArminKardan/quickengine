
# `TextEndAbbreviation` Utility

The `TextEndAbbreviation` is a utility function designed to truncate a given string to a specified maximum length by abbreviating the end of the string and appending an ellipsis (`...`). This is particularly useful when displaying text content within limited horizontal space without losing the contextual beginning of the string.

### Import Path

```ts
import TextEndAbbreviation from '@/frontend/components/qecomps/TextEndAbbreviation';
```

---

## Usage

### Basic Example

The following example demonstrates how to shorten a long string to a maximum length of 12 characters. The resulting string will preserve the beginning and truncate the end, replacing the cut-off part with an ellipsis:

```jsx
export default p => Component(p, Page);
const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {
  return <div style={{ direction: z.lang.dir, padding: 10 }}>
    {TextEndAbbreviation("example of a long text", 12)}
  </div>
}
```

**Output:**
```
example o...
```

---

## Parameters

| Parameter | Type     | Description                                |
|-----------|----------|--------------------------------------------|
| `text`    | `string` | The original string to abbreviate.         |
| `maxLen`  | `number` | Maximum number of characters to preserve, including ellipsis. |

---

## Notes

- If the length of `text` is already less than or equal to `maxLen`, the function returns the original text without modification.
- The function ensures that the returned string never exceeds the `maxLen` constraint, including the length of the appended ellipsis (`...`).
- This utility is typically used in UI components like `<Text>` when paired with the `abbreviatend` prop for consistent visual formatting.
