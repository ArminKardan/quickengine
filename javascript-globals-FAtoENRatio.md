# FAtoENRatio 

The `FAtoENRatio` function is used to evaluate the ratio of **Farsi (Persian)** characters to **non-Farsi** characters in a given string. This function is helpful for content validation, localization checks, and dynamic language-based rendering.


## Description

**Function Signature**:
```ts
FAtoENRatio(input: string): number
```

- **Input**: A `string` to be evaluated.
- **Output**: A `number` between `0` and `1` representing the proportion of Farsi characters:
  - `1.0` → The string is fully Persian.
  - `0.0` → No Persian letters are present.

---

### Example

In this example, a string is sent from the back-end to the front-end. The `FAtoENRatio` function is used on the front-end to calculate the proportion of Farsi characters before rendering the result.

```ts
FAtoENRatio(inputString);
```

**Expected Output**:
If the string is `"hi من آرمینم"`, the function would return approximately `0.8`.

---
