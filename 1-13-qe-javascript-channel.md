# QE Nexus Integration (Javascript)

## Overview

In QE Javascript environments (`microservice`, `xwebsite` frontend  and backend, GAPI), and also `nodejs-worker` the global `nexus` object enables communication with all blocks. One of its features is **Channel Messaging**, a publish-subscribe model that allows applications to broadcast and receive messages across shared "channels".

This is useful for real-time interactions such as logs, event updates, and state sharing among clients and services.

---

## Nexus Channel Communication

Channels in Nexus function like private chat rooms. Clients can **subscribe** to a channel, receive messages through a **message receiver**, and optionally **send messages** to it.

> ✅ Nexus channels are secure and scoped: only those who know the exact channel name can subscribe. Channel listings are hidden from all users except super admins.

---

### 🔹 Step 1: Subscribe to a Channel

```js
await nexus.subscribe(channelName: string)
```

Subscribes the current session to a named channel.

---

### 🔹 Step 2: Assign Message Receiver

Define a handler for all incoming Nexus messages, including both **direct** and **channel-based** messages:

```js
nexus.msgreceiver = async (specs) => {
  // handle incoming message
}
```


### 💡 `specs` Object Format

```ts
{
  fromjid: string,         // Full JID (Jabber ID) of the sender
  app: string,             // Explore app name
  uid: string,             // Sender's UID
  resource: string,        // Sender's resource ID
  role: "owner" | "partner" | "user", // Sender's role in the Explore project
  body: string,            // Message body
  itsme: boolean,          // True if this is an echo of the current user’s own message
  itsbro: boolean,         // True if the sender is the same user from another block
  channel: string          // Channel name (empty if it's a direct message)
}
```
---

### 🔸 Field Descriptions

| Field       | Description |
|-------------|-------------|
| `fromjid`   | Full Jabber ID (XMPP address) of the sender. |
| `app`       | Explore app name where the sender belongs. |
| `uid`       | Sender's unique user ID. |
| `resource`  | Resource identifier (e.g., block name). |
| `role`      | Sender's role: `owner`, `partner`, or `user`. |
| `body`      | The actual message string. May be empty or null. |
| `itsme`     | True if it's the current user's own message echoed back. |
| `itsbro`    | True if message is sent by same user from another block. |
| `channel`   | Name of the channel if message came via channel. Otherwise, empty. |

> ⚠️ **Note:** All Nexus communications **must** go through the `nexus` object. Do not use raw XMPP commands.

---

---

### 🔹 Step 3: Send Message to Channel

Here we send our string message to the channel.

```js
await nexus.sendtochannel(channelname: string, body: string);
```


## 📦 Example: Channel Subscription & Messaging

```jsx

  await nexus.subscribe("testchannel");

  nexus.msgreceiver = async specs => {
    let { app, resource, uid, itsme, itsbro, fromjid, role, body, channel } = specs;
    console.log(`[${channel}] ${uid} (${role}): ${body}`);
  };

  await nexus.sendtochannel("testchannel", "hi from me");

```