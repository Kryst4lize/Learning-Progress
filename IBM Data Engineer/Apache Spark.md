Keyword : [[Distributed Database]], [[Resilient Distributed Datasets_(RDD)]], [[Hadoop]], [[Python]]
# Overview
- **Definition of Spark**: Spark is a **distributed computing system** designed to process large-scale datasets efficiently. It addresses the limitations of the Hadoop MapReduce framework, which was often slow for certain data processing tasks.
    
- **Key Features of Spark**:
    - **In-Memory Processing**: Spark allows data to be cached in memory, significantly reducing the high I/O costs associated with traditional disk-based systems.
    - **Multi-Language Support**: It supports several programming languages, including **Java, Scala, Python, and R**, providing an easy-to-use API for developers.
    - **Integration with Data Sources**: Spark has built-in support for popular data sources like **Hadoop Distributed File System (HDFS), Cassandra, and Amazon S3**, facilitating the development process.
- **Tasks Performed by Data Engineers Using Spark**:
    - **Data Ingestion**: Data engineers intake large volumes of data from various sources, including HDFS, cloud storage, databases, and streaming sources like Apache Kafka.
    - **Data Transformation**: After ingestion, they clean, filter, and aggregate data using Spark's APIs, performing tasks like joining datasets and pivoting.
    - **Data Storage Strategies**: Engineers design efficient data storage solutions using Spark's distributed storage capabilities, handling large datasets across systems like HDFS and Amazon S3.
    - **Complex Data Processing**: They utilize Spark for tasks such as graph processing, stream processing, and machine learning, building data processing pipelines for real-time and batch processing.
    - **Performance Optimization**: Data engineers optimize Spark performance by tuning parameters like partitioning and memory usage, as well as monitoring the Spark cluster for efficiency.
- **Apache Spark Overview**:
    
    - **Open Source**: Apache Spark is an open-source, in-memory application framework designed for distributed data processing and iterative analysis on large datasets.
    - **In-Memory Processing**: Operations are performed within the memory (RAM), which enhances speed and efficiency.
- **Distributed Computing**:
    ![[Parallel_vs_Distributed.png]]
    - **Definition**: Involves multiple computers or processors working together. It is often confused with parallel computing, but they differ in memory access.
    - **Memory Access**: Parallel computing shares memory, while distributed computing allows each processor to access its own memory.
- **Benefits of Distributed Computing**:
    
    - **Scalability**: Distributed systems can easily scale by adding more machines to handle increased workloads.
    - **Fault Tolerance and Redundancy**: Independent nodes can fail without affecting the overall system, ensuring business continuity.
- **Comparison with MapReduce**:
- ![[MapReduce_vs_Spark1.png]]
    ![[MapReduce_vs_Spark2.png]]
    - Traditional MapReduce jobs involve time-consuming disk reads and writes. In contrast, Spark minimizes these operations by keeping data in-memory, significantly speeding up processing times.
- **Applications of Spark**:
    
    - **Data Engineering**: Tools like the core Spark engine, clusters, executors, SparkSQL, and DataFrames are utilized.
    - **Data Science and Machine Learning**: Libraries such as SparkML and Streaming support data science applications.
---
# Spark Cluster Manager
- **Overview of Spark Cluster Modes**: The video introduces different modes of running Apache Spark on a cluster, focusing on their components and benefits.
    
- **Spark Cluster Manager**:
    
    - It communicates with the cluster to acquire resources for applications.
    - Runs as a service outside the application, abstracting the cluster type.
    - The Spark Context creates tasks and communicates resource needs to the cluster manager, which reserves executor cores and memory.
- **Cluster Managers Supported by Spark**:
    
    1. **Standalone Cluster Manager**:
        ![[Apache_spark_cluster_start.png]]
        - Included with Spark installation, ideal for simple clusters.
        - Composed of Workers (running on cluster nodes) and a Master (managing the workers).
        - The Master connects workers and tracks them using heartbeat polling.
        - To set up, start the Master, then use its URL to start workers.
    2. **Apache Hadoop YARN**:
        ![[Apache_hadoop_yarn_start.png]]
        - A general-purpose cluster manager popular in the big data ecosystem.
        - Supports multiple frameworks, but has more complex setup requirements.
        - To run Spark on YARN, use the ‘--master’ option with the keyword YARN.
    3. **Apache Mesos**:
        
        - Another general-purpose cluster manager that allows dynamic partitioning.
        - May require additional setup depending on configuration needs.
    4. **Kubernetes**:
        - An open-source system for running containerized applications.
        - Provides portability and simplifies deployment.
        - Spark uses a built-in native Kubernetes scheduler.
