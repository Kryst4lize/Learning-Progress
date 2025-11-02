[[Distributed Database]] [[NoSQL]]
- **Definition and Overview**:
    - Apache Cassandra is an **open-source**, **distributed**, and **decentralized** database designed for high availability and scalability. It is **fault-tolerant** and offers tunable consistency.
- **History and Development**:
    - Originally created at Facebook, Cassandra is now widely used by major companies like **Netflix**, **Spotify**, and **Uber**.
- **Comparison with MongoDB**:
    
    - While both are NoSQL databases, Cassandra is optimized for **write-intensive** applications, whereas MongoDB is more suited for **read-specific** use cases.
    - Cassandra uses a **peer-to-peer architecture**, unlike MongoDB's primary-secondary architecture.
- **Key Features**:
    - **Always available** with tunable consistency.
    - **Fast write throughput** while maintaining performance for read operations.
    - **Linear scalability** without needing to restart or reconfigure.
    - Supports **multiple data centers**, making it ideal for global applications.
    - Uses a **SQL-like query language**.
- **Limitations**:
    - Cassandra does not support **joins**, has limited **aggregation support**, and lacks support for **transactions**. It should not be seen as a drop-in replacement for relational databases.
- **Best Use Cases**:
    - Ideal for applications that are **write-intensive** and require high availability, such as:
        - Recording transactions for e-commerce.
        - Storing user access information.
        - Time series data, like sensor updates.
- **Conclusion**:
    - Apache Cassandra is a powerful solution for applications needing fast data storage and retrieval, especially in scenarios with high traffic and geographical distribution.
---
# Architecture of Cassandra

Cassandra is a popular open-source distributed NoSQL database system known for its scalability, high performance, and fault tolerance. While it doesn't have a traditional architectural structure like a building, it does have a robust design that allows it to handle large amounts of data across multiple nodes. After reading this document, you will have a basic understanding of the components.

## Apache Cassandra topology

Cassandra is a distributed system architecture. The basic component of Cassandra's architecture is the standalone unit, node. It is also known as a single Cassandra. Nodes can be added or removed without affecting the system's availability. Each node operates independently and communicates with other nodes through a peer-to-peer protocol.

![Cassandra acrchitecture](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMSkillsNetwork-CS0101EN-Coursera/images/architecture_01.png)

As well as being a distributed system, Cassandra is designed to be a peer-to-peer architecture, with each node connected to all other nodes. Every Cassandra node can run all database operations and handle client requests independently, eliminating the need for a primary node.

![Database operations](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMSkillsNetwork-CS0101EN-Coursera/images/architecture_02.png)

How do the nodes in this peer-to-peer architecture know to which node to route a request without a primary node? What if a certain node is down or up? Through the gossip protocol.

The gossip protocol enables nodes to exchange details and information, updating each node about the status of all other nodes. A node performs gossip communications with up to three other nodes every second. The gossip messages follow a specific format and use version numbers to communicate efficiently. So, each node can build the entire metadata of the cluster (which nodes are up/down, what the tokens allocated to each node are, and so on).

### Components of a Cassandra node

Several components in Cassandra nodes are involved in the write and read operations. Some of them are listed next:

#### Memtable

Memtables serve as in-memory structures within Cassandra, buffering write operations before being written onto disk. Typically, each table has an active Memtable. Eventually, these Memtables are flushed to disk, transforming into immutable SSTables (Sorted String Tables).

The triggering of Memtable flushes can occur through various methods:

- Exceeding a predefined threshold for Memtable memory usage.
- Approaching the maximum size of the CommitLog, which prompts Memtable flushes to free up CommitLog segments.
- Setting specific time intervals to trigger flushes on a per-table basis.

These triggers initiate the process where the buffered data in Memtables is persisted onto disk as SSTables, ensuring data durability and efficient retrieval in the Cassandra database system.

#### Commit log

Commit logs in Cassandra function as append-only logs, capturing all local mutations on a specific Cassandra node. Before you write data to a Memtable, you must record it in a commit log. This process ensures durability in the event of an unexpected shutdown. Upon restarting, any mutations in the commit log are applied to the Memtables, guaranteeing data consistency and recovery in the Cassandra database system.

