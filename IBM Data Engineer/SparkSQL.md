[[Python]], [[Resilient Distributed Datasets_(RDD)]], [[Apache Spark]]
- **SparkSQL**: A module in Spark for structured data processing, allowing interaction through SQL queries and the DataFrame API. It supports multiple programming languages, including Java, Scala, Python, and R. -> Querying structured and semi-structured data using SQL-like syntax. It integrates SQL queries with Spark's data processing capabilities.
## DataFrames
- A DataFrame is a collection of data organized into named columns, similar to a table in a relational database or a data frame in R/Python.
- Built on top of the Spark SQL RDD API, DataFrames utilize RDDs for relational queries.
- **Benefits of SparkSQL and DataFrames**:
    ![[SparkSQLExample.png]]
    ![[asff.png]]
    - **Scalability**: Handles data from small to large scales (kilobytes to petabytes).
    - **Data Format Support**: Works with various data formats and storage systems.
    - **Optimization**: Utilizes a Catalyst optimizer for performance improvements.
    - **Developer-Friendly**: Integrates well with big data tools and offers APIs for multiple languages.
## Datasets
- **Definition**: Datasets are a new data abstraction in Apache Spark, combining features of RDDs (Resilient Distributed Datasets) and DataFrames ([[SparkSQL#**DataFrames**]]). They consist of strongly typed JVM (Java Virtual Machine) objects, providing type safety during creation.
    
- **Key Features**:
    
    - **Immutability**: Datasets cannot be modified once created, similar to RDDs.
    - **Encoders**: They convert type-specified JVM objects into a tabular format.
    - **API Extension**: Datasets extend the DataFrame API, allowing for more structured data handling.
- **Advantages**:
    
    - **Compile-time Type Safety**: Errors can be detected before deployment, reducing costs and time.
    - **Performance**: Datasets compute faster than RDDs, especially for aggregate queries, and benefit from query optimizations via Catalyst and Tungsten.
    - **Memory Optimization**: Spark optimizes memory usage based on the dataset structure.
- **Creation Methods**:
    
    1. Using the `toDS` function from a sequence (Scala).
    ![[SparkSQL_create.png]]
    2. From a text file with an explicit schema.
    ![[SparkSQL_read_dataset.png]]
    1. From a JSON file using a custom class.
    ![[SparkSQL_create_dataset_JSON.png]]
- **Comparison with DataFrames**:
    ![[Dataframes_vs_Datasets.png]]
---
# Catalyst and Tungsten
**Spark SQL Memory Optimization using Catalyst and Tungsten**:

- **Goals of Spark SQL Optimization**: The primary aim is to enhance SQL query performance by reducing both time and memory consumption, which ultimately saves organizations resources.
    
- **Types of Optimization**:
    
    - **Rule-based Optimization**: Utilizes predefined rules to optimize SQL queries. Examples include validating indexed tables and ensuring only necessary columns are included in queries.
    - **Cost-based Optimization**: Measures the time and memory costs of different query paths and selects the one with the lowest cost.
- **Catalyst Optimizer**:
    
    - A built-in rule-based optimizer in Spark SQL, designed using Scala functional  programming constructs. 
    - Allows developers to extend optimization techniques by adding specific rules for different data sources.
    - Operates through four main phases: ([[Apache Spark#Optimization Technique in Query]])
        1. **Analysis**: Analyzes the query and creates a logical plan.
        2. **Logical Optimization**: Transforms the logical plan into an optimized logical plan by applying rules like folding and pruning.
        3. **Physical Planning**: Generates multiple physical plans based on the logical plan, selecting the one with the least cost.
        4. **Code Generation**: Produces Java bytecode to execute on each node.
    ![[Catalyst_process_optimization.png]]
- **Tungsten**:
    - Focuses on optimizing CPU performance rather than I/O, enhancing memory and CPU efficiency.
    - Manages memory explicitly, avoiding reliance on the JVM object model.
    - Implements cache-friendly data structures and optimizes data processing through techniques like loop unrolling and placing intermediate data in CPU registers.
---
#  User-Defined Schema (UDS) for DSL and SQL

**Estimated time needed:** 10 minutes

**How to Define and Enforce a User-Defined Schema in PySpark?**

In this reading, you will learn how to define and enforce a user-defined schema in PySpark.

Spark provides a structured data processing framework that can define and enforce schemas for various data sources, including CSV files. Let's look at the steps to define and use a user-defined schema for a CSV file in PySpark:

**Step 1:** Import the required libraries.
```python 
from pyspark.sql.types import StructType, IntegerType, FloatType, StringType, StructField
```

**Step 2:** Define the schema.
1. **Explore the data:** Understand the different data types present in each column.
2. **Column data types:** Determine the appropriate data types for each column based on your observed values.
3. **Define the schema:** Use the 'StructType' class in Spark and create a 'StructField' for each column, mentioning the column name, data type, and other properties.

```python
schema = StructType([
	StructField("Emp_Id", StringType(), False),
	StructField("Emp_Name", StringType(), False),
	StructField("Department", StringType(), False),
	StructField("Salary", IntegerType(), False),
	StructField("Phone", IntegerType(), True),
])
```
The schema defined above can be utilized for the below CSV file data:
**Filename: employee.csv**
```CSV
	emp_id,emp_name,dept,salary,phone
	A101,jhon,computer science,1000,+1 (701) 846 958
	A102,Peter,Electronics,2000,
	A103,Micheal,IT,2500,
```

**Step 3:** Read the input file with user-defined schema.
```python
	 #create a dataframe on top a csv file
	 df = (spark.read
	 .format("csv")
	 .schema(schema)
	 .option("header", "true")
	 .load("employee.csv")
	 )
	 # display the dataframe content
	 df.show()
```

**Step 4:** Use the `printSchema()` method in Spark to display the schema of a DataFrame and ensure that the schema is applied correctly to the data.
`df.printSchema()`
Through the preceding four steps, you've acquired the ability to establish a schema for a CSV file. Additionally, you've employed this user-defined schema (UDF) to read the CSV file, exhibit its contents, and showcase the schema itself.

---
# ETL in DataFrame
[[ETL]] 
- **Basic DataFrame Operations**: The main operations include **Reading**, **Analysis**, **Transformation**, **Loading**, and **Writing**.
    
    - **Reading**: Data is loaded into a DataFrame using Spark.
    ![[df_import.png]]
    - **Analysis**: Involves examining the dataset, including checking columns, data types, and row counts. You can use functions like `print schema`, `show`, and `select` to analyze the data.
    ![[df_printSchema.png]]
- ![[df_select.png]]
    - **Transformation**: This step focuses on filtering, sorting, and joining datasets to retain relevant data. Common techniques include filtering specific values, performing column operations, and aggregating data.
    ![[df_filter.png]]
- ![[df_groupby.png]]
    - **Loading and Writing**: After transformations, data can be exported to disk or loaded into databases.
- **ETL vs. ELT**:
    
    - **ETL (Extract, Transform, Load)**: Data is transformed before loading into a data warehouse.
    - **ELT (Extract, Load, Transform)**: Data is loaded into a data lake first, allowing for transformations as needed.
---
- **Table Views**:
    - **Temporary Views**: Exist only within the current Spark session and node.
    ![[df_tempView.png]]
    - **Global Temporary Views**: Shareable across different Spark sessions and exist within the general Spark application.
    ![[df_globalView.png]]
- **Creating Views**:
    
    - You can create a temporary view in Python using PySpark by first creating a DataFrame and then defining the view.
    - For a global temporary view, a minor syntax change is required.
- **Aggregation**:
    
    - A common process in Spark SQL used to present grouped statistics.
    - DataFrames come with built-in aggregation functions like count, average, and max.
    - Aggregation can be performed using DataFrame functions or SQL queries.
- **Data Sources Supported**:
    - **Parquet**: A columnar format for data processing.
    - **JSON**: Spark SQL can read and write JSON datasets while inferring the schema.
    - **Hive**: Spark SQL supports reading and writing data stored in Hive.