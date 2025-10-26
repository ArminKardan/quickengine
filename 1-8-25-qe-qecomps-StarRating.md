
# `StarRating` Component

The `StarRating` component is a UI element used for rendering and interacting with star-based ratings. It is commonly used in product reviews, feedback forms, and user-generated content systems.

## Import

```ts
import StarRating from '@/frontend/components/qecomps/StarRating';
```

## Example

```tsx
export default p => Component(p, Page);

const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {

  getProps(async () => {
    props.stars1 = 3.7;
  });

  return (
    <div style={{ direction: z.lang.dir, padding: 10 }}>
      <f-cse>
        <c-cc>
          <StarRating
            stars={props.stars1 || 0}
            on={(num) => {
              props.stars1 = num;
              refresh();
            }}
            id="star_test1"
          />
          <StarRating
            stars={props.stars1 || 0}
            on={(num) => {
              refresh({ stars1: num });
            }}
            id="star_test2"
            width={20}
          />
          <StarRating
            stars={props.stars1 || 0}
            on={(num) => {
              refresh({ stars1: num });
            }}
            id="star_test3"
            width={15}
          />
        </c-cc>

        <c-cc>
          <StarRating
            stars={props.stars2 || 0}
            on={(num) => {
              refresh({ stars2: num });
            }}
            id="star_test4"
          />
          <StarRating
            stars={props.stars2 || 0}
            on={(num) => {
              refresh({ stars2: num });
            }}
            id="star_test5"
            width={20}
          />
          <StarRating
            stars={props.stars2 || 0}
            on={(num) => {
              refresh({ stars2: num });
            }}
            id="star_test6"
            width={15}
          />
        </c-cc>
      </f-cse>
    </div>
  );
};
```

## Key Properties

- **`stars`**: `number`  
  The current rating value (can be a decimal like `3.7`). Typically controlled via a state variable in `props`.

- **`on`**: `(value: number) => void`  
  Callback that is triggered when the user selects a star. Use this to update the backing state (e.g., in `props` or a store).

- **`id`**: `string` _(required)_  
  A unique identifier for each instance of `StarRating`. Each component must have a unique `id` to function correctly.

- **`width`**: `number` _(optional)_  
  Customizes the size (width) of the star icons. Useful for scaling the component in different UIs.

## Notes

- It's essential that each `StarRating` instance has a unique `id`.
- Ratings are maintained in state variables like `props.stars1`, which can be pre-set via `getProps` or backend values.
- The component updates the associated state when a user clicks a star.

---

This makes `StarRating` a flexible tool for collecting user ratings in a visually intuitive way.
