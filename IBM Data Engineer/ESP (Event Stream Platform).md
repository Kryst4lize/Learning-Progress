- **[[Events]] Streaming Platform (ESP)**:
    
    - Acts as a middle layer to manage event-based [[ETL]] processes.
    - Simplifies the interaction between event sources and destinations.
- **Main Components of an ESP**:
![[ESPcomponent.png]]
    - **Event Broker**: Core component that receives and processes events.
	    ![[brokercomponent.png]]
    - **Event Storage**: Stores events for later retrieval, allowing decoupling of sources and destinations.
    - **Analytic and Query Engine**: Used for querying and analyzing stored events.
- **Popular ESP Solutions**:
    - [[Apache Kafka]] (most popular)
    - Amazon Kinesis
    - Apache Flink
    - IBM Event Stream
    - Azure Event Hub