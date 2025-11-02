[[Big data]]
1. **Big Data and Parallel Processing**:
    
    - Big Data requires parallel processing due to the massive volumes of data that exceed the capacity of a single computer.
    - **Linear Processing**: Involves executing instructions sequentially. It is inefficient for complex problems like Big Data, as errors require restarting the entire process.
    - **Parallel Processing**: Breaks down tasks into executable instructions that are distributed across multiple nodes, allowing simultaneous execution. This method is more efficient for handling large datasets.
    ![[Parallel_vs_Linear_bigdata.png]]
1. **Advantages of Parallel Processing**:
    
    - **Reduced Processing Times**: Processes Big Data significantly faster than linear processing.
    - **Lower Memory and Processing Requirements**: Tasks are executed on separate nodes, reducing overall resource needs.
    - **Flexibility**: Nodes can be added or removed as needed, optimizing infrastructure costs.
3. **Data Scaling**:
    
    - **Scaling Up**: Increasing the capacity of a single node, which can eventually become insufficient.
    - **Scaling Out (Horizontal Scaling)**: Adding more nodes to manage increased workloads, forming a computing cluster.
4. **Embarrassingly Parallel Calculations**:
    
    - These are tasks that can be easily divided and executed independently, such as processing chunks of a large dataset without interdependencies.
5. **Fault Tolerance**:
    
    - Refers to a system's ability to continue functioning despite component failures. In systems like Hadoop, data partitions are replicated across nodes, allowing recovery if one node fails.
6. **Key Takeaways**:
    - Parallel processing is essential for efficiently managing Big Data.
    - Understanding the differences between linear and parallel processing is crucial for optimizing data handling.
    - Fault tolerance is vital for maintaining system reliability in distributed computing environments.
---
# Tools 
[[Big data#Technology]]
- **Big Data Tooling Categories**: There are six main categories of tools in the Big Data ecosystem:
    
    - **Data Technologies**: Designed for analyzing and processing Big Data, handling both structured and unstructured data. Key technologies include Apache Hadoop, Apache HDFS, and Apache Spark.
    - **Analytics and Visualization**: Tools that uncover patterns and trends in data, providing visual representations through graphs and charts. Examples include Tableau, Palantir, and SAS.
    - **Business Intelligence (BI)**: Transforms raw data into actionable insights for business analysis. Notable BI tools are Cognos, Oracle, and PowerBI.
    - **Cloud Service Providers**: Offer infrastructure and support for data processing, including AWS, IBM, and GCP.
    - **NoSQL Databases**: Specifically designed for Big Data, these databases store data in documents rather than relational tables. Examples include MongoDB and Cassandra.
    - **Programming Tools**: Used for large-scale analytical tasks, including R, Python, and SQL.
- **Roles in the Big Data Life Cycle**: Each category plays a critical role in managing and processing Big Data, from data capture to analysis and visualization.