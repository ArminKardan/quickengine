# Receive data from a Nexus Channel:

Here we receive messages using Nexus Channel from `mychannel` from a [XWebsite](https://qepal.com/docs/2-adminpanel.md) block.

```tsx
import { GenerateMetaDefault, Meta } from '@/common/seo';
import Component, { PageEl } from '@/frontend/components/qecomps/Component'
import type { GetServerSideProps, GetServerSidePropsContext } from 'next';

export default p => Component(p, Page);
const Page: PageEl = (props: {} & { [key: string]: any }, refresh, getProps, onLoad, onConnected, dies, isFront, z) => {

  onConnected(async () => {
    await nexus.subscribe("mychannel");
    nexus.on.channel("mychannel", async specs => {
      let { app, body, fromjid, itsbro, itsme, resource, role, uid } = specs;
      console.log(specs)
    })
  })
  return <div style={{ direction: z.lang.dir, padding: 10 }}>
  </div>
}
```

> Note that body only can be a javascript Object and inside it can be only JSON supported types.


### 💡 `specs` Object Format

```tsx
{
  
  app: string,             // Explore app name
  uid: string,             // Sender's UID
  resource: string,        // Sender's resource ID
  role: "owner" | "partner" | "user", // Sender's role in the Explore project
  body: Object | Array,            // Message body
  itsme: boolean,          // True if this is an echo of the current user’s own message
  itsbro: boolean,         // True if the sender is the same user from another block
  channel: string          // Channel name (empty if it's a direct message)
  fromjid: string,         // Full JID (Jabber ID) of the sender
}
```
---

### 🔸 Field Descriptions

| Field       | Description |
|-------------|-------------|
| `app`       | Explore app name where the sender belongs. |
| `uid`       | Sender's unique user ID. |
| `resource`  | Resource identifier (e.g., block name). |
| `role`      | Sender's role: `owner`, `partner`, or `user`. |
| `body`      | The actual message string. May be empty or null. |
| `itsme`     | True if it's the current user's own message echoed back. |
| `itsbro`    | True if message is sent by same user from another block. |
| `fromjid`   | Full Jabber ID (XMPP address) of the sender. |
| `channel`   | Name of the channel if message came via channel. Otherwise, empty. |

