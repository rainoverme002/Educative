# Scalability

- the ability of the application to handle & withstand increased workload without sacrificing the latency
- should scale well when subjected to a heavy traffic load & should maintain the latency of the system

## What is Latency

- Latency is the amount of time a system takes to respond to a user request

### Network Latency

- the amount of time that the network takes for sending a data packet from point A to point B
- To cut down the network latency, businesses use CDN & try to deploy their servers across the globe as close to the end-user as possible

### Application Latency

- the amount of time the application takes to process a user request 
- The first step is to run stress & load tests on the application & scan for the bottlenecks that slow down the system as a whole

## Types Of Scalability

### Vertical Scaling

- adding more power to your server (scaling up)
- simpler, but availability risk

### Horizontal Scaling

- adding more hardware to the existing hardware resource pool (scaling out
- provides us with the ability to dynamically scale in real-time as the traffic on our website increases & decreases)

#### Cloud Elasticity

- why cloud computing got so popular in the industry is the ability to scale up & down dynamically (cloud elasticity)
- server nodes on the backend also helps with the website staying alive online all the time (High Availability)

### Which Scalability Approach Is Right for Your App

- your app is a utility or a tool which is expected to receive minimal consistent traffic => A single server
- your app is a public-facing social app like a social network => high availability & horizontal scalability is important to you.

## How to fix primary Bottlenecks

- Use caching exhaustively throughout the application to speed up things significantly
- Load balancers are the gateway to our application. Using too many or too few of them impacts the latency of our application

### Database

- use of database partitioning, sharding, use multiple database servers to make the module efficient
- The database is just not the place to put business logic. Not only it makes the whole application tightly coupled

Pick the right database

- Need transactions & strong consistency? Pick a Relational Database
- If you can do without strong consistency rather need horizontal scalability on the fly pick a NoSQL database.

### Application Architecture

- A common architectural mistake is not using asynchronous processes & modules where ever required rather all the processes are scheduled sequentially
- These tasks should be forwarded to a messaging server as opposed to doing it all sequentially & making the user wait for everything.

### Code level

- Using unnecessary loops, nested loops.
- Writing tightly coupled code.
- Not paying attention to the Big-O complexity while writing the code. Be ready to do a lot of firefighting in production.

## Tuning performance

[performance analysis tool](https://en.wikipedia.org/wiki/List_of_performance_analysis_tools)

[Facebook to support global event](https://engineering.fb.com/production-engineering/how-production-engineers-support-global-events-on-facebook/)

[How Hotstar scaled](https://www.8bitmen.com/how-hotstar-scaled-with-10-3-million-concurrent-users-an-architectural-insight/)

- Profiling, the dynamic analysis of our code
- Caching, Cache wisely. Cache everywhere. Cache all the static content. Hit the database only when it is really required. Try to serve all the read requests from the cache. Use a write-through cache
- Use a CDN, reduces the latency of the application due to the proximity of the data from the requesting user
- Compress data, Use apt compression algorithms to compress data. As compressed data consumes less bandwidth, consequently, the download speed of the data on the client will be faster.
- Avoid unnecessary round trips between the client & server
- In the industry tech like Cadvisor, Prometheus and Grafana are pretty popular for tracking the system via web-based dashboards.