- **Local Mode**:
    ![[Apache_spark_local_start.png]]
    - Runs Spark applications as a single process on the local machine.
    - Useful for testing or debugging without connecting to a cluster.
    - To run in local mode, use the ‘--master’ option with the keyword ‘local’ followed by the number of cores.
--- 
# Spark Submit
- **Unified Interface**:
    - The term "unified interface" means that switching from local mode to cluster mode requires changing only a single argument.
    ![[Spark_submit_syntax.png]]
    - The `spark-submit` script operates consistently across different programming languages, allowing for simultaneous execution of Python and Java applications.
- **Submission Process**:
    
    - The submission process involves:
        1. Parsing command line arguments.
        2. Reading additional configurations from the `spark-defaults` folder.
        3. Using the `--master` argument to specify how to connect to the cluster or run locally.
        4. Specifying application files (JARs or Python files) to start the driver program and distribute files.
        ![[Apache_spark_language_params.png]]
	- Submission Options:
		![[Spark_submit_flags.png]]
- **Managing Dependencies**:
    
    - For Java or Scala applications, creating an **uber-JAR** (a single JAR file with all dependencies) is recommended for portability.
    - For Python applications, ensure that:
        1. Cluster nodes access required dependencies with the same version.
        2. The same Python version is used.
    - Python dependencies can be included using the `--py-files` argument.
- **Using Spark Shell**:
    
    - Spark Shell is available for Scala and Python, providing access to Spark APIs for data manipulation.
    - It can be used in local or cluster mode, automatically initializing the SparkContext and SparkSession.
    - Users can start working with data immediately, and actions on DataFrames generate Spark jobs sent to the cluster.
- **Examples**:
    - Two examples of `spark-submit` are provided:
        1. Launching a Scala version of SparkPi with YARN as the master.
        2. Launching a Python version of SparkPi on a Spark Standalone cluster.
    ![[Spark_submit_example.png]]
---
# Configuration 
- **Configuration Types**: Apache Spark applications can be configured using three methods:
    
    - **Properties**: Adjust application behaviors.
    - **Environment Variables**: Set on a per-machine basis.
    - **Logging Configuration**: Controlled by log4j defaults.
- **Configuration Files**:
    
    - Located in the `conf` directory.
    - No preexisting files after installation, but templates are provided.
    - Templates contain sample configurations that can be enabled by uncommenting.
- **Setting Properties**:
	    ![[Spark_configuration.png]]

- **Precedence Order**:
    
    - Programmatically set configurations take the highest precedence.
    - Followed by configurations provided with `spark-submit`.
    - Lastly, configurations in `spark-defaults.conf`.
    ![[Spark_configuration_priority.png]]
- **Static vs. Dynamic Configuration**:
    
    - **Static Configuration**: Hardcoded values in the application, used for properties unlikely to change (e.g., application name).
    - **Dynamic Configuration**: Values that can change based on the environment (e.g., master location, executor memory).
- **Environment Variables**: Loaded from `conf/spark-env.sh`, allowing for machine-specific configurations.
    
- **Logging Configuration**: Managed through `conf/log4j-properties`, where log levels and output destinations can be adjusted.

---

- **Apache Spark Components**: The architecture consists of three main components:
    
    - **Data Storage**: Datasets are loaded from compatible data sources into memory.
    - **High-Level Programming APIs**: Spark provides APIs in Scala, Python, and Java.
    - **Cluster Management Framework**: This framework manages distributed computing and can operate as a stand-alone server, Mesos, or YARN.
- **Spark Core**: Often referred to simply as "Spark," the Spark Core is the fault-tolerant base engine for large-scale data processing. It manages memory, schedules tasks, and contains APIs for defining [[Resilient Distributed Datasets_(RDD)]]. 
    
- **Spark Application Architecture**:
    ![[Apache_spark_architecture.png]]
    - Comprises a **driver program** and **executor programs** that run on worker nodes.
    - The driver splits jobs into tasks and communicates with executors, which perform the tasks and return results.
---
# Processing in Spark
- **Main Processes**:
    A Spark application consists of two main processes: the **driver program** and **executors**.
    - **Driver program** runs one process per application, which can be on a cluster node or a separate machine. It executes user code, creates work, and sends it to the cluster.
    - **Executors** run multiple threads to perform work concurrently and operate independently across the cluster.
    ![[Spark_component.png]]
