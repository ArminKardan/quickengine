
### `Num2FA` Function

The `Num2FA` function is a utility that converts numeric values into their Persian (Farsi) word representation. This is especially useful in Persian-language applications for formal documents, forms, and UI text.

#### 📦 Import Path

```js
import Num2FA from '@/frontend/components/qecomps/Num2FA';
```

#### 🧠 Description

`Num2FA(number)` takes a numeric input and returns a string with the corresponding Persian phrase.

For example, calling `Num2FA(1000)` will return:

```
یک هزار
```

#### 🧪 Usage Example

The following example shows how to use `Num2FA` within a React component. It renders the Persian equivalent of the number `1000` as `"یک هزار"`:

```jsx
// Front-end function:
export default p => Component(p, Page);

const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {
  return (
    <div style={{ direction: z.lang.dir, padding: 10 }}>
      {Num2FA(1000)}
    </div>
  );
};
```
