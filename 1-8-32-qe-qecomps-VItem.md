
**`VItem`**: It's a very useful and important component of QE and by this we can have an icon (image) and a text below it. It can be imported by:

```ts
import VItem from '@/frontend/components/qecomps/VItem';
```

It can be highlighted (selected) by the field `selected` and has lots of useful optional fields as shown in the examples below.

---

### **Example 1:** Basic clickable items

```jsx
<w-x>
  <VItem title={"Item 1"} image='https://cdn.qepal.com/qepal/10319754.png' on={()=>{console.log("Item 1 clicked.")}} />
  <VItem title={"Item 2"} image='https://cdn.qepal.com/qepal/10073813.png' on={()=>{console.log("Item 2 clicked.")}} />
  <VItem title={"Item 3"} image='https://cdn.qepal.com/qepal/10415700.png' on={()=>{console.log("Item 3 clicked.")}} />
</w-x>
```

---

### **Example 2:** Using a list to render multiple items

```jsx
<w-c>
  {props.items.map(item => <VItem
    title={item.name}
    image={item.icon}
    on={() => { console.log("Item 1 clicked.") }}
  />)}
</w-c>
```

---

### **Example 3:** Selectable items (radio-like behavior)

```jsx
<w-c>
  {props.items.map(item => <VItem
    title={item.name}
    image={item.icon}
    selected={item.selected}
    on={() => {
      props.items.forEach(it => it.selected = false)
      item.selected = true; refresh()
    }}
  />)}
</w-c>
```

---

### **Example 4:** Scaling down the item size

```jsx
<w-c>
  {props.items.map(item => <VItem
    title={item.name}
    image={item.icon}
    selected={item.selected}
    style={{ transform: "scale(0.8)" }}
    on={() => {
      props.items.forEach(it => it.selected = false)
      item.selected = true; refresh()
    }}
  />)}
</w-c>
```

---

### **Example 5:** Adding a secondary icon (`image2`)

```jsx
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
```

---
