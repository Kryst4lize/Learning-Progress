- **Definition**: A **distributed database** is a collection of multiple interconnected databases that are spread across various physical locations and communicate via a computer network.
Keyword : [[Distributed Architecture]]
- **Data Fragmentation**:
    
    - To manage large data, it is fragmented or partitioned into smaller pieces. This process is also known as **sharding**.
    - Fragmentation can be done by:
        - Grouping keys lexically (e.g., all keys starting with A).
        - Grouping records with the same key on the same server (e.g., all transactions from a specific store).
- **Data Replication**:
    
    - Replication involves storing copies of data fragments in two or more locations to ensure data availability.
    - If one node fails, data can be retrieved from another node.
    - However, replication requires consistent synchronization across nodes to avoid data inconsistency.
- **Advantages of Distributed Databases**:
    
    - **Reliability and Availability**: Data is replicated, so if one server is down, data can still be accessed from another.
    - **Improved Performance**: Query processing time is reduced, especially for high volumes of data.
    - **Scalability**: New servers can be added to increase system capacity.
    - **Continuous Operation**: Reduces reliance on a central site.
- **Challenges**:
    - **Concurrency Control**: Managing simultaneous data modifications across multiple locations can lead to synchronization issues.
    - Limited support for transactions due to the nature of distributed systems.
    - Distributed databases follow the **BASE consistency model**, which allows for eventual consistency rather than immediate consistency.