
# `Window` Component

The `Window` component is a key layout utility in the QE system. It helps organize content into distinct, sectioned UI blocks, similar to desktop application windows. Useful for grouping settings, items, or any type of related UI elements.

## Import Path

```ts
import Window from '@/frontend/components/qecomps/Window';
```

## Example 1: Sectioning with `Window`

Use `Window` to organize different UI sections (e.g., settings vs. item list).

```jsx
export default p => Component(p, Page);
const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {
  getProps(async () => {
    props.items = [
      { name: "Item 1", icon: 'https://cdn.qepal.com/qepal/10319754.png', type: "A" },
      { name: "Item 2", icon: 'https://cdn.qepal.com/qepal/10073813.png', type: "B" },
      { name: "Item 3", icon: 'https://cdn.qepal.com/qepal/10415700.png', type: "C" },
    ]
  })
  return <div style={{ direction: z.lang.dir, padding: 10 }}>
    <Window title='Settings'>
      <Icon2Titles
        title1={"Price"}
        title2={"Click to set the price."}
        image={"https://cdn.qepal.com/qepal/11182140.png"}
        nobold
        style={{ backgroundColor: "#B5D3B5" }}
      />
      <br-xxxx/>
      <Icon2Titles
        title1={"Image"}
        title2={"Click to set the image."}
        image={"https://cdn.qepal.com/qepal/11155574.png"}
        nobold
        style={{ backgroundColor: "#B5D3B5" }}
      />
    </Window>
    <Window title='Items'>
      <w-c>
        {props.items.map(item => {
          let img2 = null
          if (item.type == "A")
            img2 = 'https://cdn.qepal.com/qepal/11048584.png'
          else if (item.type == "B")
            img2 = 'https://cdn.qepal.com/qepal/10246100.png'
          else if (item.type == "C")
            img2 = 'https://cdn.qepal.com/qepal/1100450.png'

          return <VItem
            title={item.name}
            image={item.icon}
            image2={img2}
            selected={item.selected}
            style={{ transform: "scale(0.8)" }}
            on={() => {
              props.items.forEach(it => it.selected = false)
              item.selected = true; refresh()
            }}
          />
        })}
      </w-c>
    </Window>
  </div>
}
```

## Example 2: Custom Content Style

`Window` also supports custom styling for its content section using `contentStyle`:

```jsx
<Window title='Items' contentStyle={{backgroundColor:"pink", padding:5}}>
  <VItem title={"The item"} image='https://cdn.qepal.com/qepal/10415700.png' on={()=>{}} />
</Window>
```

## Example 3: Title Color Customization

You can customize the background and text color of the title area with `titlebgcolor` and `titlecolor`:

```jsx
<Window title='Items' titlebgcolor='#8EC288' titlecolor='maroon'>
  <VItem title={"The item"} image='https://cdn.qepal.com/qepal/10415700.png' on={()=>{}} />
</Window>
```

## Available Props

| Prop            | Type    | Description                                                                 |
|-----------------|---------|-----------------------------------------------------------------------------|
| `title`         | string  | Title text shown at top of window                                           |
| `contentStyle`  | object  | Style applied to content container (under title)                            |
| `titlebgcolor`  | string  | Background color of title section                                           |
| `titlecolor`    | string  | Text color of title section                                                 |

This component is ideal for modular, well-structured UIs.
