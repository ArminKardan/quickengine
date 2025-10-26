
### `Flag` Component

The `Flag` component is a reusable UI component in a Next.js application that allows developers to display the flag of any country using its country code.

#### 📦 Import Path

```js
import Flag from '@/frontend/components/qecomps/Flag';
```

#### 🧠 Description

The `Flag` component renders a country's flag based on the given ISO 3166-1 alpha-2 country code (`ccode`). It accepts standard React props such as `style` to control the appearance, including size and layout. This is particularly useful in internationalized applications where visual identification of regions is needed.

#### 🧪 Usage Example

The example below demonstrates how to render flags for the **United States**, **Australia**, and **Mexico**, each with a width of `50px`:

```jsx
// Front-end function:
export default p => Component(p, Page);

const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {
  return (
    <div style={{ direction: z.lang.dir, padding: 10 }}>
      <Flag ccode="us" style={{ width: 50 }} />
      <Flag ccode="au" style={{ width: 50 }} />
      <Flag ccode="mx" style={{ width: 50 }} />
    </div>
  );
};
```
