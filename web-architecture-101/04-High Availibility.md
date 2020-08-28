# High Availibility

- the ability of the system to stay online despite having failures at the infrastructural level in real-time
- improves the reliability of the system, ensures minimum downtime.
- To meet the high availability requirements systems are designed to be fault-tolerant, their components are made redundant

## Reasons For System Failures

[How Google make Japan Internet down](https://thenextweb.com/google/2017/08/28/google-japan-internet-blackout/)

- Software Crashes
- Hardware Failures, Overloaded CPU, RAM, hard disk failures, nodes going down. Network outages
- Human Errors, Flawed configurations & stuff
- Planned Downtime, Update or Maintenance

## Achieving High Availability - Fault Tolerance

- A fault-tolerant system is equipped to handle faults

```text
A very basic example of a system being fault-tolerant is a social networking application. In the case of backend node failures, a few services of the app such as image upload, post likes etc. may stop working. But the application as a whole will still be up. This approach is also technically known as Fail Soft.
```

- the entire massive service is architecturally broken down into smaller loosely coupled services called the micro-services.

There are many upsides of splitting a big monolith into several microservices, as it provides:

- Easier management
- Easier development
- Ease of adding new features
- Ease of maintenance
- High availability

## Redudancy

- Redundancy is duplicating the components or instances & keeping them on standby to take over in case the active instances go down. It’s the fail-safe, backup mechanism.
- Systems should be well monitored in real-time to detect any bottlenecks or single point of failures
- Automation enables the instances to self-recover without any human intervention

## Replication

- Replication means having a number of similar nodes running the workload together
- no standby or passive instances
- also known as the Active-Active High Availability mode

## High Availability Cluster

- High Availability cluster also known as the Fail-Over cluster
- The nodes in the cluster are connected by a private network called the Heartbeat network that continuously monitors the health and the status of each node in the cluster
