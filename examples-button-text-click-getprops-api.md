
### Button Click Text Change Example + getProps
Here we have a button with [Custom tags](https://qepal.com/docs/1-9-qe-customtags.md) that change the button text after clicking on it. Here ve use getProps to have initial values of `props.btntext` before the page/component loads.

> Remember that We never use `getProps` while the component / page is needed for SEO.


In below example the page / component will be loaded with fetched json by external website using api and set the value to `props.btntext` and after user clicks on the button the page / component will re-render and the button's text will change to `Clicled!`.


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

  getProps(async (isFront)=>{
    let json = await api("https://example.com/api/text");
    props.btntext = json.value
  })

  return <div style={{ direction: z.lang.dir, padding: 10 }}>
  <b-200 onClick={async ()=>{
    props.btntext = "Clicked!";
    refresh();
  }}>
  {props.btntext}</b-200>
  
  </div>
}
```