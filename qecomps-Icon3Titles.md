# `Icon3Titles` Component

`Icon3Titles` is a key UI component used in QE's Next.js frontend. It is typically used as an item in a list, featuring an image with rounded corners on the left and three lines of titles/descriptions beside it.

**Import Path:**
```ts
import Icon3Titles from '@/frontend/components/qecomps/Icon3Titles';
```

---

## 🧩 Basic Usage

### Example 1: Basic `Icon3Titles` Rendering

```tsx
export default p => Component(p, Page);

const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {
  return (
    <div style={{ direction: z.lang.dir, padding: 10 }}>
      <Icon3Titles
        title1="Primary title"
        title2="Secondary title"
        title3="Tertiary title"
        image="/example.png"
      />
    </div>
  );
};
```

---

## ⚡ Click Event Handling

Like `Icon2Titles`, `Icon3Titles` supports an `on` attribute that handles click events.

### Example 2: Using `on` Attribute

```tsx
export default p => Component(p, Page);

const Page: PageEl = (...) => {
  return (
    <div style={{ direction: z.lang.dir, padding: 10 }}>
      <Icon3Titles
        title1="Primary title"
        title2="Secondary title"
        title3="Tertiary title"
        image="/example.png"
        on={async () => { console.log("clicked!") }}
      />
    </div>
  );
};
```

---

## ⚙️ Adding Right-Side Icon

`Icon3Titles` allows appending an icon to the right side using the `righticon` prop. You can attach event handlers to it separately from the main item.

### Example 3: Right Icon With `img` Tag

```tsx
export default p => Component(p, Page);

const Page: PageEl = (...) => {
  return (
    <div style={{ direction: z.lang.dir, padding: 10 }}>
      <Icon3Titles
        title1="Primary title"
        title2="Secondary title"
        title3="Tertiary title"
        image="/example.png"
        righticon={
          <img
            src="https://cdn.qepal.com/qepal/gear.svg"
            style={{ height: 38, width: 38 }}
            onClick={async (e) => {
              e.stopPropagation();
              console.log("item options clicked!");
            }}
          />
        }
        on={async () => { console.log("clicked!") }}
      />
    </div>
  );
};
```

> **Note:** `e.stopPropagation()` is used to prevent the `on` handler from firing when the `righticon` is clicked.

---

### Example 4: Right Icon With Material Icon

```tsx
import SettingsIcon from '@mui/icons-material/Settings';

export default p => Component(p, Page);

const Page: PageEl = (...) => {
  return (
    <div style={{ direction: z.lang.dir, padding: 10 }}>
      <Icon3Titles
        title1="Primary title"
        title2="Secondary title"
        title3="Tertiary title"
        image="/example.png"
        righticon={
          <SettingsIcon
            onClick={async (e) => {
              e.stopPropagation();
              console.log("wow");
            }}
            style={{ width: 38, height: 38, opacity: 0.6 }}
          />
        }
        on={async () => { console.log("hi") }}
      />
    </div>
  );
};
```

---

## 🔵 Rounded Icon

Use the `roundicon` attribute to render the main image as a circle.

### Example 5: Circular Image

```tsx
export default p => Component(p, Page);

const Page: PageEl = (...) => {
  return (
    <div style={{ direction: z.lang.dir, padding: 10 }}>
      <Icon3Titles
        title1="Primary title"
        title2="Secondary title"
        title3="Tertiary title"
        image="/example.png"
        roundicon
      />
    </div>
  );
};
```

---

## ✴️ Special Badge Below Image

You can display a special badge below the main image using the `special` prop. Style it with `specialcolor` and `specialtextcolor`.

### Example 6: Special Text with Styling

```tsx
export default p => Component(p, Page);

const Page: PageEl = (...) => {
  return (
    <div style={{ direction: z.lang.dir, padding: 10 }}>
      <Icon3Titles
        title1="Primary title"
        title2="Secondary title"
        title3="Tertiary title"
        image="/example.png"
        special="wow"
        specialcolor="yellow"
        specialtextcolor="black"
      />
    </div>
  );
};
```

---

## 🔤 Typography Customization

By default:
- `title1`: bold, font-size: 14px
- `title2`: font-size: 12px
- `title3`: font-size: 11px

Use the `nobold` attribute to disable bold styling on `title1`.

### Example 7: Disable Bold Title

```tsx
export default p => Component(p, Page);

const Page: PageEl = (...) => {
  return (
    <div style={{ direction: z.lang.dir, padding: 10 }}>
      <Icon3Titles
        title1="Primary title"
        title2="Secondary title"
        title3="Tertiary title"
        image="/example.png"
        nobold
      />
    </div>
  );
};
```

---

## 🧱 Custom Element Injection

All `title1`, `title2`, `title3`, and `image` props accept React elements for rich customization.

### Example 8: Custom Elements in Titles and Image

```tsx
import FaceRetouchingNaturalIcon from '@mui/icons-material/FaceRetouchingNatural';

export default p => Component(p, Page);

const Page: PageEl = (...) => {
  return (
    <div style={{ direction: z.lang.dir, padding: 10 }}>
      <Icon3Titles
        title1={<f-13 style={{ color: "blue" }}>Primary title</f-13>}
        title2={
          <f-13 style={{ color: "pink", backgroundColor: "black" }}>
            <i>Secondary title</i>
          </f-13>
        }
        title3={<f-10>Tertiary title</f-10>}
        image={<FaceRetouchingNaturalIcon style={{ fontSize: 50 }} />}
      />
    </div>
  );
};
```

> In this example, we use Material Icons and custom styles for a fully personalized UI.

---

## 📝 Summary

| Prop              | Type              | Description                                          |
|-------------------|-------------------|------------------------------------------------------|
| `title1`          | `string \| JSX`   | Primary title (bold by default)                     |
| `title2`          | `string \| JSX`   | Secondary title                                     |
| `title3`          | `string \| JSX`   | Tertiary title                                      |
| `image`           | `string \| JSX`   | Image or icon to display on the left                |
| `righticon`       | `JSX.Element`     | Optional icon on the right                          |
| `roundicon`       | `boolean`         | Make the image circular                             |
| `on`              | `() => Promise`   | Click handler for the whole component               |
| `special`         | `string`          | Text shown under the main image                     |
| `specialcolor`    | `string`          | Background color of special text                    |
| `specialtextcolor`| `string`          | Text color of special text                          |
| `nobold`          | `boolean`         | Disables bold styling on `title1`                   |
