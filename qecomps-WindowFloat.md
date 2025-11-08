
# `WindowFloat` Component

The `WindowFloat` component is arguably the most important component in the QE front-end system. It is a floating version of the `Window` component that appears in the center of the screen with a dark overlay background, drawing focus to its contents. It is typically used to show forms or modal content and **must not** be used without a conditional render — it should appear only when needed, like for showing a popup form.

## Import Path

```js
import WindowFloat from '@/frontend/components/qecomps/WindowFloat';
```

## Example 1: Basic Usage with a Toggle

In this example, we show a `VItem` inside a `Window`. Clicking on the item opens a `WindowFloat` showing details.

```jsx
{props.form == "settings" ? <WindowFloat title='Settings form' onclose={()=>{refresh({form:null})}}>
  The item will be here
</WindowFloat> : null}

<Window title='Items' contentStyle={{ padding: 10 }}>
  <VItem title={"The item"}
    image='https://cdn.qepal.com/qepal/10415700.png'
    on={() => { refresh({ form: "settings" }) }}
    style={{transform:"scale(0.9)"}}
  />
</Window>
```

## Example 2: Selecting an Icon for Each Item

Clicking on a `VItem` opens a `WindowFloat` that lets users select a new icon from a list.

```jsx
{props.form == "changeicon" ? <WindowFloat
  title='Icon list'
  onclose={() => { refresh({ form: null }) }}>
  <w-xse>
    {props.icons.map(icon => {
      return <VItem image={icon} style={{ transform: "scale(0.8)" }} on={() => { props.item.icon = icon; refresh({ form: null }) }} />
    })}
  </w-xse>
</WindowFloat> : null}
```

## Example 3: Multi-Step Icon Selection

This example has three modal forms:

- `chooseaction`: Let user pick which icon to change.
- `chooseimg1`: Select icon1 (`image`).
- `chooseimg2`: Select icon2 (`image2`).

```jsx
{props.form == "chooseaction" ? <WindowFloat title='Choose action' onclose={() => { refresh({ form: null }) }}>
  <w-xse>
    <VItem title={"Change Image1"} image='https://cdn.qepal.com/qepal/edit.svg' on={() => { refresh({ form: "chooseimg1" }) }} />
    <VItem title={"Change Image2"} image='https://cdn.qepal.com/qepal/edit.svg' on={() => { refresh({ form: "chooseimg2" }) }} />
  </w-xse>
</WindowFloat> : null}
```

## Example 4: Styling and Advanced Options

`WindowFloat` supports the following props:

- `contentStyle`: Style for content container.
- `contentbgcolor`: Background color for content.
- `titlebgcolor`: Background color for title bar.
- `titletextcolor`: Text color of title.
- `maxWidth`: Maximum width of the floating window (number or string).
- `watermarkimg`: URL for a faded watermark behind the content.
- `onhelp`: Function triggered when help icon is clicked.

```jsx
{props.form == "settings" ? <WindowFloat
  title='Settings form'
  maxWidth={500}
  watermarkimg='https://cdn.qepal.com/qepal/10703030.png'
  onhelp={()=>{console.log("user needs help...")}}
  onclose={() => { refresh({ form: null }) }}>
  Settings will be here
</WindowFloat> : null}
```

## Usage Guidelines

- Always control `WindowFloat` with a conditional (e.g., `props.form == "..."`).
- Use `onclose` to hide the modal.
- Pair with `refresh()` to rerender or update props.
