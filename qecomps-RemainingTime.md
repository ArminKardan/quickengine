## `RemainingTime`

The `RemainingTime` function calculates the human-readable time difference between two timestamps. It supports automatic multilingual formatting on the front-end and accepts a language code on the back-end.

### Import Path

```ts
import RemainingTime from '@/frontend/components/qecomps/RemainingTime';
```

### Usage (Front-End)

```tsx
export default p => Component(p, Page);
const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {
  return <div style={{ direction: z.lang.dir, padding: 10 }}>
    <c-ss>
      <f-12>{RemainingTime(new Date(), new Date(new Date().getTime() - 3600000))}</f-12>
      <f-12>{RemainingTime(new Date(), new Date(new Date().getTime() - 2 * 3600000))}</f-12>
    </c-ss>
  </div>
}
```

### Parameters

- `biggerTime`: `Date` or `number` (Unix timestamp) - the more recent time.
- `smallerTime`: `Date` or `number` - the earlier time.
- `lang`: _(only on back-end)_ optional `string` (e.g., `"en"`, `"fa"`, `"fr"`, `"ar"`). Ignored on front-end.

### Notes

- Use native `Date` or Unix timestamp values (not ISO strings).
- Automatically localizes time unit (e.g., Minutes, Hours) based on:
  - **Front-End**: user's selected language (`z.lang`).
  - **Back-End**: explicitly passed `lang` string.
- `biggerTime` should be more recent than `smallerTime` (closer to now).

### Example Output (User language = English)

- `RemainingTime(now, now - 3600000)` → `60 Minutes`
- `RemainingTime(now, now - 2 * 3600000)` → `2 Hours`