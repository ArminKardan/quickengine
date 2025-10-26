# `TextBox` Component Documentation

The `TextBox` component is a single-line text input component that shares many common fields with the `TextArea` component. However, it is restricted to a single line of input and includes additional configuration options tailored to more compact input scenarios.

---

### Import
```js
import TextBox from '@/frontend/components/qecomps/TextBox';
```

---

## Common Fields with `TextArea`

The following fields are supported identically as in `TextArea`:

- `tight`
- `tightkey`
- `defaultValue`
- `placeholder`
- `selectonclick`
- `on`
- `readOnly`

> Note: `TextBox` does **not** support multi-line input, hence no `minHeight`.

---

## Examples

### Example 1: Clearable Text Input Using `deltxt`

Shows a delete icon at the end of the input field. Clicking it clears the text.

```jsx
<TextBox
  title="Enter your message:"
  defaultValue={props.mytxt}
  on={txt => { props.mytxt = txt }}
  tight={props}
  tightkey="mytxt"
  deltxt
/>
```

---

### Example 2: Custom Text Directions with `dir` and `direction`

Use `dir` to specify the input direction and `direction` for the title's direction.

```jsx
<TextBox
  title="ایمیل خود را وارد کنید:"
  on={txt => { props.useremail = txt }}
  placeholder="example@domain.com"
  tight={props}
  tightkey="useremail"
  dir="ltr"
/>
```

---

### Example 3: Icons with Direction Awareness

Add `lefticon` and `righticon`, along with click handlers. Icons are flipped automatically in RTL layouts unless `nolefticonrotate` or `norighticonrotate` are set.

```jsx
<TextBox
  title="Enter your message:"
  on={txt => { props.mytxt = txt }}
  tight={props}
  tightkey="mytxt"
  placeholder="example message"
  fontSize={13}
  lefticon="https://cdn.qepal.com/qepal/1041877.png"
  onlefticon={() => { console.log("left icon is clicked!") }}
  nolefticonrotate
  righticon="https://cdn.qepal.com/qepal/10488819.png"
  onrighticon={() => { console.log("right icon is clicked!") }}
  norighticonrotate
/>
```

---

### Example 4: Advanced Usage with `padding`, `type`, and JSX Icons

Demonstrates usage of custom padding, numeric type, and JSX elements as icons. Also shows `textAlign`.

```jsx
<TextBox
  title="Enter your age:"
  on={txt => { props.mytxt = txt }}
  tight={props}
  tightkey="mytxt"
  placeholder="18"
  fontSize={13}
  lefticon={
    <Img
      src="https://cdn.qepal.com/qepal/1041877.png"
      style={{ width: 30, margin: "0 3px" }}
      on={() => { console.log("Left icon clicked!") }}
    />
  }
  righticon={
    <Img
      src="https://cdn.qepal.com/qepal/10278573.png"
      style={{ width: 30, margin: "0 3px" }}
      on={() => { console.log("Right icon clicked!") }}
    />
  }
  padding="0px 20px 0 10px"
  type="numeric"
  textAlign="center"
/>
```

---

### Summary of Additional Fields

| Field               | Type       | Description |
|--------------------|------------|-------------|
| `deltxt`           | `boolean`  | Enables clear/delete icon |
| `dir`              | `string`   | Input direction (`ltr` or `rtl`) |
| `direction`        | `string`   | Title direction |
| `fontSize`         | `number`   | Font size for input |
| `lefticon`, `righticon` | `string` or `element` | Icons to appear on left or right |
| `onlefticon`, `onrighticon` | `function` | Handlers for icon clicks |
| `nolefticonrotate`, `norighticonrotate` | `boolean` | Prevent icon flip in RTL |
| `padding`          | `string`   | Custom padding for input field |
| `type`             | `string`   | Input type (`numeric`) |
| `textAlign`        | `string`   | Text alignment (`left`, `right`, `center`) |

---

Use `TextBox` for compact, flexible single-line inputs with localization and icon support.