# More on Architecture

- Shared Nothing Architecture
  - eliminating all single points of failure.
  - Every module has its own memory, own disk.
  - if several modules in the system go down, the other modules online stay unaffected.
  - It also helps with the scalability and performance.

## Event Driven Architecture

- What Is Blocking?
  - The flow of execution is blocked waiting for a process to complete
  - Unless we add asynchronous behaviour to it by annotating it and moving the task to a separate thread
- What Is Non-Blocking?
  - the flow doesn’t wait for the first function, that is called, to return the response
  - Non-blocking architecture is also known as the Reactive or the Event-driven architecture
- What Are Events?
  - an event can be anything from:
    - a tweet to a click of a button,
    - an HTTP request,
    - an ingested message,
    - a change in the value of a variable etc
  - Events happening too often is called a stream of events
- References:
  - NodeJS is not fit for CPU intensive tasks. CPU intensive operations are operations that require a good amount of computational power
  - [Node JS Event Loop](https://nodejs.org/fa/docs/guides/event-loop-timers-and-nexttick/)
  - [Linkedin using Play for identifying user online status](https://www.8bitmen.com/linkedin-real-time-architecture-how-does-linkedin-identify-its-users-online/)

## Web Hooks

- WebHooks are more like call-backs. It’s like I will call you when new information is available. You carry on with your work.
- WebHooks enable communication between two services without a middleware. They have an event-based mechanism.
- Whenever the new information is available on the backend. The server fires an HTTP event to all the registered endpoints of the consumers, notifying them of the new update.
- Example: Browser notifications

## Hexagonal Architecture

- In theory, the architecture consists of three components:
  - Ports
  - Adapters
  - Domain
- The focus of it to make the components of the application:
  - independent
  - loosely coupled
  - easy to test.
- In real world case, it will consists of:
  - controller
  - service
  - object model

## Peer to Peer Architecture

- A network in which computers also known as nodes can communicate with each other without the need of a central server.
- Several nodes in the network taking part equally acting as both the client & the server
- A Seeder is a node which hosts the data on its system and provides bandwidth to upload the data to the network
- a Leecher is a node which downloads the data from the network
- A large file is transferred between the nodes by being divided into chunks of equal size in a non-sequential order.

### Type of P2P Networks

- Unstructured
  - nodes/peers keep connecting with each other randomly
  - there is no structure, no rule
  - Just simply connect & grow the network
  - To search the data is very resource-intensive (O(n) complexity)
  - Example: Gossip, Kazaa & Gnutella
- Structured
  - holds proper indexing of the nodes or the topology 
  - Example: BitTorrent
- Hybrid
  - cherry-picking the good stuff from all the models
  - Example: Tradepal, GitTorrent, Bitcoin, Twister

### Centralized vs Decentralized
  
- Centralized:
  - central server has access to all your messages
  - if the server is destroyed, your data too
- Decentralized:
  - Nobody has control over your data
  - Decentralized social networks ask you to Bring Your Own Data
  - Ensuring the Safety of Our Data
  - Economic Compensation to the parties involved in the network
  - Infrastructure Ease

## Federated architecture

- an extension to the decentralized architecture
- a group of semi-autonomous entities exchanging information with each other
- Example: Mastodon, Minds, Diaspora
