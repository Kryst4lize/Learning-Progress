**Hadoop Distributed File System (HDFS)**: 
Keyword : [[Hadoop]] [[Hadoop#Ecosystem]]

- **Definition**: HDFS is a distributed file system that allows access to files across multiple servers. It is the storage layer of Hadoop, designed for handling large data sets.
    
- **File Handling**:
    
    - Files are split into smaller chunks called **blocks** (default sizes are 64 or 128 MB).
    - HDFS is optimized for **streaming data**, providing a constant bitrate for data transfer.
	![[SplitChunkHDFS.png]]
- **Key Features**:
    
    - **Cost Efficiency**: Utilizes commodity hardware, reducing storage costs.
    - **Scalability**: Can scale to hundreds of nodes, accommodating large data volumes (up to petabytes).
    - **Fault Tolerance**: Data is replicated across different machines to prevent loss in case of hardware failure.
    - **Portability**: Designed to easily move between platforms.
- **Node Types**:
    
    - **Name Node**: The primary node that manages file access and task assignments.
    - **Data Nodes**: Secondary nodes that store data and handle read/write requests.
    ![[NodeTypeHDFS.png]]
- **Rack Awareness**:
    
    - HDFS uses rack awareness to optimize data storage and retrieval, reducing network traffic and improving performance by keeping replicas in different racks.
- **Replication**:
    - Data blocks are replicated to ensure reliability. The **replication factor** determines how many copies of each block are created.
    Example : Replication with 2 replication_factor
    ![[ReplicationFactor.png]]
- **Read/Write Operations**:
    
    - HDFS follows a **write once, read many** model, meaning files cannot be edited after being written, but new data can be appended.
    - The read operation involves the client requesting data locations from the name node, while the write operation checks for file existence and permissions before proceeding.
    ![[ReadWriteHDFS.png]]
- **Architecture**:
    - HDFS operates on a primary/secondary node architecture, with one name node and multiple data nodes managing file operations.
    ![[ArchitectureHDFS.png]]