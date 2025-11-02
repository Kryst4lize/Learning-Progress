[[HDFS]] [[Apache Cassandra]] [[Parallel and Scaling processing]] [[Distributed Database]]
- **Resilient Distributed Datasets (RDDs)**:
    
    - RDDs are Spark's primary data abstraction, representing a collection of fault-tolerant elements partitioned across a cluster.
    - They are **immutable**, meaning they cannot be changed once created.
    - RDDs can be created from:
        - External or local files from Hadoop-supported file systems (e.g., HDFS, Cassandra).
        - Existing collections using the **parallelize** function.
        - Transformations on existing RDDs to create new RDDs.
    - RDDs support various file types and databases, enabling flexible data handling.
	    ![[RDD_support_file.png]]
- **Parallel Programming**:
    
    - Involves using multiple compute resources simultaneously to solve computational tasks.
    - Tasks are divided into discrete parts, processed concurrently by multiple processors accessing a shared memory pool.
    - RDDs facilitate parallel programming by allowing distributed partitions to be processed in parallel.
- **Resilience in Spark**:
    - RDDs provide resilience through:
        - **Immutability**: Data is recoverable since it cannot be altered.
        - **Caching**: RDDs can be cached in memory, speeding up future operations significantly, especially for iterative algorithms.
---
# Characteristic 
- **Transformations and Actions**:
    
    - **Transformations**: These create a new RDD from an existing one. They are **lazy**, meaning they are not computed immediately but only when an action is called. An example is the **map transformation**, which applies a function to each element of the dataset.
    - **Actions**: These evaluate the transformations and return results to the driver program. An example is the **reduce action**, which aggregates all elements of an RDD.
- **Common Transformations and Actions**:
    1. **Transformations**:
        ![[RDD_transformation.png]]
    2. **Actions**:
        ![[RDD_Action.png]]
## **Directed Acyclic Graph (DAG)**:
- Spark uses a DAG to manage RDD operations. The DAG consists of vertices (representing RDDs) and edges (representing transformations or actions).
- The acyclic nature means that new edges originate only from existing vertices, ensuring a clear flow of operations.
- **Fault Tolerance**:
    - DAGs enable fault tolerance. If a node fails, Spark can replicate the DAG and restore the node, ensuring data integrity and continuity in processing.
- **Process Overview**:
    - When an RDD is created, a DAG is generated.
    - The DAG Scheduler performs transformations and updates the DAG to point to new RDDs.
    - Actions trigger the evaluation of the DAG, allowing the driver program to receive computed values.
