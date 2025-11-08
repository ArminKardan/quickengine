# Send Data using Nexus Direct request to a sample app:

Here we send an direct request to `emyapp` from a [XWebsite](https://qepal.com/docs/3-xwebsite.md) block.

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
    
    <b-200 style={{ backgroundColor: "green" }} onClick={async () => {
      if (typeof nexus == "undefined") { //nexus is available only for logged in users.
        await loginbyQE();
        return;
      }
      await nexus.direct({app:"emyapp", body:{myval:"Hi from XWebsite!"}})
    }}>Send</b-200>

  </div>
}
```

> Note that body only can be a javascript Object and inside it can be only JSON supported types.