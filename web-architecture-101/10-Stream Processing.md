# Stream Processing

- To manage and gather the massive amount of streaming data
- What for?
  - to understand the user’s needs & their behaviour.
  - to track issue or service efficiency
- [Netflix real time stream processing](https://medium.com/netflix-techblog/keystone-real-time-stream-processing-platform-a3ee651812a)
- [Netflix migrating stream processing](https://www.infoq.com/articles/netflix-migrating-stream-processing/)

## Data Ingestion

- the process of collecting data streaming-in from several different sources and making it ready to be processed by the system
- Two primary ways to ingest data:
  - Real-time (we need information as soon as we can get.)
  - Batches (systems that read trends over time)
- Challenges:
  - Slow Process
  - Complex & Expensive
  - Moving Data Around Is Risky

### Use Cases

- Moving Big Data Into Hadoop
- Streaming Data from Databases to Elasticsearch Server
- Log Processing
- Stream Processing Engines for Real-Time Events

### Layers Of Data Processing Setup

- Data collection layer
- Data query layer
- Data processing layer
- Data visualization layer
- Data storage layer
- Data security layer

## Data Pipelines

- These ensure smooth flow of data.
- Enables the business to apply filters and business logic on streaming data.
- Avert any bottlenecks & redundancy in the data flow.
- Facilitate parallel processing of data.
- Avoid data being corrupted.

### ETL (Extract Transform Load)

- Extract means fetching data from single or multiple data sources.

- Transform means transforming the extracted heterogeneous data into a standardized format based on the rules set by the business.

- Load means moving the transformed data to a data warehouse or another data storage location for further processing of data.

## Distributed Data Processing

- diverging large amounts of data to several different nodes, running in a cluster, for parallel processing.
- working in conjunction with each other co-ordinated by a node-co-ordinator (Apache Zookeeper)
- helps accomplish the task in a significantly less amount of time
- Example:
  - Apache Hadoop
    - batch processing
    - managing distributed data processing across clusters
    - managing all the communication and data transfer
  - Spark
    - high performance for both batch & real-time in-stream processing
    - can work with diverse data sources & facilitates parallel execution of work in a cluster.
  - Storm
    - processing massive amounts of streaming data.
    - for real-time analytics, machine learning, distributed remote procedure calls
  - Kafka
    - distributed scalable pub/sub message queue
    - real time

## Lambda Architecture

- distributed data processing architecture that leverages both the batch & the real-time streaming data
- built to tackle the latency issues arising out of the batch processing approach
- Layers of Lambda:
  - Batch Layer (batch processing)
  - Speed Layer (real-time data)
  - Serving layer (combine both results)

## Kappa Architecture

- all the data flows through a single data streaming pipeline (opposite of Lambda)
- Kappa contains only two layers:
  - Speed, which is the streaming processing layer
  - Serving which is the final layer.
