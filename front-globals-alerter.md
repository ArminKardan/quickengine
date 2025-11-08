### `alerter`: Global Front-End Alert Utility

`alerter` is a global front-end function similar to `alert`, but more powerful. It displays messages via a floating UI (`WindowFloat`) and supports strings, objects, and JSX content. It also supports styling, titles, and watermark images.

---

### ✅ Basic Example

```jsx
<b-200 class="btn btn-info" onClick={() => {
  alerter("Welcome dear user!");
}}>
  Welcome
</b-200>
```

---

### ⚙️ Usage Modes

#### Mode 1: Single Argument

```ts
alerter(content: string | object | JSX.Element)
```

Displays content directly without a title.

#### Mode 2: Multiple Arguments

```ts
alerter(
  title: string,
  content: string | object | JSX.Element,
  contentStyle?: CSSProperties,
  watermarkImage?: string
)
```

Allows a title, optional styling, and watermark.

**Example:**

```jsx
await alerter(<f-18>Hello</f-18>);
await alerter("Title", "Message", { minHeight: 200 }, "https://example.com/image.png");
```

---

### ⚠️ Important: Use `await` for Multiple Alerts

When using `alerter` in sequence, use `await` to avoid premature dismissal of previous dialogs.

#### Incorrect (will skip first alert):

```jsx
alerter("First");
alerter("Second");
```

#### Correct:

```jsx
await alerter("First");
await alerter("Second");
```

This rule also applies to `confirmer` and `prompter`.
