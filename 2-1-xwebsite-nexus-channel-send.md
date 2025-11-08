# Send Data using Nexus Direct request to a sample app:

Here we send an direct request to `emyapp` from a [XWebsite](https://qepal.com/docs/3-xwebsite.md) block.

```tsx
import { GenerateMetaDefault, Meta } from '@/common/seo';
import Component, { PageEl } from '@/frontend/components/qecomps/Component'
import type { GetServerSideProps, GetServerSidePropsContext } from 'next';

export default p => Component(p, Page);
const Page: PageEl = (props: {} & { [key: string]: any }, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {

  return <div style={{ direction: z.lang.dir, padding: 10 }}>
    <b-200 style={{ backgroundColor: "green" }} onClick={async () => {
      if (typeof nexus == "undefined") { //nexus is available only for logged in users.
        await loginbyQE();
        return;
      }
      await nexus.subscribe("mychannel")
      await nexus.sendtochannel("mychannel", { myval: "Hi from XWebsite!" });

    }}>Send to mychannel</b-200>
  </div>
}
```

> Note that body only can be a javascript Object and inside it can be only JSON supported types.