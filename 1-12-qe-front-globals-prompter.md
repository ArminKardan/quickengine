### `prompter`: Global Input Prompt Utility

`prompter` is a global front-end function for receiving user input as a string. It returns a `Promise<string | null>`:
- Returns `string` if the user submits.
- Returns `null` if the user cancels.

---

### ✅ Example 1: Basic Usage

```jsx
<b-200 class="btn btn-info" onClick={async () => {
  let txt = await prompter("Enter your name:");
  if (txt === null) {
    alerter("User canceled the prompt.");
  } else if (txt === "") {
    alerter("User confirmed an empty string.");
  } else {
    alerter("User entered: " + txt);
  }
}}>
  Ask user's name?
</b-200>
```

---

### ⚙️ Usage Modes

#### Mode 1: Single Argument

```ts
prompter(content: string | JSX.Element): Promise<string | null>
```

#### Mode 2: Multiple Arguments

```ts
prompter(
  title: string,
  content: string | JSX.Element,
  maxLength?: number,
  multiline?: boolean,
  defaultValue?: string,
  style?: CSSProperties,
  selectionClick?: boolean,
  inputType?: "email" | "number" | "tel" | "text" | "url"
): Promise<string | null>
```

---

### ✅ Example 2: Advanced Usage

```jsx
<b-200 class="btn btn-info" onClick={async () => {
  let txt1 = await prompter(<f-10>{"Enter your name:"}</f-10>);
  let txt2 = await prompter("User's name", <f-10>{"Enter your name:"}</f-10>);
  let txt3 = await prompter(
    "User's name",
    "Enter your name:",
    100,
    true,
    "Armin",
    {},
    true,
    "email"
  );
}}>
  Ask user's name?
</b-200>
```

`prompter` is async like `alerter` and `confirmer`, and should be used with `await` for proper behavior.