#### SSTables

SSTables (Sorted String Tables) are the immutable data files in Cassandra, storing data persistently on disk. These files are created by flushing memtables or streaming from other nodes. When you generate SSTables, Cassandra initiates the compaction processes to merge multiple SSTables into one. You should be able to see the new SSTable while the older SSTables become eligible for removal.

An SSTable comprises various distinct components stored in separate files, some of which include:  
**Data.db**: This file contains the actual data stored by Cassandra.  
**Index.db**: An index file that maps partition keys to specific positions within the Data.db file, aiding in efficient data retrieval.  
**Summary.db**: This file provides a sample subset (typically every 128th entry) of the information contained in the Index.db file, offering an overview for quicker data access.  
**Filter.db**: Cassandra employs a Bloom Filter in this file, which serves as a probabilistic data structure, assisting in determining if a partition key exists in the SSTable without requiring a disk seek.  
**CompressionInfo.db:** This file holds metadata regarding the offsets and lengths of compressed chunks within the Data.db file, facilitating the decompression of stored data.

These distinct files within an SSTable collectively form an organized structure that enables efficient data storage, indexing, retrieval, and compression within the Cassandra database system.

#### Write process at node level

Writes are distributed across nodes in the cluster, utilizing a coordinator node that manages the operation and replicates data to appropriate replicas based on the configured consistency level.

- Logging data in the commit log
- Writing data to the Memtable
- Flushing data from the Memtable
- Storing data on disk in SSTables

![write process](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMSkillsNetwork-CS0101EN-Coursera/images/commit.png)

#### Read at node level

While writes in Cassandra are very simple and fast operations done in memory, the read is a bit more complicated since it needs to consolidate data from memory (Memtable) and disk (SSTables). Since you can fragment data on disk into several SSTables, the reading process needs to identify which SSTables most likely contain info about the querying partitions. The Bloom Filter information makes this selection through the following steps:

1. Checks the Memtable
2. Checks Bloom filter
3. Checks partition key cache, if enabled
4. If the partition is not in the cache, the partition summary is checked
5. Then, the partition index is accessed
6. Locates the data on the disk
7. Fetches the data from the SSTable on disk
8. Data is consolidated from Memtable and SSTables before being sent to the coordinator  
![Bloom filter](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMSkillsNetwork-CS0101EN-Coursera/images/write.png)

  

#### Data distribution

**Partitioner**: Cassandra uses a partitioner to distribute data across nodes. This consistent hashing algorithm ensures an even data distribution across the cluster, preventing hotspots and facilitating horizontal scaling.

![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMSkillsNetwork-CS0101EN-Coursera/images/partition.png)

**Token Ring**: Cassandra employs a token ring mechanism, assigning a range of tokens to each node in the cluster. Each token corresponds to a particular data range, allowing nodes to locate and manage data efficiently.  
  

#### Data model

**Column family data model**: Cassandra follows a column-family-based data model, organizing data into rows and columns. It stores data in tables composed of rows indexed by a unique key. Each row contains columns with different attributes.

![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMSkillsNetwork-CS0101EN-Coursera/images/model.png)  
  

#### Replication and consistency

**Replication**: Data replication is configurable in Cassandra. Each piece of data is replicated across multiple nodes (replication factor) to ensure fault tolerance and high availability, even in node failures.

**Consistency levels**: Cassandra offers tunable consistency levels for read and write operations. Users can choose between different consistency levels, balancing consistency and performance based on application requirements.

#### Read and Write Operations

**Distributed writes**: Writes are distributed across nodes in the cluster, utilizing a coordinator node that manages the operation and replicates data to appropriate replicas based on the configured consistency level.

**Read optimization**: Cassandra supports efficient reads by allowing read operations from multiple replicas. It uses the "hinted handoff" mechanism to ensure consistency in case some replicas are temporarily unavailable.

#### Architecture Components

**Gossip protocol**: Cassandra uses the gossip protocol for inter-node communication. Nodes exchange information about the cluster's state, such as membership changes or node failures, ensuring each node stays updated.

**Compaction and compression**: Cassandra periodically performs compaction to merge and organize data files, optimizing storage and improving performance. It also supports data compression to reduce disk usage.

