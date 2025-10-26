
# `Menu` Component Documentation

The `Menu` component is a `Next.js` front-end UI element used to display a small menu below its trigger element (usually a button or similar). It supports multiple clickable options and automatically closes when the user clicks outside of the menu or on one of the menu items.

### Import Statement

```ts
import Menu from '@/frontend/components/qecomps/Menu';
```

### Description

- This component displays a dropdown-style menu when the child element is clicked.
- The menu appears **below and near the child element**.
- The menu **automatically closes** when the user clicks **outside** or selects an **option**.
- It accepts an `options` prop, which is an array of React elements (typically `<f-12>` or other small components), each representing a menu item.

### Example

The following example shows a `Menu` with three selectable options triggered by a button:

```jsx
// Front-end function:
export default p => Component(p, Page);

const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {
  return <div style={{ direction: z.lang.dir, padding: 10 }}>
    <Menu options={[
      <f-12 onClick={() => { console.log("option 1 clicked") }}>Option 1</f-12>,
      <f-12 onClick={() => { console.log("option 2 clicked") }}>Option 2</f-12>,
      <f-12 onClick={() => { console.log("option 3 clicked") }}>Option 3</f-12>,
    ]}>
      <b-200 className='btn btn-primary'>Button</b-200>
    </Menu>
  </div>
}
```

### Behavior Notes

- Clicking on the "Button" opens the menu.
- The menu will contain the three options listed.
- Selecting an option logs a message to the console and closes the menu.
- Clicking outside the menu also closes it.

This component is particularly useful for contextual actions, dropdowns, and user interaction menus.
