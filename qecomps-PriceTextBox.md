# `PriceTextBox` Component Documentation

The `PriceTextBox` is a versatile component used to display or input a numeric value formatted as a price. It supports customization, unit display, click-based recommendation values, and other UX enhancements.

It can be imported using:

```ts
import PriceTextBox from '@/frontend/components/qecomps/PriceTextBox';
```

---

## Example 1: Basic Usage

```jsx
<PriceTextBox
  fractions={0}
  title='Enter price amount:'
  defaultValue={"100"}
  unit={z.lang[z.middleuser.unit]}
  on={(amount:number) => { console.log(amount) }}
/>
```

A price text box that fills its parent container, with a default value of `100`. The unit is based on the user's selected unit.

---

## Example 2: Using `explain` for Hinting Values

```jsx
<PriceTextBox
  fractions={0}
  title='Enter price amount:'
  explain={3000}
  explainstr='Maximum value'
  defaultValue={"100"}
  unit={z.lang[z.middleuser.unit]}
  on={(amount:number) => { console.log(amount) }}
/>
```

Displays a message (e.g., “Maximum value”) that the user can click to auto-fill the price field with the `explain` value.

---

## Example 3: Controlled Input with Minimum and Maximum Rules

```jsx
<PriceTextBox
  fractions={0}
  title='Enter price amount:'
  explain={2000}
  explainstr='Maximum'
  defaultValue={props.amount.toString()}
  unit={z.lang["usd"]}
  on={(amount: number) => { props.withdraw_amount = amount }}
/>
<b-200 className='btn btn-neutral' onClick={async () => {
  if (props.withdraw_amount) {
    if (props.withdraw_amount < 100) {
      alerter("Minimum withdraw amount is 100USD.")
    } else if (props.withdraw_amount > 2000) {
      alerter("Maximum withdraw amount is 2000USD.")
    } else {
      alerter("Your withdraw is valid and it's on process.")
    }
  } else {
    alerter("Please enter price.")
  }
}}>CHECK</b-200>
```

A more complete usage where a user can withdraw an amount between 100 and 2000 USD. Input is validated before proceeding.

---

## Example 4: Read-Only Mode and Left Icon

```jsx
<PriceTextBox
  fractions={0}
  title='Enter price amount:'
  defaultValue={"100"}
  unit={z.lang[z.middleuser.unit]}
  on={(amount: number) => { console.log(amount) }}
  readOnly
  lefticon='https://cdn.qepal.com/qepal/10169352.png'
  onlefticon={() => { alerter("left icon clicked!") }}
/>
```

The field becomes read-only. The left-side icon is clickable and triggers an `onlefticon` callback.

---

## Example 5: Right-Side Custom Content

```jsx
<PriceTextBox
  fractions={0}
  title='Enter price amount:'
  defaultValue={"100"}
  unit={z.lang[z.middleuser.unit]}
  on={(amount: number) => { console.log(amount) }}
  righttext={<f-cc><sp-2/><Flag ccode='ir' style={{width:30}} on={()=>{
    console.log("FLAG CLICKED!")
  }}/></f-cc>}
/>
```

Includes a clickable country flag on the right side—useful for selecting or displaying additional information such as currency or region.

---