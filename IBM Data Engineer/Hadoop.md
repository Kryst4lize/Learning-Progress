[[Parallel and Scaling processing]]
-  **Definition and Purpose of Hadoop**:
    - Hadoop is an **open-source framework** designed for **processing large dataset**s. It addresses the challenges of handling **Big Data**, which can grow from gigabytes to terabytes and beyond.
- **Growth of Data**:
    
    - As businesses grow, their data needs increase significantly. For example, data can expand from 1 terabyte to 100 terabytes, necessitating more robust processing solutions.
- **Hadoop's Functionality**:
    
    - Hadoop is not a database but an **ecosystem** that allows for the **distributed processing** of data across clusters of computers. It can handle various types of data:
        - **Structured** (tabular data)
        - **Unstructured** (images, videos)
        - **Semi-structured** data.
- **Historical Context**:
    
    - The need for Hadoop arose in the late 1990s due to the rapid growth of the web and the complexity of data structures.
    - The **Apache Software Foundation** was established in 1999, leading to the development of the **Nutch web search engine** in 2002, which laid the groundwork for Hadoop.
- **Core Components of Hadoop**:
    - **Hadoop Common**: Essential utilities and libraries for other Hadoop modules.
    - **Hadoop Distributed File System (HDFS)**: Manages large datasets on commodity hardware.
    - **MapReduce**: A processing unit that splits data into smaller units for simultaneous processing.
    - **YARN (Yet Another Resource Negotiator)**: Manages resources for various processing tasks.
- **Drawbacks of Hadoop**:
    
    - Hadoop is not suitable for:
        - **Transaction processing** due to lack of random access.
        - Tasks that cannot be performed in parallel or have dependencies.
        - **Low latency** data access, which is crucial for real-time applications.
        - Processing many small files or intensive calculations with little data.
- **Solutions to Limitations**:
    
    - New tools like **Hive** and **Pig** were developed to enhance Hadoop's capabilities. Hive provides an SQL-like interface for querying, while Pig allows for multi-query processing to reduce data scans.
- **Conclusion**:
    - Hadoop is a powerful framework for Big Data processing, with core components that facilitate data storage and processing. However, its limitations have led to the development of additional tools to improve its functionality.
---
# MapReduce
- **Definition**: MapReduce is a programming pattern that enables massive scalability across many servers in a Hadoop cluster. It is a core component of Apache Hadoop and is used for distributed computing.
    
- **Components**:
    
    - **Map**: This task processes input data and converts it into key-value pairs. It extracts important information and produces a preliminary output.
    - **Reduce**: This task aggregates the key-value pairs produced by the Map task. It processes multiple outputs from the Map step to generate a final output.
- **Process**:
    
    1. **Mapping**: Input data is split into smaller files, and each file is processed to create key-value pairs.
    2. **Shuffling**: The Reducer sorts the key-value pairs and groups them by key.
    3. **Reducing**: The Reducer aggregates the values associated with each key to produce the final output.
    ![[MapReduceProcessData.png]]
- **Advantages**:
    
    - High level of parallelism allows for independent tasks to run simultaneously, saving time.
    - Flexibility to process both structured and unstructured data.
    - Supports various programming languages (Java, Python, C++, etc.).
- **Use Cases**:
    - Social media analytics (e.g., LinkedIn, Instagram).
    - Movie recommendations (e.g., Netflix).
    - Fraud detection in financial transactions.
    - User behavior analysis in advertising (e.g., Google Ads)
---
# Ecosystem
![[EcosystemHDFS.png]]
- **Stages of Big Data Processing**:
    1. **Ingest**: Data is collected from various sources using tools like:
        - **Flume**: Collects and transfers streaming data.
        - **Sqoop**: Transfers bulk data between relational databases and Hadoop.
    2. **Store**: Data is stored in HDFS and HBase.
    3. **Process and Analyze**: Data is processed using:
        - **Pig**: A procedural data flow language for analyzing large data sets.
        - **Hive**: A data warehouse software that provides an SQL-like interface for querying data.
    4. **Access**: Users access refined data using tools like:
        - **Impala**: Allows non-technical users to query data.
        - **Hue**: A web interface for managing and querying data in Hadoop.