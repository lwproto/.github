<p align="center">
<img src="https://raw.githubusercontent.com/lwproto/.github/refs/heads/main/images/logo.svg" alt="lwproto">
</p>

<p align="center">
<em>"Don't turn a matchstick into a multicooker!"</em>
</p>

<p align="center">
  <strong>Lightweight protocol stack for resource-constrained IoT and embedded systems</strong>
</p>

## What is lwproto?

`lwproto` is a family of **independent, lightweight protocols** designed for **resource-constrained devices** and **low-bandwidth networks**.

It is built for environments where:

* RAM is measured in kilobytes
* Every milliwatt matters
* Radio links are narrow or unreliable, such as **LoRa**, **BLE**, **NB-IoT**, and **EDGE**
* Even wired links such as **CAN** and **RS-485** still need compact framing

The stack is intentionally small, modular, and transport-neutral. Each protocol can be used on its own, without depending on the others or on any specific transport layer.

## Core philosophy

lwproto exists for one reason: to solve communication problems without dragging in unnecessary complexity.

The guiding principles are:

* **Minimal overhead** - as little as **4 bytes**
* **Transport-agnostic** - works over any byte-oriented channel
* **Modular** - use only the protocols you actually need
* **Platform-neutral** - no lock-in, no hidden dependencies
* **Resource-aware** - designed with constrained memory, CPU, and bandwidth in mind

This is a stack for embedded systems that need efficiency first, not feature bloat.

## Current stack

| Protocol                                    | Status                             | Description                                                                                                                    | Overhead                |
| ------------------------------------------- | ---------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ | ----------------------- |
| **[Fink](https://github.com/lwproto/fink)** | Spec ready; Python MVP in progress | Ultra-light discrete protocol for short commands, statuses, and telemetry. See the Fink repository for the full specification. | **4 bytes**             |
| **Mink**                                    | In development                     | Streaming protocol with multiplexing, packet reordering, and CRC-8. Designed for logs and continuous data.                     | **6 bytes** *(planned)* |
| **Tork**                                    | In development                     | Transactional protocol with guaranteed delivery and atomicity. Designed for critical commands in unstable networks.            | *planned*               |

## Why lwproto?

Many mainstream protocols are optimised for general-purpose networking, servers, or high-throughput environments. That is useful in the right context, but it can be excessive for small embedded systems and narrow links.

lwproto takes the opposite approach:

* each protocol solves **one specific task**
* the footprint stays **small and predictable**
* the design avoids unnecessary dependencies
* the stack remains usable across very different devices and transports

The result is a set of protocols that are easier to implement, easier to audit, and more practical in constrained environments.

## Roadmap

### Mink

**Mink** will be the streaming layer of the stack.

It is planned as a **streaming protocol with multiplexing**, packet reordering correction, and basic integrity checking using **CRC-8**.

**Typical use cases:**

* logs
* telemetry streams
* continuous sensor data
* data channels over low-throughput or unstable links

### Tork

**Tork** will be the transactional layer of the stack.

It is planned as a **transactional protocol** with delivery guarantees and atomicity for critical operations.

**Typical use cases:**

* actuator commands
* configuration transactions
* control messages that must not be partially applied
* failure-sensitive embedded workflows

## Project links

* **Organisation:** [lwproto on GitHub](https://github.com/lwproto)
* **Fink repository:** [lwproto/fink](https://github.com/lwproto/fink)

## Contributing

lwproto is currently maintained by a single developer, but contributions, issues, and pull requests are welcome.

* embedded developers
* IoT engineers
* protocol designers
* open-source contributors
* students exploring low-level networking

Helpful contributions include:

* spec review
* edge-case analysis
* test vectors
* reference implementations
* documentation improvements
* real-world deployment feedback

If something feels unclear, inefficient, or overcomplicated, that is exactly the kind of feedback this project values.

## License

The project is licensed under [Apache-2.0](LICENSE).
