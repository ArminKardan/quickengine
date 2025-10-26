
# `DropDown` Component Documentation

The `DropDown` component is a user interface element used to toggle the visibility of its children by clicking a title. It is **not** to be confused with the `Menu` component. While the `Menu` component is a floating selector that closes on item selection or external click, the `DropDown` only toggles open/closed when its title is clicked.

### Import Statement

```ts
import DropDown from '@/frontend/components/qecomps/DropDown';
```

---

## Example 1: Basic DropDown with Text

A basic example where the `DropDown` is controlled using a state property `props.isddopen`.

```jsx
// Front-end function:
export default p => Component(p, Page);
const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {
  return <div style={{ direction: z.lang.dir, padding: 10 }}>
    <DropDown id="test" title='متن باز شونده' state={props.isddopen}>
      The hidden element that by click will be shown
    </DropDown>
  </div>
}
```

---

## Example 2: DropDown Open by Default

You can programmatically set the DropDown to open on initial render by modifying the `props.isddopen` value using `getProps`.

```jsx
// Front-end function:
export default p => Component(p, Page);
const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {

  getProps(async isFront => {
    if (isFront)
      props.isddopen = "open";
  });

  return <div style={{ direction: z.lang.dir, padding: 10 }}>
    <DropDown id="test" title='متن باز شونده' state={props.isddopen}>
      The hidden element that by click will be shown
    </DropDown>
  </div>
}
```

---

## Example 3: Custom Title and Content Background Colors

You can customize the background colors of the title and content areas using `titlebgcolor` and `contentbgcolor` props.

```jsx
// Front-end function:
export default p => Component(p, Page);
const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {
  return <div style={{ direction: z.lang.dir, padding: 10 }}>
    <DropDown
      id="test"
      title='متن باز شونده'
      state={props.isddopen}
      titlebgcolor='#75B058'
      contentbgcolor='#A7C0C4'
    >
      The hidden element that by click will be shown
    </DropDown>
  </div>
}
```

---

### Notes

- The `DropDown` will maintain its open/close state unless explicitly toggled via its title click.
- Ideal for embedding expandable sections in your UI.
