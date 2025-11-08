## QE Real-time Communications (Nexus)

### Overview

**Nexus** is a real-time, XMPP-based communication system used across all users and blocks within the QE ecosystem. It facilitates secure, high-speed communication between frontend and backend components, as well as with hardware devices.

- **Web connectivity** is established via WebSocket.
- **Hardware integration** is supported.
- Compatible with **web**, **mobile**, and **desktop** applications.

Every block that comes online connects to the Nexus network, enabling seamless, peer-to-peer communication across the system. This infrastructure is a core component of QE, contributing to its robustness and scalability as one of the most powerful platforms available.

> **Important Note**: Nexus enforces strict identity validation. Every message contains the sender’s `explore` app name, block identity, and user information. Anonymous message sending is not supported.

---

### Nexus Communication Methods

Nexus enables inter-block communication using three distinct methods:

---

#### 1. Nexus-API

This communication method supports remote procedure calls to workers using multiple listeners. You can send structured data (objects) and receive object-based responses.

> For this type of communication, the requester must `get` the worker's service.

- **Use case**: When a response is required from a worker.
- **Timeout**: Requests time out after 30 seconds if the worker does not respond.
- **Targeting**:
  - Requires the `app` name of the `explore`.
  - Optionally specify the target `resource` for more control.
  - Supports load balancing when no specific worker is targeted.
- **Recommended for**: Request-response interactions with worker blocks.

Examples:
- [How to Receive a Nexus API message from NodeJS worker](https://qepal.com/docs/1-11-qe-nexus-api-receive-js.md)
- [How to Receive a Nexus API message from Python worker](https://qepal.com/docs/1-11-qe-nexus-api-receive-python.md)
- [How to Send a Nexus API message from NodeJS worker](https://qepal.com/docs/1-11-qe-nexus-api-send-js.md)
- [How to Send a Nexus API message from Python worker](https://qepal.com/docs/1-11-qe-nexus-api-send-python.md)
- [How to Send a Nexus API message from XWebsite](https://qepal.com/docs/1-11-qe-nexus-api-send-xwebsite.md)
- [How to Send a Nexus API message from Admin Panel](https://qepal.com/docs/1-11-qe-nexus-api-send-admin-panel.md)

---

#### 2. Nexus-Channel

Nexus-Channel enables broadcast-style communication. Any QE block can **subscribe to** or **publish messages on** a named channel.

> The only way that a [XWebsite](https://qepal.com/docs/3-xwebsite.md) or [Admin panel](https://qepal.com/docs/2-adminpanel.md) can receive realtime data without sending request is a Nexus Channel.

- **Use case**: Broadcasting or aggregating messages between multiple blocks.
- **Message type**: String-based.
- **No need** to specify `app` name or `resource`.
- **Recommended for**:
  - One-to-many or many-to-one communication.
  - Shared data propagation across blocks.


Examples:
- [How to Receive Nexus Channel messages by a NodeJS worker](https://qepal.com/docs/1-11-qe-nexus-direct-receive-js.md)
- [How to Receive Nexus Channel messages by a Python worker](https://qepal.com/docs/1-11-qe-nexus-direct-receive-python.md)

- [How to Send Nexus Channel messages by a NodeJS worker](https://qepal.com/docs/1-11-qe-nexus-direct-send-js.md)
- [How to Send Nexus Channel messages by a Python worker](https://qepal.com/docs/1-11-qe-nexus-direct-send-python.md)

- [How to Send Nexus Channel messages in XWebsites](https://qepal.com/docs/1-11-qe-nexus-direct-send-js.md)
- [How to Send Nexus Channel messages in Admin Panels](https://qepal.com/docs/1-11-qe-nexus-direct-send-js.md)

---

#### 3. Nexus-Direct

This method enables one-way, string-based messaging to a specific worker without expecting a response.

- **Use case**: Fire-and-forget style commands.
- **Listeners**: One listener per worker.
- **No response or timeout handling**.
- **Targeting**:
  - Requires the `app` name and the exact `resource` of the destination worker.
- **Recommended for**: Lightweight commands where acknowledgment is not needed.

Examples:
- [How to Receive Nexus Direct messages by a NodeJS worker](https://qepal.com/docs/1-11-qe-nexus-direct-receive-js.md)
- [How to Receive Nexus Direct messages by a Python worker](https://qepal.com/docs/1-11-qe-nexus-direct-receive-python.md)

- [How to Send Nexus Direct messages by a NodeJS worker](https://qepal.com/docs/1-11-qe-nexus-direct-send-js.md)
- [How to Send Nexus Direct messages by a Python worker](https://qepal.com/docs/1-11-qe-nexus-direct-send-python.md)

- [How to Send Nexus Direct messages in XWebsites](https://qepal.com/docs/1-11-qe-nexus-direct-send-js.md)
- [How to Send Nexus Direct messages in Admin Panels](https://qepal.com/docs/1-11-qe-nexus-direct-send-js.md)

---



These methods provide flexible, reliable, and secure ways to orchestrate real-time communication in QE’s distributed architecture.
