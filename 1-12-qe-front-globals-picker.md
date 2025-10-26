### `picker`: Global Item Selection Utility

`picker` is a global front-end function used to let users select an item from a list. It presents the items in a floating window and returns the `key` of the selected item. If the user cancels, `null` is returned.

---

### 🧾 Input Format

The function expects an array of objects in the following format:

```ts
Array<{ key: string, title1: string, title2: string, image: string }>
```

If your data is in a different structure, you can use `Array.prototype.map()` to transform it.

---

### ✅ Example Usage

```jsx
export default p => Component(p, Page);
const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {

  getProps(() => {
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
          const key = await picker(
            props.items.map(it => ({
              key: it.id,
              title1: it.name,
              title2: "امتیاز:" + it.score,
              image: it.image
            }))
          );
          alerter("شما " + key + " را انتخاب کردید.");
        }}>
          Pick an item from the list
        </b-200>
      </Window>
    </div>
  );
};
```

---

### 📝 Notes

- If the user closes the picker without selecting an item, `null` is returned.
- Returned `key` can be used to identify the selected item.
