

## 📁 Component File Location

Each language-specific component is located at:

```
@/frontend/myfolder/MyComponent.tsx
```

---

## 🧱 Minimum Component Template

Below is the minimum boilerplate to define a valid QE component:


> Note: onConnected method is unusable for components and it's only called on QE pages when the Nexus is connected on browser side. 
```tsx

import { GenerateDefault, Meta } from '@/common/seo';
import Component, { PageEl } from '@/frontend/components/qecomps/Component'
import type { GetServerSideProps, GetServerSidePropsContext } from 'next';

export default p => Component(p, Page);
const Page: PageEl = (props: {} & { [key: string]: any }, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {

  onLoad(async () => { //[if needed] when component/page loads

  })

  getProps(async (isFront) => { //[if needed] should be used only when SEO doesn't related to this component.

  })

  dies(async () => {// [if needed]  when component dies

  })

  return <div style={{ direction: z.lang.dir, padding: 10 }}>Hello world!</div>
}

```
