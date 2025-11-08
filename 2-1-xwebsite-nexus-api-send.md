# Send Nexus API request to a built-in QE app from XWebsite block:
Here we send an api ping request to `eagents` from front-end of a [XWebsite](https://qepal.com/docs/3-xwebsite.md) block (a sample QE built-in app) app and get it's response. Here we used `<b-200>` from [QE Custom Tags](https://qepal.com/docs/1-9-qe-customtags.md) and send a ping request using nexus.

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
      let json = await nexus.api({ app: "eagents", cmd: "ping" });
      await alerter(json) //it should show message {code:0, pong:true}
    }}>Ping</b-200>

  </div>
}
```



# Send Nexus API request + Data to a built-in QE app from XWebsite block:
Here we send an api ping request to `eagents` from front-end of a [XWebsite](https://qepal.com/docs/3-xwebsite.md) block (a sample QE built-in app) app and get it's response. Here we used `<b-200>` from [QE Custom Tags](https://qepal.com/docs/1-9-qe-customtags.md) and send a ping request using nexus.

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
      let json = await nexus.api({ app: "eagents", cmd: "ping", body:{myval:"Hi from XWebsite!"} });
      await alerter(json) //it should show message {code:0, pong:true}
    }}>Ping</b-200>

  </div>
}
```

> Note that body only can be a javascript Object and inside it can be only JSON supported types.