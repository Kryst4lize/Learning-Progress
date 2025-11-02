ETL Fundamentals Overview
Keyword: [[Apache Spark]], [[HDFS]]
- **ETL Definition**: ETL stands for **Extract, Transform, Load**. It is an automated data pipeline engineering methodology used to acquire and prepare data for analytics environments, such as data warehouses or data marts.

Key Components of ETL

1. **Extraction**: [[Data Collection]]
    
    - The process of obtaining or reading data from one or more sources.
    - Common methods include:
        - **Web Scraping**: Extracting data from web pages using programming languages like Python or R.
        - **APIs**: Programmatically connecting to data sources to query and retrieve data.
    - Data can be:
        - **Static**: Such as data archives, where extraction is part of a batch process.
        - **Dynamic**: Streaming live data from sources like weather stations, social media feeds, or IoT devices.
2. **Transformation**: [[Data Wrangling]]
    
    - Also known as data wrangling, this step involves processing data to conform to the requirements of the target system and intended use case.
    - Transformation processes can include:
        - **Cleaning**: Fixing errors or filling in missing values.
        - **Filtering**: Selecting only the necessary data.
        - **Joining**: Merging related data from disparate sources.
        - **Feature Engineering**: Creating key performance indicators (KPIs) for dashboards or machine learning models.
        - **Formatting and Data Typing**: Ensuring data compatibility with its destination.
3. **Loading**: [[Data Loading]]
    - This step involves writing the transformed data to a new destination environment.
    - Typical destinations include databases, data warehouses, and data marts.
    - The goal is to make the data readily available for analytics applications, enabling users to gain insights through dashboards, reports, and advanced analytics.

Use Cases for ETL Processes

- **Digitizing Analog Data**: Converting paper documents, photos, and analog audio/video into digital formats through extraction, transformation, and storage.
- **Historical Data Capture**: ETL processes capture transaction history from online transaction processing (OLTP) systems for analysis in online analytical processing (OLAP) systems.
- **Feature Engineering**: Preparing data for dashboards used by various stakeholders, including operations, sales, marketing, and executives.
- **Machine Learning**: Training and deploying models for prediction and decision-making.
---
# ELT Or ETL ?
Stages of the ELT Process
1. **Extraction**:
    - Data is gathered from various sources, which can include databases, APIs, and other data repositories.
    - The extraction is often done asynchronously, allowing for efficient data retrieval without waiting for each source to respond.
2. **Loading**:
    - The extracted raw data is loaded directly into a target environment, typically a data lake or a cloud-based analytics platform.
    - This step involves minimal processing, ensuring that the data remains in its original form.
3. **Transformation**:
    - Transformation occurs after the data has been loaded into the destination environment.
    - Modern analytics tools enable users to perform on-demand transformations, allowing for interactive exploration, visualization, and advanced analytics (e.g., modeling and prediction).
    - This dynamic transformation process is more flexible compared to traditional ETL methods.

Use Cases for ELT
- ELT is particularly beneficial in scenarios involving:
    - **High-Performance Computing**: Handling large volumes of data efficiently.
    - **Big Data**: Managing the massive swings in data scale that come with big data products.
    - **Real-Time Analytics**: Performing calculations on streaming data as it arrives.
    - **Distributed Data Sources**: Integrating data from various global locations seamlessly.

Advantages of ELT

- **Speed**:
    - Moving data is often a bottleneck; ELT minimizes this by reducing the amount of data movement required.
    - By loading data directly into the analytics platform, users can access and analyze data more quickly.
- **Flexibility**:
    - ELT allows for a clean separation between data movement and processing, enabling users to build a suite of data products from the same data sources.
    - Users can transform data in various ways without the risk of losing information, as they work with a replica of the source data.
- **Cost Efficiency**:
    - Cloud computing resources can scale on demand, meaning organizations only pay for what they use.
    - This eliminates concerns about underutilizing resources and overspending on hardware.

Why is ELT Emerging?

- The evolution of cloud computing solutions is a significant factor in the rise of ELT.
- Cloud platforms can handle vast amounts of asynchronous data and are designed to scale efficiently.
- The flexibility of ELT makes it suitable for a variety of applications, allowing organizations to adapt to changing data needs without losing valuable information.

