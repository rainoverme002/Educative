# Caching

- It ensures low latency and high throughput
- Store frequently accessed data in the RAM
- Caching can be:
  - dynamic (has expired time)
  - static (images/css)
- You can cache it in:
  - CDN
  - Redis/Memcache

## Caching strategies

- Cache Aside
  - most common caching strategy
  - lazy-loaded
  - Check the cache first, if empty will read from real DB

- Read through
  - cache always stays consistent with the database.

- Write-Through
  - before the data is written to the DB, the cache is updated with it
  - works well for write-heavy workloads

- Write-Back
  - directly written to the cache
  - after some delay as per the business logic writes data to the database.
