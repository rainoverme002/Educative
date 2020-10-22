# Load Balancing

> Just for the record – Node, Server, Server Node, Instance, Machine they all mean the same thing & can be used interchangeably.

## How it work

- act as a single point of contact for all the client requests
- regularly perform health checks of the machines in the cluster and update it's list with the online machine

Before we go through, we need to know on how DNS work

### DNS (Domain Name System) Load Balancer

- It use Domain Resolver to forward your request to nameserver
- The nameserver will return the IP address
- It is usually managed by ISP (Internet service provider)
- Less expensive option

### Hardware vs Software LB

- Hardware
  - physical machine
  - top-notch performance
  - need maintenance & regular updates

- Software
  - cost-effective and offer more flexibility
  - continually perform health checks on the servers
  - Example: HAProxy

### Algorithm for traffic routing

- Round Robin & Weighted Round Robin
  - based on the server’s compute & traffic handling capacity weights
  - useful for different data centers with different compute capacities.

- Least connection
  - routed to the machine that has the least open connections
  - good for long opened connections (a gaming application)

- Random
  - randomly routed to the servers

- Hash
  - always be routed to the same server.