- **Spark Context**:
    ![[Spark_context.png]]
    - The **Spark Context** is initiated when the application launches and must be created in the driver before creating DataFrames or RDDs. It manages the lifecycle of these data structures.
- **Jobs and Tasks**:
    
    - The driver creates work from user code, referred to as **Jobs**. The Spark Context divides these jobs into **tasks** that can be executed in parallel on the cluster.
    ![[Spark_job_and_tasks.png]]
    - **Tasks** operate on different data subsets called **Partitions**, allowing for parallel execution in the executors.
    ![[Spark_job_and_task2.png]]
- **Cluster Components**:
    
    - A **Spark Worker** is a node in the cluster that performs work, while a **Spark Executor** utilizes local resources (memory and compute cores) to run tasks.
    - Increasing the number of executors and available cores enhances the cluster's parallelism.
- **Stages and Shuffles**:
    
    - A **stage** represents a set of tasks that an executor can complete on the current data partition.
    - A **shuffle** occurs when tasks require data from other partitions, marking the boundary between stages. Shuffles are costly due to data serialization and I/O operations.
    ![[Spark_stage&Shuffle.png]]
- **Driver Modes**:
    
    - The driver program can run in **client mode** (outside the cluster) or **cluster mode** (on a worker node within the cluster). It must maintain communication with the cluster during execution.
    ![[Spark_driver_mode.png]]
---
# Optimization Technique in Query
When you're working with PySpark DataFrames for data processing, it's important to know about the two types of transformations: **narrow and wide**. 
- Narrow transformations in Spark work within partitions without shuffling data between them. They're applied locally to each partition, avoiding data exchange. 
- Wide transformations in Spark involve redistributing and shuffling data between partitions, often leading to more resource-intensive and complex operations.

![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-BD0225EN-SkillsNetwork/images/Picture1.png)

Within narrow transformations, data is transferred without executing data shuffling operations.

![](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-BD0225EN-SkillsNetwork/images/Picture2.png)

Wide transformations involve the shuffling of data across partitions.

**Examples of narrow transformations**

Narrow transformations can be compared to performing straightforward operations on distinct data sets. Consider having various types of data in separate containers. You can perform actions on each data container or shift data between containers independently without requiring interaction or transfer. Examples of narrow transformations include modifying individual pieces of data, selecting specific items, or combining two data containers.

1. **Map:** Applying a function to each element in the data set.
```python
from pyspark import SparkContext
sc = SparkContext("local", "MapExample")
data = [1, 2, 3, 4, 5]
rdd = sc.parallelize(data)
mapped_rdd = rdd.map(lambda x: x * 2)
mapped_rdd.collect() # Output: [2, 4, 6, 8, 10]
```
2. **Filter:** Selecting elements based on a specified condition.
```python
from pyspark import SparkContext
sc = SparkContext("local", "UnionExample")
rdd1 = sc.parallelize([1, 2, 3])
rdd2 = sc.parallelize([4, 5, 6])
union_rdd = rdd1.union(rdd2)
union_rdd.collect() # Output: [1, 2, 3, 4, 5, 6]
```


**3. Union:** Combining two data sets with the same schema.
```python
from pyspark import SparkContext
sc = SparkContext("local", "GroupByExample")
data = [("apple", 2), ("banana", 3), ("apple", 5), ("banana", 1)]
rdd = sc.parallelize(data)
grouped_rdd = rdd.groupBy(lambda x: x[0])
sum_rdd = grouped_rdd.mapValues(lambda values: sum([v[1] for v in values]))
sum_rdd.collect() # Output: [('apple', 7), ('banana', 4)]
```


**Examples of wide transformations**

Wide transformations can be compared to tasks accomplished with teamwork and where information is needed from different groups to conclude. Imagine you have a group of friends, each with a puzzle piece. In order to put the puzzle together, you might need to trade pieces between your friends to make everything fit. These kinds of tasks are a good example of wide transformation. Such tasks can be a little more complicated because everyone needs to collaborate and move pieces around.