**Snitches and load balancing**: Snitches determine network topology, optimizing data replication and routing. Load balancing ensures that queries are evenly distributed across nodes to prevent uneven distribution.

#### Security

**Security features**: Cassandra offers security features like authentication, encryption, and access control mechanisms to ensure data integrity, confidentiality, and protection against unauthorized access.

## Summary

Cassandra's architecture is designed for high availability, fault tolerance, scalability, and efficient data management across distributed environments, making it a powerful choice for handling large-scale data-intensive applications.

---
# Features 
- **Distributed and Decentralized Architecture**:
    
    - **Distributed**: Cassandra clusters operate across multiple machines, appearing as a unified system to users and applications.
    - **Decentralized**: All nodes in a Cassandra cluster are identical, with no primary or secondary nodes. This is achieved through a peer-to-peer communication protocol called gossip.
![[cassandra_distributed_architecture.png]]
- **Data Distribution**:
    
    - Data is organized based on queries, particularly using a partition key. For example, if querying users by state, the state column is declared as the partition key.
    - Data is distributed in the cluster by hashing the partition key into tokens, with each node having a predefined list of token intervals.
- **Replication**:
    
    - Data replication occurs clockwise in the cluster, considering the placement of nodes in racks and data centers.
    - The replication factor determines how many nodes hold a copy of the data, enhancing data availability.
![[Cassandra_replication.png]]
- **Availability vs. Consistency**:
    
    - Cassandra is designed for high availability, meaning that even if part of the cluster fails, nodes can still respond to requests, albeit with potential data inconsistencies.
    - Developers can control the level of consistency (strong or eventual) at the operation level, with conflicts resolved during read operations.
- **Fault Tolerance**:
    
    - The decentralized nature of Cassandra contributes to its fault tolerance. If one node fails, users can connect to another node without service interruption.
- **Scalability**:
    
    - Clusters can be scaled by adding nodes, with performance increasing linearly. New nodes can start serving traffic immediately, and existing nodes redistribute responsibilities seamlessly.
- **High Write Throughput**:
    
    - Cassandra handles large volumes of writes by parallelizing write operations across all nodes holding replicas. Writes are performed in memory and then flushed to disk sequentially.
- **Cassandra Query Language (CQL)**:
    - CQL is used for data manipulation and is similar to SQL, making it easier for developers to transition. However, the execution of read and write operations differs from traditional relational databases.
---
# Cassandra Data Model 
- **Cassandra Data Model**: The video introduces the logical entities of the Cassandra data model, focusing on tables and keyspaces.
    
- **Keyspaces**: A keyspace is a logical entity that contains one or more tables and defines options like the replication strategy. It is recommended to use one keyspace per application.
    
- **Tables**: Tables are the primary structure for data storage in Cassandra, organized into rows and columns. You can create, drop, and alter tables without affecting ongoing data updates or queries.
    