| **Key Differences:**      | **ETL**                                                                                                                              | **ELT**                                                                                                                       |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------- |
| **Transformation Order:** | Transformations occur before the data reaches its destination.                                                                       | Transformations are decoupled from the data pipeline and happen in the destination environment.                               |
| **Flexibility:**          | Generally a fixed process designed for specific functions.                                                                           | More flexible, allowing for self-service analytics and enabling end users to connect to and experiment with raw data.         |
| **Big Data Handling:**    | Traditionally handles structured relational data and can face scalability issues due to reliance on on-premises computing resources. | Capable of managing both structured and unstructured data, utilizing cloud-computing services for on-demand scalability.      |
| **Time-to-Insight:**      | Modifications require time and effort, often needing input from the development team.                                                |  Provides agility, allowing end users to create dashboards and run predictive models without waiting for development changes. |

---
# ETL Technique

ETL stands for Extract, Transform, and Load, and refers to the process of curating data from multiple sources, conforming it to a unified data format or structure, and loading the transformed data into its new environment. 

![[ETL example.png]]

_Fig. 1. ETL is an acronym used to describe the main processes behind a data pipeline design methodology that stands for Extract-Transform-Load. Data is extracted from disparate sources to an intermediate staging area where it is integrated and prepared for loading into a destination such as a data warehouse._ 

# Extract 

Data extraction is the first stage of the ETL process, where data is acquired from various source systems. The data may be completely raw, such as sensor data from IoT devices, or perhaps it is unstructured data from scanned medical documents or company emails. It may be streaming data coming from a social media network or near real-time stock market buy/sell transactions, or it may come from existing enterprise databases and data warehouses.

# Transform 

The transformation stage is where rules and processes are applied to the data to prepare it for loading into the target system. This is normally done in an intermediate working environment called a “staging area.” Here, the data are cleaned to ensure reliability and conformed to ensure compatibility with the target system.  

Many other transformations may be applied, including:  

- Cleaning: fixing any errors or missing values  
    
- Filtering: selecting only what is needed  
    
- Joining: merging disparate data sources  
    
- Normalizing: converting data to common units  
    
- Data Structuring: converting one data format to another, such as JSON, XML, or CSV to database tables 
    
- Feature Engineering: creating KPIs for dashboards or machine learning   
    
- Anonymizing and Encrypting: ensuring privacy and security 
    
- Sorting: ordering the data to improve search performance 
    
- Aggregating: summarizing granular data 
    

# Load 

The load phase is all about writing the transformed data to a target system. The system can be as simple as a comma-separated file, which is essentially just a table of data like an Excel spreadsheet. The target can also be a database, which may be part of a much more elaborate system, such as a data warehouse, a data mart, data lake, or some other unified, centralized data store forming the basis for analysis, modeling, and data-driven decision making by business analysts, managers, executives, data scientists, and users at all levels of the enterprise.

