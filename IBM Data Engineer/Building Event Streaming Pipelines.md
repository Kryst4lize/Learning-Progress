- **[[Apache Kafka]] Overview**:
    - Kafka consists of brokers that receive, store, process, and distribute events.
    - Topics are used to organize data, similar to databases, where each topic can have multiple partitions for fault tolerance and throughput.
- **Kafka Components**:
    - **Brokers**: Dedicated servers that manage event storage and distribution.
    - **Topics**: Containers for events, organized into partitions.
    - **Producers**: Client applications that publish events to topics.
    - **Consumers**: Client applications that subscribe to topics and read events.
- **Event Publishing**:
    - Producers can publish events with or without keys, affecting how events are distributed across partitions.
    - The Kafka command-line interface (CLI) is used to manage topics and producers.
- **Event Consumption**:
    - Consumers read events in the order they are published and maintain an offset to track their reading position.
    - Consumers can reset their offset to read all events from the beginning.
Examples: 
![[StreamPipelineKafkaExample.png]]
---
## Topic CLI
Parameter explaination:
- --topic : the name of your created topic
- --create: create command
- --partitions: total part of topic
- --replication-factor: total copy of topic
- --list: list all the name of topics
- --describe: get topic details
- --delete: delete the topic
![[KafkaTopicCLI.png]]
## Producer CLI
![[KafkaProducerCLI.png]]
## Consumer CLI
![[KafkaConsumerCLI.png]]

---
# Streaming Process 
Kafka Streams API
- **Purpose**: The Kafka Streams API is a simple client library that helps data engineers process and analyze data stored in Kafka topics within event streaming pipelines.
- **Functionality**: It allows for the processing of data in real-time, ensuring that each record is processed only once and one at a time.

Stream Processing Applications

- **Definition**: Applications developed to process streams of data, which may include tasks like filtering, aggregating, and enhancing data.
- **Example Use Case**: A weather data processing application that filters out only extreme weather events from raw data.
![[StreamingKafka.png]]
### Stream Processing Topology

- **Concept**: The Kafka Streams API operates on a computational graph known as a stream processing topology.
- **Components**:
    - **Nodes**: Each node in the topology represents a stream processor that performs data transformations.
    - **Edges**: The edges of the graph represent the input and output streams between processors.
**Types of Processors**
1. **Source Processor**:
    - **Role**: Acts like a consumer, consuming streams from Kafka topics and forwarding them to downstream processors.
    - **Characteristics**: Has no upstream processors.
2. **Sink Processor**:
    - **Role**: Acts like a producer, publishing the processed streams to a Kafka topic.
    - **Characteristics**: Has no downstream processors.
![[KafkaProcessingTopology.png]]


Example of Weather Stream Processing

- **Initial Setup**:
    
    - A producer publishes raw weather data (in JSON format) to a topic called `raw_weather_topic`.
    - A consumer reads this raw data from the topic.
- **Ad Hoc Data Processor**:
    
    - Initially, a simple script or application processes the raw data to filter for extreme weather events (e.g., very high temperatures).
    - The processed data is then published to another topic called `processed_weather_topic`.
- **Using Kafka Streams API**:
    - Instead of developing a complex ad hoc processor, the Kafka Streams API can be integrated.
    - The topology would consist of:
        - A source processor that consumes data from `raw_weather_topic`.
        - A stream processor that filters the data based on high temperatures.
        - A sink processor that publishes the filtered data to `processed_weather_topic`.
![[KafkaStream.png]]