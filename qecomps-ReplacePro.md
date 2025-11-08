
# `ReplacePro` Utility

The `ReplacePro` function allows for dynamic insertion of React components (e.g., buttons, images, or other JSX elements) into a string by replacing specific placeholder tokens. This is particularly useful when you want to embed components inline with text content.

## Function Signature

```ts
ReplacePro(
  text: string,             // The original text
  target: string,           // The placeholder string to be replaced
  replacement: ReactNode    // The JSX element to insert in place of the placeholder
): ReactNode
```

## Basic Example

In the following example, we replace every occurrence of the keyword `"IMAGE"` in the input text with an `<img>` component:

```tsx
export default p => Component(p, Page);

const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {
  return (
    <div style={{ direction: z.lang.dir, padding: 10 }}>
      {ReplacePro(
        "این تصویر IMAGE مربوط به کلوز IMAGE  است",
        "IMAGE",
        <img
          src="https://cdn.qepal.com/qepal/emoji/❤.png"
          style={{ width: 15, marginLeft: 5, marginRight: 5 }}
        />
      )}
    </div>
  );
};
```

> ✅ *Recommendation:* When inserting circular or square images inline with text, it is common to use a style like `width: 15px; margin-left: 5px; margin-right: 5px` for optimal spacing.

---

## Nested Replacement Example

You can also chain multiple `ReplacePro` calls to handle different placeholders in sequence. Here's an example where we first replace `"IMAGE"` with one emoji and then replace `"KEY2"` with another:

```tsx
export default p => Component(p, Page);

const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {
  const firstChange = ReplacePro(
    "این تصویر IMAGE مربوط به کلوز IMAGE KEY2  است",
    "IMAGE",
    <img
      src="https://cdn.qepal.com/qepal/emoji/❤.png"
      style={{ width: 15, marginLeft: 5, marginRight: 5 }}
    />
  );

  const final = ReplacePro(
    firstChange,
    "KEY2",
    <img
      src="https://cdn.qepal.com/qepal/emoji/🌎.png"
      style={{ width: 15, marginLeft: 5, marginRight: 5 }}
    />
  );

  return (
    <div style={{ direction: z.lang.dir, padding: 10 }}>
      <b-200 style={{ backgroundColor: "#748EC5", fontSize: 12 }}>
        {final}
      </b-200>
    </div>
  );
};
```

In this example:
- All instances of `"IMAGE"` are replaced by the ❤️ emoji (`❤.png`)
- The placeholder `"KEY2"` is replaced by the 🌍 emoji (`🌎.png`)

This pattern is useful for composing rich content dynamically with fine-grained control over placement and styling.

---

Let me know if you'd like this file saved with a `.md` extension or integrated into documentation structure.
