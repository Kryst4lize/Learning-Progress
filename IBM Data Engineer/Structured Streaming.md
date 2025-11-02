[[Data Loading]]
- **Definition of Streaming Data**: Streaming data is continuously generated and often comes from multiple sources. It is characterized by the unavailability of complete datasets at any given time, as data is created incrementally.
    
- **Structured Streaming**: This is a component of Apache Spark that processes streaming data using Spark SQL. It utilizes the same DataFrame and Dataset APIs as batch processing.
    
- **Processing Methods**:
    
    - **Micro-batches**: Data is processed in small batches.
    - **Continuous Processing**: A more recent method that allows for real-time processing.
- **Key Terms**:
    
    - **Source**: The origin of the streaming data.
    - **Sink**: The destination where the processed data is output.
    - **Event Time**: The timestamp when a data point is created, distinct from arrival or processing time.
    - **End-to-End Latency**: The total time taken for data to move from source to sink.
    - **Watermarking**: A technique to handle late data, allowing for updates to results after initial processing.
- **Data Sources**: Spark Structured Streaming supports various data sources, including files, Kafka, IP sockets, and Rate sources.
    
- **Output Modes**:
    
    - **Append**: Only new rows are added.
    - **Complete**: The entire result table is rewritten.
    - **Update**: Only updated rows are modified, which is useful for managing late data.
- **Sinks**: Common sinks include:
    
    - **Foreach**: Applies a function to each record.
    - **ForeachBatch**: Applies a function to each batch.
    - **Console and Memory**: Primarily for debugging, not fault-tolerant.
- **Advanced Features**:
    - **External Listeners**: Monitors data streams and triggers events.
    - **Checkpointing**: Saves the progress of queries to recover from failures and allows writing streams to disk.