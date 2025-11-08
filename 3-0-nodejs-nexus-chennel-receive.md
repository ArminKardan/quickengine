# Nexus Channel Message Receive (NodeJS Worker):
Here we set a sample NodeJS worker to listen to a channel named `mychannel`:

```tsx
import { App } from './libs/bridge';

(async () => {

    console.clear()
    await App.Init(false); //run worker, no rest api needed.
    await App.initUDB(); //optional, initializing database
    await App.Connect({public:true}) //connect to nexus

    nexus.on.channel("mychannel", async specs=>{
        let {app, body, fromjid, itsbro, itsme, resource, role, uid} = specs;
        console.log(specs)
    })

})();

```


### 💡 `specs` Object Format

```ts
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

