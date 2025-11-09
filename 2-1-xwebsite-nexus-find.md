# Find Nexus Workers

In the example below we find all workers that is available from a Service named `emyapp` and send a `ping` by [Nexus API](https://qepal.com/docs/2-1-xwebsite-nexus-api-send.md) to it.


```tsx
import Component, { PageEl } from '@/frontend/components/qecomps/Component'
import type { GetServerSideProps, GetServerSidePropsContext } from 'next'

// Frontend rendering function:
export default p => Component(p, Page)

const Page: PageEl = (
  props: {} & { [key: string]: any },
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
      let json = await nexus.find({app:"emyapp"});
      if(json.code == 0 && json.jids.length > 0)
      {
        let jid = json.jids.at(0);
        let json_api = await nexus.api({app:"emyapp", cmd:"ping", jid })
        await alerter(json_api)
      }

    }}>Find & Ping</b-200>

  </div>
}
```