- **Primary Keys**:
    
    - The primary key is a subset of the table's columns and must be defined when creating a table.
    - It serves two main roles: optimizing read performance and ensuring uniqueness of entries.
    - A primary key consists of a mandatory partition key and optional [[Apache Cassandra#Clustering Key]].
- **Partition Keys**:
    
    - The partition key determines data locality in the cluster and is hashed to decide which node will store the data.
    - Data is grouped by the partition key into partitions, which are the basic unit of storage in Cassandra.
- **Static and Dynamic Tables**:
    
    - **Static Tables**: Have a primary key that includes only the partition key, resulting in static partitions with one entry.
    - **Dynamic Tables**: Include both partition keys and clustering keys, allowing for multiple entries per partition.
- **Query Performance**: Efficient querying is crucial, especially in large clusters, as it limits the number of nodes contacted to retrieve data.
## Clustering Key
- **Clustering Key Characteristics**:
    
    - A clustering key can consist of a single or multiple columns.
    - In the example provided, the clustering key is the **username**, which means data is stored in ascending order by username within each partition.
- **Query Example**:
    
    - The video illustrates a query: "give me all users in group ID 12 that are aged 32."
    - A suggested data model for this query includes **group ID** as the partition key and **age** and **username** as clustering keys. This structure allows users of the same age to be grouped together within the same partition.
    ![[queryexample.png]]
- **Performance Optimization**:
    
    - By organizing data this way, the query can quickly locate the relevant partition and read only the necessary records, significantly reducing the amount of data processed and improving query performance, especially in large partitions.
- **Dynamic Tables**:
    
    - The video explains that in **dynamic tables**, partitions grow as new entries are added, thanks to the clustering key's role in the primary key.
    - It notes that replication is not considered in the example, meaning each partition is held by a single node until changes in the cluster occur.
    ![[Cassandra_dynamic_table_distribution.png]]
- **Primary Key Design Guidelines**:
    
    - When designing a primary key, consider:
        - Choosing a partition key that answers queries while distributing data evenly across the cluster.
        - Minimizing the number of partitions read to answer a query to enhance performance.
        - Building a clustering key that further reduces the data read by ordering columns according to query needs.
- **Conclusion**:
    - The video emphasizes that building a primary key to optimize query performance is just the beginning of the data modeling process in Cassandra. It highlights the importance of starting with the queries you want to answer when defining a Cassandra table.
---
# Cassandra Query Language (CQL)**

- **Introduction to CQL**:
    
    - CQL is the primary language for interacting with Apache Cassandra clusters.
    - It features a simple, [[Struct Query Language (SQL)]]-like syntax for various database operations such as creating keyspaces, tables, and executing queries.
![[CQL.png]]
- **Key Differences from SQL**:
    
    - CQL does not support **JOIN** statements; data must be stored in a way that avoids the need for joins.
    - Operations like inserts, updates, and deletes are performed directly in memory without prior reads.
- **Case Sensitivity**:
    
    - CQL keywords and identifiers are case-insensitive unless enclosed in double quotation marks.
    - For example, 'Select' and 'SELECT' are treated the same.
- **Running CQL Queries**:
    
    - Queries can be executed using:
        - A licensed Cassandra client driver (e.g., Java, Python, Scala).
        - The CQL Shell client (cqlsh), which is included with the Cassandra package.
- **CQL Shell (cqlsh)**:
    
    - A Python-based command line interface for executing CQL commands.
    - Connects to a single node by default or a specified node.
    - Key functionalities include:
        - Creating, altering, and dropping keyspaces and tables.
        - Inserting, updating, and deleting data.
        - Executing SELECT queries.
- **Command-Line Options for cqlsh**:
    
    - Common options include:
        - `help`: Displays help for cqlsh commands.
        - `version`: Shows the current version of cqlsh.
        - `user` and `password`: For authentication.
        - `keyspace`: Specifies the keyspace to authenticate to.
        - `file`: Executes commands from a specified file.
        - `request timeout`: Sets a timeout for queries (default is 10 seconds).
- **Special Commands in cqlsh**:
    
    - **CAPTURE**: Saves command output to a file.
    - **CONSISTENCY**: Sets or shows the current consistency level.
    - **COPY**: Imports or exports data to/from Cassandra.
    - **DESCRIBE**: Provides details about the current cluster and its objects.
    - **EXIT**: Ends the cqlsh session.
    - **PAGING**: Controls the paging of query results.
    - **TRACING**: Enables or disables request tracing.
- **Consistency in Cassandra**:
    
    - Cassandra allows tuning of consistency at the operation level.
    - Consistency refers to the number of nodes that must respond for an operation to be successful.
    - Options include:
        - ONE, TWO, THREE nodes.
        - QUORUM (majority of nodes).
        - ALL replicas.
        - LOCAL_QUORUM (majority from the local data center).
- **COPY Command**:
    - Used for bulk data operations:
        - **COPY TO**: Exports data from a table to a CSV file.
        - **COPY FROM**: Imports data from a CSV file into an existing table, ensuring all rows have the same number of fields.
---
# Data Types
1. **Overview of Data Types in CQL**:
    - CQL has various data types categorized into three main groups:
        - **Built-in Data Types**
        - **Collection Data Types**
        - **User-Defined Data Types (UDTs)**
2. **Built-in Data Types**:
    [[Data]]
    - These are pre-defined types in Cassandra, including:
        - **Ascii**
        - **Boolean**
        - **Decimal**
        - **Double**
        - **Float**
        - **Int**
        - **Text**
        - **Blob**: Used for storing binary large objects like images or audio, recommended size is up to 1 MB.
        - **Bigint**: A 64-bit signed long integer, offering a larger range than the int data type.
        - **Varchar**: Represents UTF8 encoded strings.
3. **Collection Data Types**:
    
    - Used to group and store data in a column, avoiding the need for joins (Not suitable for large scale data like real-time data like sensors ,...). Types include:
        - **Lists**: Maintains order and allows duplicate values (e.g., a log of entries).
        - **Maps**: Stores key-value pairs (e.g., journal entries with dates).
        - **Sets**: Stores unique elements in a sorted order (e.g., a list of email addresses).
4. **User-Defined Data Types (UDTs)**:
    
    - Allows users to create custom data types that can combine multiple fields. For example, an address can include apartment number, street, etc. UDTs can include any valid data type, including collections and other UDTs.
---
# Keyspaces Operator

- **Keyspaces in Apache Cassandra**:
    - A **keyspace** must be defined before creating tables, as there is no default keyspace.
    - A keyspace can contain multiple tables, but each table belongs to only one keyspace.
- **Replication**:
    
    - Replication is specified at the keyspace level.
    - The **replication factor** (number of data replicas) is set during keyspace creation but can be modified later.
    - The **replication strategy** determines how replicas are distributed across cluster nodes.
- **Creating a Keyspace**:
    
    - Example CQL command: `CREATE KEYSPACE intro_cassandra WITH REPLICATION = { 'class' : 'NetworkTopologyStrategy', 'datacenter1' : 3, 'datacenter2' : 2 }`.
    - This command creates a keyspace named `intro_cassandra` with a replication factor of 5 (3 replicas in datacenter1 and 2 in datacenter2).
- **Checking Keyspace Creation**:
    
    - Use `DESCRIBE KEYSPACES` or `DESCRIBE <keyspace_name>` to verify if a keyspace has been created.
- **Replication Factor and Strategy**:
    
    - The replication factor indicates how many copies of data are stored on different nodes.
    - All replicas in Cassandra are equally important; there are no primary or secondary replicas.
    - The replication factor should not exceed the number of nodes in the cluster.
- **Example of a Four-Node Cluster**:
    
    - In a four-node cluster with a replication factor of 3, data is replicated clockwise while considering rack placements.
    - For instance, if node 1 holds the initial data, the next replicas will be placed on nodes 3 and 4, ensuring they are in different racks.
    ![[CassandraExample1.png]]
- **Multi-Data Center Environment**:
    
    - In a setup with two data centers and a replication factor of 5, the process is similar.
    - After placing replicas in the first data center, the system moves to the second data center to place the remaining replicas.
	![[CassandraExample2.png]]
- **Modifying and Deleting a Keyspace**:
    
    - To modify a keyspace, use the `ALTER KEYSPACE` command (e.g., to change the replication factor).
    - To delete a keyspace, use the `DROP KEYSPACE` command, which removes all tables and data within that keyspace.
    - Cassandra takes a snapshot of the keyspace before dropping it, allowing for data recovery if needed.
    ![[AlterkeyspaceCassandra.png]]
---
# Table Operator
- **Cassandra Tables**: The video explains the role of tables in Cassandra, emphasizing that tables are created within a keyspace. A keyspace must exist before a table can be declared.
    
- **Table Creation Syntax**: The generic syntax for creating a table includes:
    
    - `CREATE TABLE IF NOT EXISTS keyspace_name.table_name (column_definitions);`
    - The `IF NOT EXISTS` clause prevents errors if the table already exists.
![[tablecreatecassandra.png]]
- **Column Definitions**: Columns are defined in parentheses after the table name, using a comma-separated list. The `PRIMARY KEY` parameter can be specified to indicate the primary key for the table.
    
- **Static vs. Dynamic Tables**:
    
    - **Static Table**: Contains a primary key with only one column (e.g., `username`).
	    ![[StatictableCassandra.png]]
    - **Dynamic Table**: Has a primary key composed of both a partition key (e.g., `groupid`) and a clustering key (e.g., `username`). The `STATIC` clause can be used for columns that share a single value across all partition rows.
	    ![[DynamictableCassandra.png]]
- **Data Selection**: After creating a table, a `SELECT` statement can be used, but it will return empty results if no data has been inserted.
- Data Properties and option
	`Using DESCRIBE command`
	![[DescribeCommandCassandra.png]]
	- **Table Properties**:
	    - Data is ordered by the clustering key by default.
	    - The `WITH CLUSTERING ORDER BY` parameter can change the order of data within a partition.
	    - The `default_time_to_live` parameter sets an expiration time for data, allowing for automatic deletion after a specified duration.
	- **Data Flushing**: Data is flushed from memory to disk under certain conditions:
	    - When the memtable is full.
	    - When the commit log is full.
	    - At specific intervals (default is 0, meaning not activated).
- **Altering Tables**: Tables can be altered to:
    
    - Add or drop regular columns.
    - Rename columns (not applicable to partition keys).
    - Change table properties.
    - Note that primary keys cannot be modified after table creation.
    ![[AltertableCassandra.png]]
- **Deleting Tables**: Tables can be deleted using:
    - `TRUNCATE`: Removes all data but retains the schema. Requires all replicas to be available.
    - `DROP`: Removes both data and schema. A snapshot of the data is taken before deletion.
    ![[DeletetableCassandra.png]]
---
# CRUD
1. **CRUD Definition**: CRUD stands for Create, Read, Update, and Delete, which are the four basic operations for managing data in databases.
    
2. **Write Process in Cassandra**:
    
    - When a write operation occurs, the node receiving the write acts as the **coordinator**.
    - The coordinator sends the write request to all replicas of the partition.
    - Acknowledgment is required from a minimum number of nodes specified for consistency to confirm the operation.
    ![[WriteProcessCassandra.png]]
1. **Example of Write Operation**:
    
    - In a keyspace with a replication factor of 3, if a write is sent to node 4 and node 2 is unavailable, the operation can still succeed if nodes 1 and 3 acknowledge the write.
4. **Node-Level Write Operations**:
    - Writes are stored in memory (Memtable) and later flushed to disk as SSTables.
    - Each write operation is timestamped for data reconciliation, where the most recent data prevails.
	![Bloom filter](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMSkillsNetwork-CS0101EN-Coursera/images/write.png)
1. **Insert Operations**:
    
    - Requires the full primary key to be specified.
    - Acts as both an insert and an update (upsert) since Cassandra does not read before writing.
    - Can include a Time-To-Live (TTL) to make data available only for a specified duration.
    ![[InsertOperatorCassandra.png]]
1. **Update Operations**:
    
    - Updates can be performed using only the partition key for static columns.
    - If an update is attempted on a non-existing entry, it behaves like an insert.
    ![[UpdateOperatorCassandra.png]]
1. **Lightweight Transactions**:
    
    - These transactions enforce a read-before-write mechanism using the `IF` clause in INSERT and UPDATE statements.
    - They are slower (**at least four times**) than normal operations and should be used sparingly.
    ![[Pasted image 20250122212726.png]]
Reading Data in Cassandra
- **Coordinator Node**: When a read operation is initiated, a node in the cluster acts as the coordinator. For example, node 4 is the coordinator in the provided scenario.
- **Consistency Setting**: Reads are sent to a number of replicas based on the consistency level. For instance, a consistency level of two means two out of three replicas will be contacted.
![[ReadOperatorCassandra.png]]
- **Select Operation**:
    - Always start with the **partition key** to limit the read to relevant replicas.
    - Follow the order of primary key fields for optimal performance.
    - Filtering the partition key and clustering keys is allowed, but selecting all data from a table is discouraged in production due to performance issues.
    ![[SelectOperatorCassandra.png]]

Deleting Data in Cassandra

- **Delete Operations**:
    - Can delete specific entries identified by the full primary key or at the partition level.
    - Deletes can also target a continuous range within a partition.
![[CreateIndexCassandra.png]]
- **Tombstones**:
    - When data is deleted, a special marker called a **tombstone** is written to indicate the deletion.
    - The actual data remains on disk for a configurable period (default is 10 days) before being permanently removed.
    - Tombstones ensure that deleted data is not visible in queries, but the data still exists until the grace period elapses.