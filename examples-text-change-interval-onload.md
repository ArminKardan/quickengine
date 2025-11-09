
### Text change interval with onLoad
Here we have a text that at initial it's value is "Not started" then after loading page it will count from 1 up.

> Note: Every `setInterval` must be stopped by dies.
```tsx

import { GenerateDefault, Meta } from '@/common/seo';
import Component, { PageEl } from '@/frontend/components/qecomps/Component'
import type { GetServerSideProps, GetServerSidePropsContext } from 'next';

export default p => Component(p, Page);
const Page: PageEl = (props: {} & { [key: string]: any }, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {

  onLoad(async () => { //when component/page loads
    props.counter = 0;
    props.c = setInterval(()=>{props.counter++; refresh()}, 1000)
  })

  dies(async ()=>{
    clearInterval(props.c)
  })

  return <div style={{ direction: z.lang.dir, padding: 10 }}>{props.counter || "Not started"}</div>
}

```

