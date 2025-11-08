
# `Icon2Titles` Component (Next.js, QE)

`Icon2Titles` is a core UI component used frequently in list displays. It visually aligns a circular image on the left, followed by two lines of text (title and description) on the right. This component supports interaction, styling, and additional UI augmentations.

**Import Statement:**
```js
import Icon2Titles from '@/frontend/components/qecomps/Icon2Titles';
```

---

### 📌 Example 1: Basic Usage
A minimal example rendering `Icon2Titles` with two lines of text and an image.
```jsx
export default p => Component(p, Page);
const Page: PageEl = (...) => {
  return (
    <div style={{ direction: z.lang.dir, padding: 10 }}>
      <Icon2Titles
        title1={"Primary title"}
        title2={"Secondary title"}
        image={"/example.png"}
      />
    </div>
  );
};
```

---

### 📌 Example 2: Click Handling (`on` Prop)
Triggers a function when the item is clicked.
```jsx
<Icon2Titles
  title1={"Primary title"}
  title2={"Secondary title"}
  image={"/example.png"}
  on={async () => { console.log("hi"); }}
/>
```

---

### 📌 Example 3: Adding a Right-Side Icon (e.g. Settings)
Includes a right-aligned icon with its own click handler.

```jsx
<Icon2Titles
  title1={"Primary title"}
  title2={"Secondary title"}
  image={"/example.png"}
  righticon={
    <img
      src="https://cdn.qepal.com/qepal/gear.svg"
      onClick={async (e) => {
        e.stopPropagation();
        console.log("wow");
      }}
      style={{ width: 25, height: 25 }}
    />
  }
  on={async () => { console.log("hi"); }}
/>
```

ℹ️ `e.stopPropagation()` is used to prevent the parent `on` handler from firing when the icon is clicked.

---

### 📌 Example 4: Right Icon Using Material UI
Alternative to using an image — here using MUI's `SettingsIcon`.

```jsx
import SettingsIcon from '@mui/icons-material/Settings';

<Icon2Titles
  title1={"Primary title"}
  title2={"Secondary title"}
  image={"/example.png"}
  righticon={
    <SettingsIcon
      onClick={async (e) => {
        e.stopPropagation();
        console.log("wow");
      }}
      style={{ width: 25, height: 25, opacity: 0.6 }}
    />
  }
  on={async () => { console.log("hi"); }}
/>
```

---

### 📌 Example 5: Showing a Percent Indicator
Use the `percent` and `percentColor` props to visually show progress or usage.

```jsx
<Icon2Titles
  title1={"Primary title"}
  title2={"Secondary title"}
  image={"/example.png"}
  percent={25}
  percentColor="#7EB983"
/>
```

---

### 📌 Example 6: Custom Font Sizes
Control font sizes using `f1` (title1) and `f2` (title2). Defaults are `12px` and `11px`.

```jsx
<Icon2Titles
  title1={"Primary title"}
  title2={"Secondary title"}
  image={"/example.png"}
  f1="20px"
  f2="10px"
/>
```

---

### 📌 Example 7: Disable Bold & Hover
Use `nobold` to disable bold font, and `nohover` to remove hover background effect.

```jsx
<Icon2Titles
  title1={"Primary title"}
  title2={"Secondary title"}
  image={"/example.png"}
  nobold
  nohover
/>
```

---

### 📌 Example 8: Custom JSX for Titles and Image
You can pass React elements instead of plain strings for `title1`, `title2`, and `image`.

```jsx
import AcUnitIcon from '@mui/icons-material/AcUnit';

<Icon2Titles
  title1={<f-13 style={{ color: "blue" }}>Primary title</f-13>}
  title2={
    <f-13 style={{ color: "pink", backgroundColor: "black" }}>
      <i>Secondary title</i>
    </f-13>
  }
  image={<AcUnitIcon style={{ fontSize: 30 }} />}
/>
```

> ✅ Using Material Icons like `AcUnitIcon` with `fontSize: 30px` works well for custom image display.

---

### 📝 Notes
- Default component height is `40px`.
- Ideal `righticon` dimensions are `25px × 25px`.
- Highly customizable for both content and interaction needs.
