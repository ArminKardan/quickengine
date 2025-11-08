### `Bold` Component

The `Bold` component is used for rendering bold text in a reliable and visually consistent way across languages, especially for non-Latin scripts such as Persian or Arabic. Instead of relying on the CSS `font-weight` property—which may not render correctly in some scripts—the component applies a font that is inherently bold and selected based on the user's language setting in QE.

#### Why Use `Bold` Instead of `font-weight`?

- **Cross-language consistency**: Ensures bold text appears correctly in Eastern and complex scripts.
- **Automatic font selection**: The component dynamically chooses an appropriate bold font based on the user's selected language and locale.
- **Visual clarity**: Provides a uniform and robust styling experience across all supported languages.

#### Import Statement

```ts
import Bold from '@/frontend/components/qecomps/Bold';
```

---

### Example

This example demonstrates how to use the `Bold` component along with a custom font size:

```ts
import Bold from '@/frontend/components/qecomps/Bold';
import Component, { PageEl } from '@/frontend/components/qecomps/Component';

export default p => Component(p, Page);

const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {
  return (
    <div style={{ direction: z.lang.dir, padding: 10 }}>
      <Bold><f-12>I'm a bold, with font-size:12px text!</f-12></Bold>
    </div>
  );
};
```

In this code:
- `<Bold>` wraps the content to ensure it is rendered using the correct bold font.
- `<f-12>` is assumed to be a custom tag or utility for applying a font size of 12px.

---

### Usage Note

Always use the `Bold` component for emphasizing text in QE applications instead of CSS `font-weight`, especially when targeting international users with diverse language scripts.