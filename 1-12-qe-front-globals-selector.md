### `selector`: Global Multi-Item Selection Utility

`selector` is a global front-end function for selecting multiple items from a list. It takes two arguments:

1. A **sync function** that returns an array of items in the format:
   ```ts
   Array<{
     key: string;
     title1: string;
     title2: string;
     image: string;
     highlight: boolean;
   }>
   ```

2. An **async function** called when an item is clicked, receiving the item's `key`.

---

### ✅ Behavior

- Selected items are visually highlighted (`highlight: true`).
- You can use a custom field (e.g. `selected`) to track selection state.
- Toggle selection with `^= 1` to flip the boolean.

---

### 📌 Example

```jsx
export default p => Component(p, Page);
const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {

  getProps(async () => {
    props.items = [
      {
        id: "id1",
        name: "name1",
        score: 100,
        image: "/image1.jpg"
      },
      {
        id: "id2",
        name: "name2",
        score: 100,
        image: "/image2.jpg"
      },
    ];
  });

  return (
    <div style={{ direction: z.lang.dir, padding: 10 }}>
      <Window title="Global functions" contentStyle={{ padding: 10 }}>
        <b-200 class="btn btn-info" onClick={async () => {
          await selector(
            () => props.items.map(it => ({
              key: it.id,
              title1: it.name,
              title2: "امتیاز:" + it.score,
              image: it.image,
              highlight: it.selected
            })),
            async key => {
              props.items.find(i => i.id === key).selected ^= 1;
            }
          );

          await alerter("selected items", props.items.filter(it => it.selected));
        }}>
          Select multiple item from list
        </b-200>
      </Window>
    </div>
  );
};
```

After the user selects items and closes the selector, you can inspect the `selected` field on each item to identify the chosen entries.
