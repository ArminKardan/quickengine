## Nexus 

### Overview

**Nexus** is a real-time communication system used across all users and blocks within the QE ecosystem. It facilitates secure, high-speed communication between frontend and backend components, as well as with hardware devices.

Every block that comes online connects to the Nexus network, enabling seamless, peer-to-peer communication across the system. This infrastructure is a core component of QE, contributing to its robustness and scalability as one of the most powerful platforms available.

> **Important Note**: Nexus enforces strict identity validation. Every message contains the sender’s Service app name, block identity, and user information. Anonymous message sending is not supported.

---

### Nexus Communication Methods

Nexus enables inter-block communication using three distinct methods:

#### 1. Nexus API

This communication method supports remote procedure calls to workers using multiple listeners. You can send structured data (objects) and receive object-based responses.

> For this type of communication, the requester must `get` the worker's service.

- **Use case**: When a response is required from a worker.
- **Timeout**: Requests time out after 30 seconds if the worker does not respond.


Examples:
- [How to Receive a Nexus API message from NodeJS worker](https://qepal.com/docs/3-0-nodejs-nexus-api-receive.md)
- [How to Receive a Nexus API message from Python worker](https://qepal.com/docs/3-1-python-nexus-api-receive.md)
- [How to Send a Nexus API message from NodeJS worker](https://qepal.com/docs/3-0-nodejs-nexus-api-send.md)
- [How to Send a Nexus API message from Python worker](https://qepal.com/docs/3-1-python-nexus-api-send.md)
- [How to Send a Nexus API message from XWebsite](https://qepal.com/docs/2-1-xwebsite-nexus-api-send.md)
- [How to Send a Nexus API message from Admin Panel](https://qepal.com/docs/2-0-adminpanel-nexus-api-send.md)

---

#### 2. Nexus Channel

Nexus Channel enables broadcast-style communication. Any QE block can **subscribe to** or **publish messages on** a named channel.

> The only way that a [XWebsite](https://qepal.com/docs/3-xwebsite.md) or [Admin panel](https://qepal.com/docs/2-adminpanel.md) can receive realtime data without sending request is a Nexus Channel.


Examples:
- [How to Receive Data from a Nexus Channel by Admin Panel](https://qepal.com/docs/2-0-adminpanel-nexus-channel-receive.md)
- [How to Receive Data from a Nexus Channel by XWebsite](https://qepal.com/docs/2-1-xwebsite-nexus-channel-receive.md)
- [How to Receive Data from a Nexus Channel by a NodeJS worker](https://qepal.com/docs/3-0-nodejs-nexus-chennel-receive.md)
- [How to Receive Nexus Channel messages by a Python worker](https://qepal.com/docs/3-1-python-nexus-channel-receive.md)
- [How to Send Data to a Nexus Channel in Admin Panels](https://qepal.com/docs/2-0-adminpanel-nexus-channel-send.md)
- [How to Send Data to a Nexus Channel in XWebsites](https://qepal.com/docs/2-1-xwebsite-nexus-channel-send.md)
- [How to Send Data to a Nexus Channel in NodeJS worker](https://qepal.com/docs/3-0-nodejs-nexus-channel-send.md)
- [How to Send Data to a Nexus Channel in Python worker](https://qepal.com/docs/3-1-python-nexus-channel-send.md)

---

#### 3. Nexus Direct

This method enables one-way, string-based messaging to a specific worker without expecting a response.

> Only Worker Blocks can listen to directs.

Examples:
- [How to Receive Data using Nexus Direct by a NodeJS worker](https://qepal.com/docs/3-0-nodejs-nexus-direct-receive.md)
- [How to Receive Data using Nexus Direct by a Python worker](https://qepal.com/docs/3-1-python-nexus-direct-receive.md)
- [How to Send Data using Nexus Direct in Admin Panels](https://qepal.com/docs/2-0-adminpanel-nexus-direct-send.md)
- [How to Send Data to a Nexus Direct in XWebsites](https://qepal.com/docs/2-1-xwebsite-nexus-direct-send.md)
- [How to Send Data to a Nexus Direct in NodeJS worker](https://qepal.com/docs/3-0-nodejs-nexus-direct-send.md)
- [How to Send Data to a Nexus Direct in Python worker](https://qepal.com/docs/3-1-python-nexus-direct-send.md)



#### 4. Nexus Find

When we need to find our worker blocks on our user on QE we use this method. it can be used for finding Enduser workers in XWebsite front-end too.

- [How to Find Workers using Nexus Find in a Admin Panels](https://qepal.com/docs/2-0-adminpanel-nexus-find.md)
- [How to Find Workers using Nexus Find in a XWebsites](https://qepal.com/docs/2-1-xwebsite-nexus-find.md)
- [How to Find Workers using Nexus Find in a NodeJS worker](https://qepal.com/docs/3-0-nodejs-nexus-find.md)
- [How to Find Workers using Nexus Find in a Python worker](https://qepal.com/docs/3-1-python-nexus-find.md)