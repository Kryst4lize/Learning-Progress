[[Apache Cassandra]] [[MongoDB]] [[Distributed Database]] [[NoSQL]]
- **Introduction to CAP Theorem**: The CAP Theorem, also known as Brewer’s Theorem, was introduced by Professor Eric A. Brewer in 2000. It addresses the challenges faced by distributed systems, particularly in the context of databases.
    ![[CAPTheorem.png]]
- **Historical Context**: The theorem emerged during the development of big data architectures, such as Hadoop, which required databases to be distributed and always available. Traditional relational databases struggled with the new demands for availability in distributed systems.
    
- **Three Key Characteristics**:
    
    - **Consistency**: This refers to the requirement that all nodes in a distributed system see the same data at the same time. If a system is consistent, every read operation returns the most recent write for a given piece of data.
    - **Availability**: This means that every request to the system receives a response, whether it is a success or failure. The system remains operational and responsive.
    - **Partition Tolerance**: This characteristic indicates that the system continues to operate despite network failures or communication breakdowns between nodes. In distributed systems, partitions (communication breaks) are inevitable, making partition tolerance essential.
- **Trade-offs**: According to the CAP Theorem, a distributed system can only guarantee two out of the three characteristics at any given time. This means that if a system is consistent and available, it may not be able to tolerate partitions, and vice versa.
    
- **Real-World Implications**: In practice, partition tolerance is a necessity for distributed systems. For example, if a network partition occurs in a cluster of eight nodes, the system may split into two smaller clusters. Consistency between these clusters can only be achieved once communication is restored.
    
- **NoSQL Databases**: The CAP Theorem is particularly relevant for NoSQL databases, which are designed to handle scalability and flexibility. NoSQL systems can be classified based on their approach to the CAP characteristics:
    
    - **Consistent and Partition Tolerant (CP)**: Systems like MongoDB prioritize consistency.
    - **Available and Partition Tolerant (AP)**: Systems like Apache Cassandra prioritize availability.