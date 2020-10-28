# Message Queue

- a queue which routes messages from the source to the destination
- following FIFO policy
- facilitate cross-module communication (allows communication in a heterogeneous environment
- enable us to run background processes, tasks, batch jobs)
- RabbitMQ, ActiveMQ, Apache Kafka etc

## Message queue models

- Publish-Subscribe Model
  - one to many relationship
  - Analogy: the consumers subscribe to a newspaper service and service delivers the news to the multiple consumers of its service, every single day.
  - [Rabbit MQ system](https://www.rabbitmq.com/tutorials/amqp-concepts.html)

- Point to Point Model
  - the message from the producer is consumed by only one consumer.
  - one to one relationship

## Real-World Use Case

- Social media platform has many entities with many relationship
- How to implement it?
  - Pull-Based Approach
    - simple, we only need to use db query to update new post in social media
    - But, we are polling the database so often, this is expensive
    - It will not real time
  - Push-Based Approach
    - it will have a distributed transaction. One will update the database, and the other transaction will send the post payload to the message queue
    - it will spike the performance of the application and cut down a lot of resource consumption

- [LinkedIn Real-Time Architecture: How Does LinkedIn Identify Its Users Online?](https://www.8bitmen.com/linkedin-real-time-architecture-how-does-linkedin-identify-its-users-online/)

### Handling Concurrent Requests With Message Queues

- In social media platform like facebook
- [Under the hood: Broadcasting live video to millions](https://engineering.fb.com/2015/12/03/ios/under-the-hood-broadcasting-live-video-to-millions/)

#### Case 1

```text
When millions of users around the world update an entity concurrently, we can queue all the update requests in a high throughput message queue. Then we can process them one by one in a FIFO First in First Out approach sequentially.
```

#### Case 2

```text
Facebook queues all the user requests, requesting for the same data. It fetches the data from the streaming server, populates the cache & then serves the queued requests from the cache.
```
