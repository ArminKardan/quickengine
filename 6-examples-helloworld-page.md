

## 📁 Page File Location

Each language-specific page is located at:

```
./pages/[lang]/index.tsx
```

- `[lang]` represents the selected language of the user:
  - For `Admin Panel`, it's the `middleuser`'s language.
  - For `XWebsite`, it's the `enduser`'s language.

---

## 🧱 Minimum Page Template

Below is the **minimum boilerplate** to define a valid QE page:

```tsx

import { GenerateDefault, Meta } from '@/common/seo';
import Component, { PageEl } from '@/frontend/components/qecomps/Component'
import type { GetServerSideProps, GetServerSidePropsContext } from 'next';

export default p => Component(p, Page);
const Page: PageEl = (props: {} & { [key: string]: any }, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {

  onLoad(async () => { //when component/page loads

  })

  getProps(async (isFront) => { //should be used only when SEO doesn't needed.

  })

  dies(async () => {// when page/component dies

  })

  onConnected(async () => { //when nexus is connected on page

  })

  return <div style={{ direction: z.lang.dir, padding: 10 }}>Hello world!</div>
}


export const getServerSideProps: GetServerSideProps = async (context: GetServerSidePropsContext) => {

  var session = await ((await import('@/backend/SSRVerify.ts')).SSRVerify)(context, false, [])


  let meta: Meta = {} as any;

  GenerateDefault(meta, "آرمین کاردان - وب سایت شخصی",
    "بنیانگذار و استراتژیست تیم پژوهشی تورینگ",
    "https://exirnex.ir/fa",
    "https://exirnex.ir",
    "fa_IR", "https://cdn.qepal.com/qepal/qecircabs.webp", "@qepalcom");


  let obj = await Prosper({
    props: {
      session,
      meta,
    },
  }, context)
  return obj
}

```



### `Component(p, Page)`
 is a QE wrapper that ensures proper lifecycle and context binding.

### `Page` 

supports automatic props and lifecycle injection (`onLoad`, `onConnected`, `dies`, etc.).

### `getServerSideProps`
The server-side `getServerSideProps` integrates:
  - Language resolution
  - Session verification
  - Metadata injection 
  - Translation keys injection from z.lang


### `props` and `refresh`

In QE echosystem we must not use react hooks like setState, useEffect so how to re-render and update information around page? the answer is props and refresh. 

In QE echosystem props is not ready-only it's an environment that contains all our non-volatile variables during refresh.


## props
In QE echosystem props is not ready-only it's an environment that contains all our non-volatile variables during refresh. 

## refresh 
This function will re-render page and everything in the props will be non-volatile and stable to use.


> Example1: [Button click text change example.](https://qepal.com/docs/6-qe-examples-button-text-click.md)


---

### `getProps`
the getProps is a function that is called before page / component is rendered on the screen and we can use it for setting the initial values of variables inside the `props` environment. it gets an async function and we never should use it in page/ components that are important for SEO because it causes blank screen at the first moment in First Contentful Pain (FCP).
> Caution: It's rendered by Server and Browser both so we never use setInterval on this method, instead if we need setInterval we should use `onLoad`.
 
> Example 1: [Button click text change with initial props static value from getProps](https://qepal.com/docs/6-qe-examples-button-text-click-getprops.md)

> Example 2: [Get initial values from an external api by getProps](6-qe-examples-button-text-click-getprops-api.md)

> Example 3: [Get initial values from an internal GAPI by getProps](6-qe-examples-button-text-click-getprops-api.md)


### `onLoad` 
the onLoad function is the called only once [if it's used] when the page is fully loaded. It's useful to do changes automatically after page has been loaded.

> Example 1: [Counter with one second interval](https://qepal.com/docs/)