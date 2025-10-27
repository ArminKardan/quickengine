## QE Real-time Communications (Nexus)

### Overview

**Nexus** is a real-time, XMPP-based communication system used across all users and blocks within the QE ecosystem. It facilitates secure, high-speed communication between frontend and backend components, as well as with hardware devices. 

- **Web connectivity** is achieved via WebSocket.
- **Hardware integration** is supported through MQTT.
- Compatible with **web**, **mobile**, and **desktop** applications.

Every block that comes online connects to the Nexus network, enabling peer-to-peer messaging across the system. This communication infrastructure is a foundational aspect of QE, making it one of the most powerful frameworks and platforms in the world.

---

### JID (Jabber ID) Format

When a block connects to the Nexus network, it is assigned a unique **Jabber ID (JID)** in the following format:

```
[app]-[userUID]-[role]-[resource]@qepal.com/[resource]
```

#### JID Components

- **`app`**: Refers to the `explore` application's name that owns or utilizes the block.
- **`userUID`**: The unique identifier of the user who owns or is using the block.
- **`role`**:
  - `owner`: Indicates the user is the creator/owner of the `explore`.
  - `user`: Indicates the user is using a shared or purchased explore.
- **`resource`**: Describes the type of client or backend the block represents.

---

### Example

If `userA` (UID: `682ebf741c055d80a4f15f8b`) creates an `explore` with `app: etest` and runs a Node.js block with the resource name `default`, the JID would be:

```
etest-682ebf741c055d80a4f15f8b-owner@qepal.com/default
```

If `userB` (UID: `682ebf741c055d80a4f15f9a`) connects to this `Admin Panel` through the frontend (not as the owner), the JID might be:

```
etest-682ebf741c055d80a4f15f9a-user@qepal.com/webuo1561
```

In this case:
- `etest` is the app name.
- `682ebf741c055d80a4f15f9a` is `userB`’s UID.
- `user` indicates the user is not the owner.
- `webuo1561` is a randomly generated frontend resource identifier.

---

### Resource Types

The `resource` segment in the JID provides additional context about the origin of the connection. Below is a list of common resource types:

| Resource Prefix       | Description                                                                 | Example             |
|------------------------|-----------------------------------------------------------------------------|---------------------|
| `uservice[randomstr]`  | Published Admin Panel backend                                              | `userviceCSDnsa1`   |
| `udevelopment[randomstr]` | Development Admin Panel backend                                         | `udevelopmentQsdE5x`|
| `xservice[randomstr]`  | Published XWebsite backend                                                  | `xserviceRdndS5`    |
| `xdefault[randomstr]`  | Published XWebsite backend (default variant)                                | `xdefaultRdndS5`    |
| `xdevelopment[randomstr]` | Development XWebsite backend                                            | `xdevelopmentqWpK5s`|
| `webuo[randomstr]`     | Development Admin Panel frontend                                           | `webuoxsa15`        |
| `webxo[randomstr]`     | Development XWebsite frontend                                               | `webxoCDSv`         |
| `default[randomstr]`   | Node.js worker                                                              | `defaultDksbnx7`    |
| `pydefault[randomstr]` | Python worker                                                               | `pydefaultOWbhsd`   |
| `godefault[randomstr]` | Golang worker                                                               | `godefaultWDSjs`    |

---

This architecture enables a robust, dynamic, and traceable real-time communication environment across all QE blocks and services.
