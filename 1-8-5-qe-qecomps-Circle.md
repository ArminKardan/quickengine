### `Circle` Component

The `Circle` component is a lightweight, circular progress indicator used in the front-end of a Next.js application. It's useful for visually representing percentages, progress states, or metrics in a compact circular format.

---

### Import Statement

```ts
import Circle from '@/frontend/components/qecomps/Circle';
```

---

### Props

| Prop     | Type    | Description                                                                 |
|----------|---------|-----------------------------------------------------------------------------|
| `percent`| number  | Required. A value between `0` and `100` that defines the progress percent. |
| `width`  | number  | Required. The diameter (in pixels) of the circular indicator.              |

---

### Example

In this example, a 50x50 pixel circular progress bar displays `26%` completion.

```tsx
// front-end function:
export default p => Component(p, Page);

const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {
  return (
    <div style={{ direction: z.lang.dir, padding: 10 }}>
      <Circle percent={26} width={50} />
      {/* A 50px by 50px circular progress bar showing 26% */}
    </div>
  );
};
```

This component is styled and rendered automatically based on the percentage and width provided, requiring no additional CSS for typical use.

---