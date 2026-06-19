---
source: sources/wiki-PublishE28093subscribe_pattern.md
source_url: https://en.wikipedia.org/wiki/Publish%E2%80%93subscribe_pattern
---

## Publish–Subscribe (Pub/Sub) Messaging Pattern

The publish–subscribe pattern is a messaging pattern in software architecture where message senders (publishers) categorize messages into topics and send them without knowledge of receivers, while message recipients (subscribers) express interest in specific topics without knowledge of publishers. This decoupling enables asynchronous, many-to-many communication and is a core component of message-oriented middleware systems.

## Key Concepts

- **Publishers** send messages categorized by topic/class without knowing who receives them
- **Subscribers** register interest in topics and receive only matching messages, without knowing publisher identity
- **Decoupling** — pub/sub provides the highest level of decoupling among architectural messaging patterns (compared to RPC, point-to-point, message queues)
- Three dimensions of decoupling: spatial (location), temporal (timing), and logical (identity)
- Pub/sub is a **sibling** of the message queue paradigm, not a replacement — many frameworks support both (JMS, Kafka, MQTT)
- Contrasted with **point-to-point** messaging where producers send directly to consumers
- Distinguished from the **Observer pattern** — pub/sub emphasizes distributed, broker-mediated, asynchronous communication; Observer is typically in-process and tightly coupled
- Can introduce **semantic/format coupling** between publishers and subscribers, leading to brittleness over time
- Earliest described system: the "news" subsystem of the **Isis Toolkit** (SOSP '87, 1987)

## Message Filtering

- **Topic-based filtering** — messages published to named channels; subscribers register for specific topics
- **Content-based filtering** — subscribers define constraints on message attributes; only matching messages delivered
- **Hybrid filtering** — combines topic-based categorization with content-based filtering within topics

## Topologies

- **Broker-based (centralized)** — a message broker/event bus receives from publishers and routes to subscribers; may perform store-and-forward, priority queuing, routing logic
- **Brokerless (decentralized)** — publishers and subscribers discover each other directly (e.g., DDS using IP multicast); requires overlay networks, often Small-World topologies
- **Subscription timing**: build time (hardcoded handlers), initialization time (XML config), runtime (dynamic add/remove)
- Kleinberg's result: efficient decentralized routing requires **Navigable Small-World topologies**

## Commands and Syntax

No specific CLI commands — pub/sub is a pattern, not a tool. Key implementations and protocols:

- **Apache Kafka** — distributed streaming platform supporting pub/sub and queues
- **MQTT** — lightweight messaging protocol for IoT, supports pub/sub
- **JMS (Java Message Service)** — Java API supporting both pub/sub and point-to-point
- **DDS (Data Distribution Service)** — brokerless middleware using IP multicast
- **RSS / Atom** — web syndication protocols implementing pub/sub at internet scale
- **WebSub** — web-native pub/sub implementation

## Relationships

- **Message Queue** — sibling pattern; queues deliver to one consumer, pub/sub delivers to all matching subscribers
- **Observer Pattern** — in-process predecessor; pub/sub evolved from observer to support distributed, asynchronous use cases
- **Message-Oriented Middleware (MOM)** — pub/sub is typically a component within MOM systems
- **Event-Driven Programming** — pub/sub is a primary mechanism for event distribution in event-driven architectures
- **Mediator Pattern** — the broker in pub/sub acts as a mediator between publishers and subscribers
- **Client-Server Model** — pub/sub contrasts with this tightly coupled paradigm; client-server fails when either party is offline
- **Producer-Consumer Problem** — related concurrency concern when pub/sub systems buffer messages
- Listed as an **Architectural Pattern** alongside MVC, MVP, MVVM, and others in the GoF/software design pattern taxonomy

## Exam-Relevant Points

- Pub/sub provides the **highest level of decoupling** among messaging patterns — higher than RPC or point-to-point
- Three filtering strategies: **topic-based, content-based, hybrid** — know the distinctions
- Pub/sub does **not guarantee message delivery** by default; assured delivery requires additional design (e.g., subscriber acknowledgment)
- **Scalability tradeoff**: scales well at small scale and at internet scale (RSS/Atom), but can face instabilities at enterprise data-center scale (load surges, slowdowns)
- **Security concerns**: brokers can be tricked into wrong delivery (amplification attacks); unauthorized publishers can inject damaging messages; encryption prevents eavesdropping but not authorized-sender abuse
- Redundant subscribers improve reliability **without additional architectural complexity** — a key advantage over client-server redundancy
- Pub/sub is distinct from Observer pattern: pub/sub is **distributed, asynchronous, broker-mediated**; Observer is **in-process, synchronous, direct reference**
- Reference text: Hohpe's *Enterprise Integration Patterns* (2003, Addison-Wesley)
