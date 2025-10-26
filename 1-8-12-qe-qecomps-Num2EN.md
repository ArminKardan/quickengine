
### `Num2EN` Function

The `Num2EN` function is a utility that converts numeric values into their English word representation. This is particularly useful for applications requiring spelled-out numbers in forms, documents, or reports.

#### 📦 Import Path

```js
import Num2EN from '@/frontend/components/qecomps/Num2EN';
```

#### 🧠 Description

`Num2EN(number)` takes a numeric input and returns a string with the corresponding English phrase.

For example, calling `Num2EN(1000)` will return:

```
One Thousand
```

#### 🧪 Usage Example

The following example shows how to use `Num2EN` within a React component. It renders the text `"One Thousand"`:

```jsx
// Front-end function:
export default p => Component(p, Page);

const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {
  return (
    <div style={{ direction: z.lang.dir, padding: 10 }}>
      {Num2EN(1000)}
    </div>
  );
};
```
