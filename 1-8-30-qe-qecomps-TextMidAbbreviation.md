**`TextMidAbbreviation`**: Similar to `TextEndAbbreviation`, but it shortens the **middle** of the text.

### Import Path

```ts
import TextEndAbbreviation from '@/frontend/components/qecomps/TextEndAbbreviation';
```

**Example:** The output will be: `exa...ext`

```jsx
export default p => Component(p, Page);
const Page: PageEl = (props, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {

  return <div style={{ direction: z.lang.dir, padding: 10 }}>
    {TextMidAbbreviation("example of a long text", 12)}
  </div>
}
```
