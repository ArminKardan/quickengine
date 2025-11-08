### `Text` Component

The `Text` component is a versatile utility used to display concise information alongside a title, optional image, and various display options. It's commonly utilized on the QE website to showcase product features such as `price`, `guarantee`, `quota`, `expiration`, etc., where both titles and values are typically short.

> **Import Path:**
```ts
import Text from '@/frontend/components/qecomps/Text';
```

---

### Language-Based Spacing Behavior

By default, spacing between the `title` and `value` is automatically handled based on the selected language using `z.lang.textw`:

- **English**: `calc(max(7rem, 35%))`
- **Farsi**: `calc(max(5rem, 25%))`

To override this and remove the dynamic spacing, use the `nospace` prop. When `nospace` is `true`, a fixed spacing of `<sp-3/>` (6px) is applied between the `title` and `value`.

---

### Usage Examples

#### Example 1: Basic Usage
```tsx
export default p => Component(p, Page);

const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {
  return <div style={{ direction: z.lang.dir, padding: 10 }}>
    <c-x style={{ width: 500, backgroundColor: "#C5E3C0" }}>
      <Text title="Name:" value="Armin" />
    </c-x>
  </div>
}
```

#### Example 2: Without Dynamic Spacing (`nospace`)
```tsx
<Text title="Name:" value="Armin" nospace />
```

#### Example 3: Image Adjacent to Value
```tsx
<Text title="Name:" value="Armin" image="https://cdn.qepal.com/qepal/1006195.png" />
```

#### Example 4: Abbreviate Middle of Value
```tsx
<Text title="Name:" value="Hi how are you doing im well!" abbreviatemid={10} />
```

#### Example 5: Abbreviate End of Value
```tsx
<Text title="Name:" value="Hi how are you doing im well!" abbreviatend={10} />
```

> ✅ When space is limited, use `nospace` in combination with `abbreviatemid` or `abbreviatend`.

#### Example 6: Bold Value Text
```tsx
<Text title="Name:" value="Armin" bold />
```

#### Example 7: Copy to Clipboard
```tsx
<Text title="Name:" value="Here is the text to copy." copy="true" />
```

#### Example 8: Hyperlink Behavior (`href`, `target`)
```tsx
<Text title="Name:" value="Here is the link" href="https://qepal.com" />
<Text title="Name:" value="Here is the link" href="https://qepal.com" target="_blank" />
```

#### Example 9: Internal Navigation (`nexthref`)
```tsx
<Text title="Name:" value="Armin" nexthref={z.root + '/anotherpage'} />
```

#### Example 10: External Link Indicator
```tsx
<Text title="Name:" value="Here is the link." href="https://google.com" extlink />
```

#### Example 11: Background Color
```tsx
<Text title="Name:" value="Text with background" bgcolor="#83CC84" />
```

#### Example 12: Highlight Without Background
```tsx
<Text title="Name:" value="Highlighted text" highlight />
```

#### Example 13: Custom Font Weight
```tsx
<Text title="Name:" value="Armin" fontWeight="bold" />
<Text title="Name:" value="Armin" fontWeight={100} />
<Text title="Name:" value="Armin" fontWeight={600} />
```

#### Example 14: Help Tooltip
```tsx
<Text title="Name:" value="Armin" help onhelp={() => console.log("help clicked!")} />
```

#### Example 15: Clickable Value
```tsx
<Text title="Name:" value="Armin" on={() => console.log("value is clicked!")} />
```

#### Example 16: Image with Click Handler and Custom Size
```tsx
<Text title="Name:" value="Armin" image="https://cdn.qepal.com/qepal/1006195.png" />
<Text title="Name:" value="Armin" image="https://cdn.qepal.com/qepal/1006195.png" onimage={() => console.log("clicked on image!")} />
<Text title="Name:" value="Armin" image="https://cdn.qepal.com/qepal/1006195.png" onimage={() => console.log("clicked on image!")} s={17} />
```

#### Example 17: Image as JSX Element
```tsx
<Text
  title="Name:"
  value="Armin"
  image={
    <Img
      src="https://cdn.qepal.com/qepal/1006195.png"
      style={{ width: 18, height: 18 }}
      on={() => console.log("clicked!")}
    />
  }
/>
```

#### Example 18: Additional Action Link (`wlink`)
```tsx
<Text title="Name:" value="Armin" wlink="edit" />
```

#### Example 19: Customizing `wlink`
```tsx
<Text
  title="Name:"
  value="Armin"
  wlink="edit"
  whighlight
  wbold
  whref="https://google.com"
  wtarget="_blank"
  onwlink={() => console.log("edit clicked!")}
 />
```

#### Example 20: Value Styling Options
```tsx
<Text
  title="Name:"
  value="سلام ای Armin عزیز"
  vdir="rtl"
  vfontSize={11}
  valuecolor="#630707"
/>
```