3. **GroupBy:** Aggregating data based on a specific key.
```python
from pyspark import SparkContext
sc = SparkContext("local", "GroupByExample")`
data = [("apple", 2), ("banana", 3), ("apple", 5), ("banana", 1)]
rdd = sc.parallelize(data)
grouped_rdd = rdd.groupBy(lambda x: x[0])
sum_rdd = grouped_rdd.mapValues(lambda values: sum([v[1] for v in values]))
sum_rdd.collect() # Output: [('apple', 7), ('banana', 4)]
```
4. **Join:** Combining two data sets based on a common key.
```python
from pyspark import SparkContext
sc = SparkContext("local", "JoinExample")
rdd1 = sc.parallelize([("apple", 2), ("banana", 3)])
rdd2 = sc.parallelize([("apple", 5), ("banana", 1)])
joined_rdd = rdd1.join(rdd2)
joined_rdd.collect() # Output: [('apple', (2, 5)), ('banana', (3, 1))]
```

**3. Sort:** Rearranging data based on a specific criterion.
```python
from pyspark import SparkContext
sc = SparkContext("local", "SortExample")
data = [4, 2, 1, 3, 5]
rdd = sc.parallelize(data)
sorted_rdd = rdd.sortBy(lambda x: x, ascending=True)
sorted_rdd.collect() # Output: [1, 2, 3, 4, 5]
```

Wide transformations are similar to reshuffling and redistributing data between different groups. Imagine having data sets that you want to combine or organize in a new way. However, this task is not as straightforward as working with just one data set. You need to coordinate and move data between these sets, which involves more complexity. For example, merging two data sets based on a common attribute requires rearranging the data between them, making it a wide transformation in data engineering.

**PySpark DataFrame: Rule-based common transformations**

The DataFrame API in PySpark offers various transformations based on predefined rules. These transformations are designed to improve how queries are executed and boost overall performance. Let's take a look at some common rule-based transformations.
5. **Predicate pushdown:** Pushing filtering conditions closer to the data source before processing to minimize data movement.
6. **Constant folding:** Evaluating constant expressions during query compilation to reduce computation during runtime.
7. **Column pruning:** Eliminating unnecessary columns from the query plan to enhance processing efficiency.
8. **Join reordering:** Rearranging join operations to minimize the intermediate data size and enhance the join performance.
```python
9. `from pyspark.sql import SparkSession`
10. `from pyspark.sql.functions import col`

11. `# Create a Spark session`
12. `spark = SparkSession.builder.appName("RuleBasedTransformations").getOrCreate()`

13. `# Sample input data for DataFrame 1`
14. `data1 = [`
15.     `("Alice", 25, "F"),`
16.     `("Bob", 30, "M"),`
17.     `("Charlie", 22, "M"),`
18.     `("Diana", 28, "F")`
19. `]`

20. `# Sample input data for DataFrame 2`
21. `data2 = [`
22.     `("Alice", "New York"),`
23.     `("Bob", "San Francisco"),`
24.     `("Charlie", "Los Angeles"),`
25.     `("Eve", "Chicago")`
26. `]`

27. `# Create DataFrames`
28. `columns1 = ["name", "age", "gender"]`
29. `df1 = spark.createDataFrame(data1, columns1)`

30. `columns2 = ["name", "city"]`
31. `df2 = spark.createDataFrame(data2, columns2)`

32. `# Applying Predicate Pushdown (Filtering)`
33. `filtered_df = df1.filter(col("age") > 25)`

34. `# Applying Constant Folding`
35. `folded_df = filtered_df.select(col("name"), col("age") + 2)`

36. `# Applying Column Pruning`
37. `pruned_df = folded_df.select(col("name"))`

38. `# Join Reordering`
39. `reordered_join = df1.join(df2, on="name")`

40. `# Show the final results`
41. `print("Filtered DataFrame:")`
42. `filtered_df.show()`

43. `print("Folded DataFrame:")`
44. `folded_df.show()`

45. `print("Pruned DataFrame:")`
46. `pruned_df.show()`

47. `print("Reordered Join DataFrame:")`
48. `reordered_join.show()`

