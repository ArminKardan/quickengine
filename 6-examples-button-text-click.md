
### Button Click Text Change Example
Here we have a button with [Custom tags](https://qepal.com/docs/1-9-qe-customtags.md) that change the button text after clicking on it.

```tsx
import Component, { PageEl } from '@/frontend/components/qecomps/Component'
import type { GetServerSideProps, GetServerSidePropsContext } from 'next'

// Frontend rendering function:
export default p => Component(p, Page)

const Page: PageEl = (
  props,
  refresh,
  getProps,
  onLoad,
  onConnected,
  dies,
  isFront,
  z
) => {
  return <div style={{ direction: z.lang.dir, padding: 10 }}>
  
  <b-200 onClick={async ()=>{
    props.btntext = "Clicked!";
    refresh();
  }}>
  {props.btntext && "Initial value"}</b-200>
  
  </div>
}
```