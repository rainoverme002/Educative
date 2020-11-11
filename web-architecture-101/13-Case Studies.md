# Case Studies

## A Web-based Mapping Service Like Google Maps

- Data type: [Spatial Data](https://en.wikipedia.org/wiki/Spatial_database)
- Database: a non-relational NoSQL one as the map data doesn’t contain many relationships
- Architecture: client-server architecture as we need control over the service
- Backend:  Java, since it is performant, and heavily used
- APIs: Direction API, Distance Matrix, Geocoding, Places, Roads, Elevation, Time zone, Custom search API
- Server-side rendering:
  - we can cache the rendered image for future requests
  - the entire map is broken down into tiles
- UI: OpenLayers with JS framework
- Real-time Features
  - need a persistent connection
  - [How Hotstar scale](https://www.8bitmen.com/how-hotstar-scaled-with-10-3-million-concurrent-users-an-architectural-insight/)

## A Baseball Game Ticket Booking Web Portal

- Database:
  - an online payment system needs transactions & strong consistency
  - a relational database like MySQL
- Handling Concurrency
  - Using Message Queue (FIFO), like Kafka
  - Database Lock: at one point in time only one transaction has access to a resource in the database
    - can be implemented only with a transactional ACID compliant database like MySQL
    - [Snapshot Isolation](https://en.wikipedia.org/wiki/Snapshot_isolation)
    - [Isolation Datbase System](https://en.wikipedia.org/wiki/Isolation_(database_systems))
- Caching:
  - any of the popular caches like Redis, Memcache or Hazelcast
  - cache the current price of the tickets
- Backend:
  - Java, Scala, Python, Go
- UI:
  - CRUD based app with AJAX call
  - any front end frameworks
