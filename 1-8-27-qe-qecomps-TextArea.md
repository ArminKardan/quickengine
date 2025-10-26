
# `TextArea` Component

The `TextArea` component is a multi-line text input with a title and several configuration options. It supports bidirectional binding via `tight` and `tightkey`, change detection with the `on` callback, and additional tuning options for layout, styling, and behavior.

> **Import Path:**
```ts
import TextArea from '@/frontend/components/qecomps/TextArea';
```

---

### Example 1: Basic Two-Way Binding with `tight` and `tightkey`

Use the `tight` prop to bind the text area value to a property (`tightkey`) on an object. This creates two-way binding, meaning updates from either the UI or code reflect immediately.

```tsx
export default p => Component(p, Page);

const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {
  return <div style={{ direction: z.lang.dir, padding: 10 }}>
    <TextArea
      title="Enter your message:"
      on={txt => { props.mytxt = txt }}
      tight={props}
      tightkey="mytxt"
    />
    <b-200 className="btn btn-neutral" onClick={() => { props.mytxt = "wow!"; }}>
      Change text
    </b-200>
  </div>;
};
```

- Typing updates `props.mytxt`.
- Updating `props.mytxt` elsewhere instantly updates the input area without a refresh.

---

### Example 2: Setting a Default Value

Assign a default value using `defaultValue`. Initialize the value before render using `getProps`.

```tsx
export default p => Component(p, Page);

const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {
  getProps(async () => {
    props.mytxt = "example message";
  });

  return <div style={{ direction: z.lang.dir, padding: 10 }}>
    <TextArea
      title="Enter your message:"
      defaultValue={props.mytxt}
      on={txt => { props.mytxt = txt }}
      tight={props}
      tightkey="mytxt"
    />
    <b-200 className="btn btn-neutral" onClick={() => { props.mytxt = "wow!"; }}>
      Change text
    </b-200>
  </div>;
};
```

---

### Example 3: Additional Optional Props

Several additional props are available for fine-tuning behavior and appearance:

```tsx
<TextArea
  title="Enter your message:"
  on={txt => { props.mytxt = txt }}
  tight={props}
  tightkey="mytxt"
  bold
  minHeight={500}
  placeholder="Example message"
  selectonclick
/>
```

#### Optional Props

| Prop           | Type        | Description                                                                 |
|----------------|-------------|-----------------------------------------------------------------------------|
| `bold`         | `boolean`   | Makes the `title` bold.                                                    |
| `minHeight`    | `number`    | Sets the minimum height (in pixels) of the text area.                      |
| `placeholder`  | `string`    | Text to display when the input is empty.                                   |
| `readOnly`     | `boolean`   | Makes the text area non-editable.                                          |
| `selectonclick`| `boolean`   | Selects all text in the area when the user clicks inside it.              |

---

This component is ideal for capturing longer form text inputs while retaining reactive, two-way data binding.