49. `# Stop the Spark session`
50. `spark.stop()````



**Optimization techniques used in Spark SQL**

51. **Predicate pushdown:** Apply a filter to DataFrame "df1" to only select rows where the "age" column is greater than 25.
    
52. **Constant folding:** Perform an arithmetic operation on the "age" column in the folded_df, adding a constant value of 2.
    
53. **Column pruning:** Select only the "name" column in the pruned_df, eliminating unnecessary columns from the query plan.
    
54. **Join reordering:** Perform a join between df1 and df2 on the "name" column, allowing Spark to potentially reorder the join for better performance.
    

**Cost-Based optimization techniques in Spark**

Spark employs cost-based optimization techniques to enhance the efficiency of query execution. These methods involve estimating and analyzing the costs associated with queries, leading to more informed decisions that result in improved performance.

55. **Adaptive query execution:** Dynamically adjusts the query plan during execution based on runtime statistics to optimize performance.
    
56. **Cost-based join reordering:** Optimizes join order based on estimated costs of different join paths.
    
57. **Broadcast hash join:** Optimizes small-table joins by broadcasting one table to all nodes, reducing data shuffling.
    
58. **Shuffle partitioning and memory management:** Efficiently manages data shuffling during operations like groupBy and aggregation and optimizes memory usage.
    

By utilizing these methods, Spark endeavors to deliver efficient and scalable data processing capabilities. It is essential to grasp the effective application of these transformations and optimizations to attain the best possible query performance and optimal utilization of system resources.

```python
59. `from pyspark.sql import SparkSession`
60. `from pyspark.sql.functions import col`

61. `# Create a Spark session`
62. `spark = SparkSession.builder.appName("CostBasedOptimization").getOrCreate()`

63. `# Sample input data for DataFrame 1`
64. `data1 = [`
65.     `("Alice", 25),`
66.     `("Bob", 30),`
67.     `("Charlie", 22),`
68.     `("Diana", 28)`
69. `]`

70. `# Sample input data for DataFrame 2`
71. `data2 = [`
72.     `("Alice", "New York"),`
73.     `("Bob", "San Francisco"),`
74.     `("Charlie", "Los Angeles"),`
75.     `("Eve", "Chicago")`
76. `]`

77. `# Create DataFrames`
78. `columns1 = ["name", "age"]`
79. `df1 = spark.createDataFrame(data1, columns1)`

80. `columns2 = ["name", "city"]`
81. `df2 = spark.createDataFrame(data2, columns2)`

82. `# Enable adaptive query execution`
83. `spark.conf.set("spark.sql.adaptive.enabled", "true")`

84. `# Applying Adaptive Query Execution (Runtime adaptive optimization)`
85. `optimized_join = df1.join(df2, on="name")`

86. `# Show the optimized join result`
87. `print("Optimized Join DataFrame:")`
88. `optimized_join.show()`

