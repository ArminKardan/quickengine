# `Img` Component

The `Img` component is a custom image rendering utility developed specifically for QE projects. It is designed to address SEO and performance issues commonly encountered when using HTML `img` tags for icons and small images.

---

## 🔍 Motivation

In QE applications, many images are used purely for UI decoration (e.g., icons). Adding `alt` attributes for each can clutter the HTML and negatively impact SEO when overused or misused. The `Img` component solves this by replacing standard `<img>` tags with a more controlled rendering method.

---

## 📦 Import

```ts
import Img from '@/frontend/components/qecomps/Img';
```

---

## 🧱 Component Behavior

- `Img` renders the image as a CSS `background-image` inside an `f-cc` container.
- It reduces the HTML footprint by avoiding excessive use of `alt` attributes on non-critical icons.
- Use `Img` for decorative or less important UI elements.
- Use standard `<img>` for content-critical images (e.g., posters, SEO-relevant visuals).

> ⚠️ **Note:** `height` and `width` must be explicitly defined when using `Img`.

---

## ✨ Example: Basic Usage

```tsx
export default p => Component(p, Page);

const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {
  return (
    <div style={{ direction: z.lang.dir, padding: 10 }}>
      <Img src="/example.png" style={{ height: 50, width: 50 }} />
    </div>
  );
};
```

---

## 📝 Summary

| Prop   | Type     | Description                          |
|--------|----------|--------------------------------------|
| `src`  | `string` | The path to the image file           |
| `style`| `object` | Must include `height` and `width`    |

Use `Img` to maintain a lightweight and clean HTML structure while ensuring flexibility and design consistency across QE frontends.
