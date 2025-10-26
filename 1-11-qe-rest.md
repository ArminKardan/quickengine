# QE Rest APIs

Every server-side block in QE—including `microservice` backends, `xwebsite` backends, and the [QE Website](https://qepal.com)—exposes REST APIs for control and communication. Worker blocks such as `nodejs-worker`, `python-worker`, and `golang-worker` also use REST APIs.

Both **Nexus** and **REST API** methods are supported, each with distinct pros and cons.

---

## 🔁 Nexus Protocol

### ✅ Pros:
- **Low latency** bi-directional protocol with three communication modes.
- Persistent TCP connection (no need to reconnect each time).
- Written in **Rust**, ensuring lightweight and high-speed performance.
- **Secure**: Each message includes sender identity and origin (Explore instance).
- **No anonymous communication**: All participants are identified.
- **Hardware bridging**: Supports MQTT for hardware integration.
- **Real-time** and **bi-directional**.
- **DDoS protection**: Participants can be blocked at the protocol level.

### ❌ Cons:
- Requires a central QE server; entire Nexus network goes down if the server fails.
- **Proprietary**: Only QE blocks can use it directly.
- Needs custom client libraries for integration with third-party systems.

---

## 🌐 REST API

### ✅ Pros:
- **Standardized**: Compatible with nearly all systems and technologies.
- **Simple to implement** and maintain.
- **Distributed**: Each block runs its own API server; no single point of failure.
- **Firewall-friendly**: More tolerant of restrictive network environments.

### ❌ Cons:
- Less secure: Lacks identity tracking of Nexus.
- **Unidirectional**: Doesn't support peer-to-peer communication (e.g., two frontends).
- Allows **anonymous** access from outside the QE network (identifiable only by IP).
- Only **semi-real-time**; slower compared to Nexus.