In most cases, as data is being loaded into a database, the constraints defined by its schema must be satisfied for the workflow to run successfully. The schema, a set of rules called integrity constraints, includes rules such as uniqueness, [referential integrity](https://en.wikipedia.org/wiki/Referential_integrity), and mandatory fields. Thus such requirements imposed on the loading phase help ensure overall data quality.

# ETL Workflows as Data Pipelines 

Generally, an ETL workflow is a well thought out process that is carefully engineered to meet technical and end-user requirements.  

Traditionally, the overall accuracy of the ETL workflow has been a more important requirement than speed, although efficiency is usually an important factor in minimizing resource costs. To boost efficiency, data is fed through a _data pipeline_ in smaller packets (see Figure 2). While one packet is being extracted, an earlier packet is being transformed, and another is being loaded. In this way, data can keep moving through the workflow without interruption. Any remaining bottlenecks within the pipeline can often be handled by parallelizing slower tasks.  

![[ETLDatapackettransfer.png]]
_Fig 2. Data packets being fed in sequence, or “piped” through the ETL data pipeline. Ideally, by the time the third packet is ingested, all three ETL processes are running simultaneously on different packets._ 

With conventional ETL pipelines, data is processed in _batches_, usually on a repeating schedule that ranges from hours to days apart. For example, records accumulating in an Online Transaction Processing System (OLTP) can be moved as a daily batch process to one or more Online Analytics Processing (OLAP) systems where subsequent analysis of large volumes of historical data is carried out. 

Batch processing intervals need not be periodic and can be triggered by events, such as  

- when the source data reaches a certain size, or  
    
- when an event of interest occurs and is detected by a system, such as an intruder alert, or  
    
- on-demand, with web apps such as music or video streaming services 
    

# Staging Areas 

ETL pipelines are frequently used to integrate data from disparate and usually siloed systems within the enterprise. These systems can be from different vendors, locations, and divisions of the company, which can add significant operational complexity. As an example, (see Figure 3) a cost accounting OLAP system might retrieve data from distinct OLTP systems utilized by the separate payroll, sales, and purchasing departments.

![[ETL_Pipeline.png]]

_Fig 3. An ETL data integration pipeline concept for a Cost Accounting OLAP, fed by disparate OLTP systems within the enterprise. The staging area is used in this example to manage change detection of new or modified data from the source systems, data updates, and any transformations required to conform and integrate the data prior to loading to the OLAP._ 

# ETL Workflows as DAGs 

ETL workflows can involve considerable complexity. By breaking down the details of the workflow into individual tasks and dependencies between those tasks, one can gain better control over that complexity. Workflow orchestration tools such as Apache Airflow do just that.

Airflow represents your workflow as a directed acyclic graph (DAG). A simple example of an Airflow DAG is illustrated in Figure 4. Airflow tasks can be expressed using predefined templates, called operators. Popular operators include Bash operators, for running Bash code, and Python operators for running Python code, which makes them extremely versatile for deploying ETL pipelines and many other kinds of workflows into production. 

![[ETL_workflow.png]]

_Fig 4. An Apache Airflow DAG representing a workflow. The green boxes represent individual tasks, while the arrows show dependencies between tasks. The three tasks on the left, ‘runme_j’ are jobs that run simultaneously along with the ‘also_run_this’ task. Once the ‘runme_j’ tasks complete, the ‘run_after_loop’ task starts. Finally, ‘run_this_last’ engages once all tasks have finished successfully._ 

# Popular ETL tools 

There are many ETL tools available today. Modern enterprise grade ETL tools will typically include the following features: 

- Automation: Fully automated pipelines 
- Ease of use: ETL rule recommendations 
- Drag-and-drop interface: “o-code” rules and data flows 
- Transformation support: Assistance with complex calculations 
- Security and Compliance: Data encryption and HIPAA, GDPR compliance 

Some well-known ETL tools are listed below, along with some of their key features. Both commercial and open-source tools are included in the list. 

- **Talend Open Studio**
	- Supports big data, data warehousing, and profiling
	- Includes collaboration, monitoring, and scheduling
	- Drag-and-drop GUI for ETL pipeline creation
	- Automatically generates Java code
	- Integrates with many data warehouses
	- Open-source

- **AWS Glue**
	- ETL service that simplifies data prep for analytics
	- Suggests schemas for storing your data
	- Create ETL jobs from the AWS Console

- **IBM InfoSphere DataStage**
	- A data integration tool for designing, developing, and running ETL and ELT jobs
	- The data integration component of IBM InfoSphere Information Server
	- Drag-and-drop graphical interface
	- Uses parallel processing and enterprise connectivity in a highly scalable platform
- **Alteryx**
	- Self-service data analytics platform
	- Drag-and-drop accessibility to ETL tools
	- No SQL or coding required to create pipelines

- **Apache Airflow and Python**
	- Versatile “configuration” as code data pipeline platform
	- Open-sourced by Airbnb
	- Programmatically author, schedule, and monitor workflows
	- Scales to Big Data
	- Integrates with cloud platforms
- **The Pandas Python library**
	- Versatile and popular open-source programming tool
	- Based on data frames – table-like structures
	- Great for ETL, data exploration, and prototyping
	- Doesn’t readily scale to Big Data
---
# Apache Spark for ETL
- **Apache Spark Integration**:
[[Apache Spark]]
    - Spark integrates seamlessly with the Big Data Ecosystem, supporting native HDFS and various file formats like Parquet.
    - It allows for easy data cleaning and transformation using the Spark SQL framework and can handle both small and large ETL workloads efficiently.
- **Data Sources**: Spark supports extraction from various data sources, including:
    
    - HDFS data extraction from formats like Parquet, Apache ORC, and Hive.
    - An extendable data source API for custom sources.
- **Example Workflow**:
    
    - An example ETL workflow is provided where a Parquet file is extracted to create a DataFrame, additional information is extracted from a database, and the data is cleaned and transformed before being loaded into a data warehouse.