
## `PhoneEditFloat`

The `PhoneEditFloat` component allows users to input a phone number along with the country code in a floating window. It includes two parts:

1. **Country Selector** – a list of countries with phone code, name, and flag.
2. **Phone Input** – a textbox for entering the number and a `Done` button.

When `Done` is clicked, an object is passed to the `on` function in this format:

```ts
{
  ccode: string,   // e.g., "+1" for USA or "+98" for Iran
  phone: string,   // user's entered phone number
  cchar: string    // ISO 2-char country code, e.g., "US", "IR", "MX"
}
```

**Import Statement:**
```ts
import PhoneEditFloat from '@/frontend/components/qecomps/PhoneEditFloat';
```

---

### Example 1: Simple Usage

```jsx
export default p => Component(p, Page);
const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {
  return <div style={{ direction: z.lang.dir, padding: 10 }}>
    <PhoneEditFloat
      title='ورود شماره تماس'
      title2='لطفا شماره تماس خود را وارد کنید'
      explain={"۱: " + "لطفا شماره تماس خود را به دقت وارد نمایید."}
      countryitemclass={`flex min-h-[40px] rounded-md items-center bg-[#84B780] hover:bg-[#83BF7F] active:bg-[#79B075] m-1 cursor-pointer`}
      clist={{ title: z.lang.selcountry, title2: z.lang.searchccodes }}
      on={async (json) => { console.log(json) }}
      onclose={() => { }}
    />
  </div>
}
```

**Notes:**
- `z.lang.selcountry` and `z.lang.searchccodes` localize the country selection UI.
- `explain` is optional, used to show hints.
- `onclose` is called if the user closes the form without submitting.

---

### Example 2: Controlled Visibility

```jsx
export default p => Component(p, Page);
const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {
  return <div style={{ direction: z.lang.dir, padding: 10 }}>
    {props.form == "myphoneedit" ? <PhoneEditFloat
      title='ورود شماره تماس'
      title2='لطفا شماره تماس خود را وارد کنید'
      explain={"۱: " + "لطفا شماره تماس خود را به دقت وارد نمایید."}
      countryitemclass={`flex min-h-[40px] rounded-md items-center bg-[#84B780] hover:bg-[#83BF7F] active:bg-[#79B075] m-1 cursor-pointer`}
      clist={{ title: z.lang.selcountry, title2: z.lang.searchccodes }}
      on={async (json) => { console.log(json); refresh({ form: null }) }}
      onclose={() => { refresh({ form: null }) }}
    /> : null}
    <b-200 className='btn btn-info' onClick={() => {
      refresh({ form: "myphoneedit" })
    }} >Click to enter phone number!</b-200>
  </div>
}
```

**Notes:**
- Use `props.form` to toggle the visibility of the floating component.
- Once the user clicks `Done` or `Close`, set `props.form` to `null` to hide the component.
- This pattern is reusable for other floating components like `WindowFloat`.

---

### Summary
- `PhoneEditFloat` is a modal input for phone numbers with country code.
- Fully blocks the page until hidden.
- Output format: `{ ccode, phone, cchar }`.
- Must be dismissed by setting `props.form = null`.
