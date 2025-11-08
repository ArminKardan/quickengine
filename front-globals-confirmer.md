### `confirmer`: Global Confirmation Utility

`confirmer` is a global front-end function used to check if the user confirms an action. Like `alerter`, it supports two usage modes:

- **Single argument mode**
- **Multiple argument mode**

It returns a `Promise<boolean>` and should be used with `await` inside an `async` function.

---

### ✅ Example

```jsx
<b-200 class="btn btn-info" onClick={async () => {
  if (await confirmer("Do you agree?"))  // Mode 1
    alerter("1 - You agreed!");
  else
    alerter("1 - You rejected!");

  if (await confirmer("Delete Confirmation", "Do you agree?"))  // Mode 2
    alerter("2 - You agreed!");
  else
    alerter("2 - You rejected!");

  if (await confirmer("Delete Confirmation", <f-10 style={{ color: 'maroon' }}>"Do you agree?"</f-10>))  // Mode 2
    alerter("3 - You agreed!");
  else
    alerter("3 - You rejected!");

  if (await confirmer(
    "Delete Confirmation",
    <f-10 style={{ color: 'maroon' }}>"Do you agree?"</f-10>,
    "Confirm",
    "Reject"
  ))  // Mode 2 with custom button texts
    alerter("4 - You agreed!");
  else
    alerter("4 - You rejected!");
}}>
  Ask user?
</b-200>
```

---

### ⚙️ Function Signatures

#### Mode 1: Single Argument

```ts
confirmer(content: string | JSX.Element): Promise<boolean>
```

#### Mode 2: Multiple Arguments

```ts
confirmer(
  title: string,
  content: string | JSX.Element,
  confirmText?: string,
  cancelText?: string
): Promise<boolean>
```

Use this to customize the dialog title and buttons.