89. `# Stop the Spark session`
90. `spark.stop()`
```
---
# Interface CLI
- **Connecting to the UI**: When a Spark application runs, it creates a **SparkContext** which starts a web server for the application’s user interface. You can access this UI by entering the hostname of the driver followed by port **4040** in a web browser. The server remains active for the duration of the Spark application.
    
- **Tabs in the UI**:
    
    - **Jobs Tab**: Displays the application’s jobs and their statuses. It includes an event timeline showing when processes start and jobs are created. You can view job details, including duration, number of stages, and tasks.
    ![[Spark_CLI_Job_Tab.png]]
    - **Stages Tab**: Reports the state of tasks within a job, showing completed, active, or pending stages. You can click on stage IDs for detailed task information.
    ![[Spark_CLI_Stage_Tab.png]]
    - **Storage Tab**: Shows details about RDDs (Resilient Distributed Datasets) that have been cached or persisted to memory or disk.
    ![[Spark_CLI_Storage_Tab.png]]
    - **Environment Tab**: Provides information about environment variables and system properties for Spark and the JVM.
    ![[Spark_CLI_Environment_Tab.png]]
    - **Executors Tab**: Displays metrics on memory and disk usage for executors in use, along with logs for the executor processes.
    ![[Spark_CLI_Executor_Tab.png]]
    - **SQL Tab**: If the application runs SQL queries, this tab shows query details and metrics.
    ![[Spark_CLI_SQL_Tab.png]]
		- **Job Details**: The Jobs tab allows you to view specific job details, including stages, timing, and metrics related to input/output sizes and task success rates.
		- **Stage Details**: Clicking on a stage ID provides insights into the tasks within that stage, including metrics and the shuffle process.
---
# Workflow in Interface
- **Application Workflow**: The Spark application workflow consists of jobs created by the SparkContext in the driver program, tasks running in executors, and completed jobs transferring results back to the driver or writing to disk.
    
- **Spark Application UI**: The Spark Application UI centralizes critical information, allowing users to monitor application progress, identify failures, and analyze processing bottlenecks.
    ![[Apache_spark_workflow.png]]
- **Job and Stage Division**: Spark jobs are divided into stages, which are connected as a Directed Acyclic Graph (DAG). Tasks for the current stage are scheduled on the cluster, and if any task fails after several attempts, Spark marks the job as failed.
![[Apache_spark_CLI_Job_details.png]]
    
- **Example Workflow**:
    
    - A job is created and divided into stages.
    - Stage "0" has no dependencies, allowing tasks to run independently.
    - Stage "1" begins only after Stage "0" completes, especially if a shuffle is required.
    - Tasks can run independently within a stage, leading to different run times.
- **Monitoring Tasks**: The UI allows users to view task states, durations, and metrics, helping to locate failed tasks and analyze performance.
    ![[Apache_monitor_example.png]]
- **Event Logging**: To view the Application UI after the application stops, event logging must be enabled. This logs all events in the application workflow, allowing access through the Spark History server.
	![[Apache_event_logging.png]]
---
# Debugging in Spark
**Common Application Failures**:
- User code
	- Syntax, Serialization, Data validation, Error in other code location
	-> Report task's errors to driver program, then the application will be terminated
- Configuration and Application Dependency
	- Source file and Required data files
	- Application libraries must be available for all nodes of cluster
- Resource Allocation
	- CPU and memory must be available for task to run
	- Driver and executor need to spare amount of CPU and RAM to run
	- Resources will be acquired until the process completed
	- Be careful when you do not have enough Executor, it can create Task-starvation situation
- Network Communication
## Memory Resource
- **Memory Parameters**: When running a Spark application, both the driver and executor processes have an upper memory limit. This limit is crucial to prevent the application from using all available cluster memory, which can lead to performance issues.
    
- **Spark Memory Management**:
    
    - Executors use memory for processing and additional memory if caching is enabled. However, excessive caching can lead to out-of-memory errors.
    - The driver memory is responsible for loading data, broadcasting variables, and handling results. Large datasets can exceed the driver’s memory capacity, so it's advisable to filter data and use subsets when collecting to the driver.
- **Unified Memory Regions**:
    ![[Spark_memory_unified.png]]
    - Executor memory and storage memory share a unified region in the Java Heap Space. When no executor memory is used, storage can utilize all available memory. However, executor memory can evict storage memory if necessary, but only until total storage memory usage falls below a certain threshold.
- **Data Persistence**:
    
    - Caching data in Spark allows for storing intermediate calculations for reuse, which is essential for speeding up machine learning workloads that require multiple iterations over the same dataset.
    - The `cache()` method can be used to mark a DataFrame for caching in memory, which saves computational time by avoiding the need to regenerate data.
- **Setting Executor Memory**:
    ![[Spark_submit_setting.png]]
    - Memory for executors can be set in a properties file or specified during application submission to the cluster. It's important to ensure that the application has enough memory to run effectively without exhausting the executor's available memory.
- **Performance Considerations**:
    - Avoid assigning more resources than are available on the physical machine to prevent performance degradation. The default configuration uses all available memory minus 1 GiB for all available cores.
## Processor Resource
- **Processor Cores in Spark**: Apache Spark utilizes CPU cores as a resource assigned to both driver and executor processes. Executors can process tasks in parallel, limited by the number of cores assigned to the application.
    
- **Task Scheduling**: When Spark launches an application, it places tasks in a scheduling queue and assigns them to available executors. The default behavior is to maximize parallelism by scheduling tasks to executors with available cores.
    
- **Configuring Cores**:
    
    - You can configure the **number of cores for ONE EXECUTOR during application** submission using the argument `--executor-cores` followed by the desired number of cores. (Maximum core per executor)
    - Alternatively, you can specify the **total number of cores across the APPLICATION** with `--total-executor-cores`.
    
- **Worker Configuration**: When starting a worker in a Spark standalone cluster, you can specify the number of cores using the argument `--cores`. By default, Spark uses all available cores.
    ![[Spark_submit_standalone_cluster_start.png]]
- **Example Scenario**: In a scenario with one worker node and six cores:
    ![[Spark_submit_scenario_example.png]]
    - If the first application requests four cores, it will use them, leaving two cores available.
    - If a second application requests four cores while the first is running, it must wait until enough cores are free.
    - If the second application requests only two cores, it can start immediately but may take longer to finish.
- **Performance Considerations**: Maximizing Spark application performance requires careful tuning of both application workloads and cluster resources.