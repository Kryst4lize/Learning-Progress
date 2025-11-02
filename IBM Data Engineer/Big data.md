Big Data refers to the **vast amounts of data** that is being produced each moment of every day, by people, tools, and machines. The sheer velocity, volume, and variety of data challenged the tools and systems used for conventional data, leading to the emergence of processing tools and platforms designed specifically for Big Data. Big Data processing technologies help derive value from big data. These include NoSQL databases and Data Lakes and open-source technologies such as Apache Hadoop, Apache Hive, and Apache Spark.
[[NoSQL]] [[Datalake]] [[Open Source]]
**5V : Velocity, Volume, Veracity, Value and Variety**
**Tool **
- Hadoop provides distributed storage and processing of large datasets across clusters of computers. One of its main components, the Hadoop File Distribution System, or HDFS, is a storage system for big data.
    
- Hive is a data warehouse software for reading, writing, and managing large datasets.
    
- Spark is a general-purpose data processing engine designed to extract and process large volumes of data.
---
- **Definition**: Big Data is described as the digital trace generated in the digital era. It encompasses the vast amounts of data produced continuously through various digital interactions.

Comparison with Small Data

| **Small Data**                                                                                        | **Big Data**                                                                                         |
| ----------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------- |
| - Available in limited quantities.                                                                    | - Generated in massive volumes and often lacks structure.                                            |
| - Easily interpretable by humans with minimal digital processing.                                     | - Requires specialized programs for interpretation and analysis.                                     |
| - Examples include sports scores and employee shift schedules.                                        | - Examples include social media posts (semi-structured) and medical records (unstructured).          |
| - Typically structured, making it easier to store and manage within an organization’s infrastructure. | Grows exponentially over time and can be in various forms, including text, images, audio, and video. |

Big Data Life Cycle
![[BigDataLifeCyscle.png]]
1. **Collection**: Initiated by a business problem or requirement, leading to the gathering of relevant data.
2. **Storage**: Data is stored using distributed storage frameworks like Hadoop HDFS.
3. **Modeling**: Data is organized into models that define entities, relationships, and rules.
4. **Processing**: Tools such as Apache Spark are employed to analyze the modeled data and extract meaningful insights.
5. **Visualization**: The processed data is presented in graphical formats (charts, graphs) to facilitate decision-making.

Characteristics of Big Data

- **Volume**:
    - Refers to the vast amounts of data generated compared to traditional data sources.
    - Measured in petabytes, exabytes, and zettabytes, illustrating the scale of data storage.
- **Velocity**:
    - The speed at which data is generated and must be processed.
    - Attributes include batch processing (close to real-time) and streaming data.
    - Driven by improved connectivity and hardware capabilities.
- **Variety**:
    
    - The diversity of data types generated from various sources, including structured, semi-structured, and unstructured data.
    - Attributes include structure, complexity, and origin.
    - Drivers include mobile technologies and scalable hardware infrastructure.
- **Veracity**:
    - The quality and accuracy of the data collected.
    - Attributes include consistency, completeness, integrity, and ambiguity.
    - Driven by the need for traceability and robust data ingestion mechanisms.
- **Value**:
    - Represents the insights and benefits derived from effectively leveraging the previous four V's.
    - The ultimate goal is to create value through informed business decisions, efficient resource use, and the discovery of new market opportunities.

The Five V's of Big Data

1. **Velocity**: Speed of data generation and processing.
2. **Volume**: The sheer amount of data being generated.
3. **Variety**: The different forms and types of data.
4. **Veracity**: The trustworthiness and accuracy of the data.
5. **Value**: The insights and benefits gained from analyzing the data.

Scale of Big Data

- Big Data can reach sizes that exceed traditional measurements:
    - **Exabyte**: Can store over 11 million 4K resolution movies.
    - **Zettabyte**: Contains a billion terabytes.
    - **Yottabyte**: Fits one trillion terabytes.
---
# Impact
- **Definition and Importance of Big Data**: Big Data refers to the vast amounts of data generated globally, often without users being fully aware of it. This data includes personal information such as photos, videos, and text messages, which are crucial for consumer goods companies.
    
- **Examples of Big Data in Action**:
	- **Amazon**: Utilizes algorithms to recommend products based on user behavior, including past purchases, searches, and ratings.
	- **Virtual Assistants**: Tools like Siri and Alexa leverage Big Data to respond to user queries, using advanced neural networks to process speech and perform tasks.
	- **Google Now**: This service anticipates user needs by analyzing data from calendars and locations, providing timely information like traffic and weather.
	- **Impact on Businesses**: Big Data is transforming business operations and competition. Clive Humby referred to data as the "New Oil," highlighting its value. Companies increasingly rely on machine learning algorithms to make informed decisions, leading to a growing demand for data scientists and Big Data engineers.
## Example
- **Key Industries and Applications**:
    - **Retail**:
        - **Price Analytics**: Helps in market segmentation and identifying optimal price points.
        - **Sentiment Analysis**: Uses social media to gauge consumer opinions and inform marketing strategies.
    - **Insurance**:
        - **Fraud Analytics**: Identifies fraudulent claims and detects anomalies.
        - **Risk Assessments**: Uses predictive modeling to assess customer risk based on behavior.
    - **Telecommunications**:
        - **Network Security**: Machine learning identifies threats and enables predictive maintenance.
        - **Contextual Promotions**: Offers location-based promotions to enhance customer engagement.
    - **Manufacturing**:
        - **Predictive Maintenance**: Analyzes sensor data to predict equipment failures.
        - **Production Optimization**: Uses AI to recommend improvements in production processes.
    - **Automotive**:
        - **Service Predictions**: Anticipates breakdowns and schedules repairs based on sensor data.
        - **Self-Driving Technology**: Real-time data from connected cars informs driving adjustments.
    - **Finance**:
        - **Fraud Detection and Risk Assessment**: Similar to insurance, with additional focus on customer segmentation and algorithmic trading.
    
- **Internet of Things (IoT)**: IoT encompasses interconnected devices that collect and transmit data without manual input. These devices generate significant amounts of data, which is essential for their functionality. By 2030, it's projected that there will be four times more IoT devices than the global population.
    
- **IoT Ecosystem Components**:
    
    - **Data Collection**: Smart devices and sensors continuously produce data.
    - **Data Transmission**: Data is routed to cloud storage through gateways.
    - **Data Analysis**: Data engineers use algorithms to analyze this data, which informs business and consumer decisions.
- **Real-World Application**: For instance, a security camera can upload footage continuously, and a cloud-based algorithm can alert users to detected activity.
---
# Characteristic
- **Definition and Growth of Big Data**:
	    
    - Big Data refers to the vast amounts of data generated, with more data created in the last two years than in all of human history.
    - A projected **40% annual growth** in global data is expected, with digital data creation set to double by 2026.
- **Sources of Big Data**:
    
    - **Social Data**: Generated from social media interactions (likes, comments, shares).
    - **Machine-Generated Data**: Produced by IoT sensors and web logs. 
    - **Business-Generated Data**: Includes transactional data from daily operations (invoices, payment records).
- **Types of Big Data**:
    
    - **Structured Data**: Organized and labeled, fitting a predefined model (e.g., names, dates).
    - **Unstructured Data**: Makes up about 80% of data, lacking a specific format (e.g., images, videos, social media posts).
    - **Semi-Structured Data**: Contains elements of both structured and unstructured data (e.g., emails with metadata).
- **Sources of Data**: [[Data]]
    
    - Structured data often comes from relational databases and spreadsheets.
    - Semi-structured data can be found in XML and JSON files.
- **Impact of Cloud Computing**:
    - Cloud computing has significantly advanced Big Data capabilities by providing scalable resources over the Internet.
    - It allows companies to efficiently process large datasets and run complex models while reducing costs.
---
# Technology

In the evolving world of big data, new technologies are emerging to address the growing need for faster, more scalable, and efficient data processing. Traditional systems like Hadoop and Spark have been the backbone of big data processing, but modern technologies such as Apache Pulsar, Apache Druid, and PrestoDB are gaining popularity for their unique capabilities. This reading will explore these technologies and compare their features to Hadoop and Spark, providing you with a broader understanding of the current big data landscape.

- **Big Data Tooling Categories**: There are six main categories of tools in the Big Data ecosystem:
    
    - **Data Technologies**: Designed for analyzing and processing Big Data, handling both structured and unstructured data. Key technologies include Apache Hadoop, Apache HDFS, and Apache Spark.
    - **Analytics and Visualization**: Tools that uncover patterns and trends in data, providing visual representations through graphs and charts. Examples include Tableau, Palantir, and SAS.
    - **Business Intelligence (BI)**: Transforms raw data into actionable insights for business analysis. Notable BI tools are Cognos, Oracle, and PowerBI.
    - **Cloud Service Providers**: Offer infrastructure and support for data processing, including AWS, IBM, and GCP.
    - **NoSQL Databases**: Specifically designed for Big Data, these databases store data in documents rather than relational tables. Examples include MongoDB and Cassandra.
    - **Programming Tools**: Used for large-scale analytical tasks, including R, Python, and SQL.
## Objectives

By the end of this reading, learners will be able to:

1. Explain the core functionalities and use cases of modern big data technologies
2. Differentiate traditional and emerging solutions
3. Recognize the specific scenarios where each technology—Pulsar for messaging and streaming, Druid for real-time analytics, and PrestoDB for distributed querying—is best suited
4. Evaluate the scalability, performance, and latency trade-offs of these emerging technologies compared to traditional big data systems
5. Determine the right technology stack for real-world applications

---

## 1. Apache Pulsar

### Overview

Apache Pulsar is an open-source, cloud-native, distributed messaging and streaming platform developed by Yahoo in 2016. It was built to handle high-throughput, low-latency messaging for large-scale, globally distributed systems. Pulsar combines features of both message queueing systems (like Kafka) and real-time streaming platforms, making it highly versatile for modern data architectures.

### Key features

- **Unified messaging model:** Pulsar supports both message queueing and real-time streaming in a single system. This reduces the need to integrate multiple solutions for different use cases.
- **Multi-tenancy and isolation:** Pulsar architecture is designed with multi-tenancy in mind, allowing multiple clients or teams to share the same Pulsar cluster while maintaining strong isolation between their workloads. This makes Pulsar ideal for large organizations with various use cases.
- **Geo-replication:** Pulsar natively supports geo-replication, allowing seamless data replication across multiple geographic locations, which is critical for building globally distributed systems.
- **Topic compaction and retention:** Pulsar supports topic compaction, which keeps only the most recent values for each key, and message retention policies that can store messages for defined periods.
- **Scalability and performance:** Pulsar separates compute and storage (via Apache BookKeeper), allowing horizontal scaling with minimal impact on performance. Its architecture ensures low-latency message delivery and can scale to millions of topics.

### Use cases

- **Real-time analytics:** Pulsar is well-suited for capturing real-time events and streaming them to downstream analytics engines like Apache Druid or Apache Spark.
- **Event-driven architectures:** Pulsar ability to handle both message queueing and streaming makes it ideal for event-driven applications such as microservices.
- **Data pipeline orchestration:** It can serve as the backbone of complex data pipelines, ensuring real-time, fault-tolerant message delivery.

### Limitations

- Learning curve for deployment and operation
- Limited community and ecosystem compared to Kafka

---

## 2. Apache Druid

### Overview

Apache Druid is a real-time analytics database designed for rapid ingestion and querying of event-driven data. Originally developed by Metamarkets (later acquired by Snap Inc.), Druid excels at handling high volumes of time-series data, such as logs, metrics, and clickstreams.

### Key features

- **Columnar data storage:** Druid stores data in a columnar format, which allows for fast aggregation and filtering of large data sets. This structure is optimized for analytical queries that scan large amounts of data.
- **Real-time data ingestion:** Druid can ingest streaming data from sources like Apache Kafka or Pulsar and provide near-instant query results. Its ability to combine streaming and batch data ingestion makes it highly versatile.
- **Time-series analysis:** Druid architecture is optimized for time-based data, making it ideal for use cases like time-series data analysis, trend monitoring, and anomaly detection.
- **Horizontal scalability:** Druid can scale horizontally by adding more nodes, allowing it to handle petabytes of data efficiently.
- **Optimized for OLAP:** Druid is purpose-built for Online Analytical Processing (OLAP) workloads, which involve complex queries that aggregate large datasets.

### Use cases

- **Interactive dashboards:** Druid is commonly used for powering interactive analytics dashboards where users need to query large datasets in real time.
- **Fraud detection:** Its ability to analyze large volumes of real-time data makes it suitable for detecting patterns of fraud or suspicious activity.
- **Operational analytics:** Businesses use Druid to monitor and analyze metrics from their operational systems, such as monitoring system logs or user activity.

### Limitations

- Complexity in setup and configuration
- Limited flexibility for non-time-series data

---

## 3. PrestoDB

### Overview

PrestoDB is an open-source distributed SQL query engine, developed by Facebook, that allows querying across large data sets stored in a variety of systems such as HDFS, S3, MySQL, and NoSQL stores. Presto is designed to execute complex queries at interactive speeds, making it an ideal solution for businesses looking for fast querying without moving data.

### Key features

- **Federated queries:** Presto can query data from multiple sources, combining data sets from different systems into a single query. This eliminates the need for ETL (Extract, Transform, Load) processes, making it easier to work with disparate data sources.
- **Interactive query speeds:** Presto is optimized for running SQL queries with low-latency, making it a popular choice for business intelligence (BI) tools where fast querying of large datasets is essential.
- **Pluggable architecture:** Presto offers extensible architecture that allows for integration with a wide range of data sources through custom connectors.
- **Scalability:** Presto can scale horizontally across clusters, enabling it to handle large data sets spread across different storage systems.

### Use cases

- **Data lake querying:** Presto is frequently used to query data in distributed data lakes such as those built on top of HDFS or AWS S3.
- **Interactive analytics:** Business intelligence and reporting tools use Presto to provide users with fast, interactive access to large data sets.
- **Ad hoc data exploration:** Data scientists and engineers use Presto for exploratory data analysis across multiple data sources.

### Limitations

- Not designed for transaction processing or streaming workloads
- Requires careful tuning for large-scale queries

---

## Comparison with Hadoop and Spark

|     | Feature                | Apache Hadoop                            | Apache Spark                            | Apache Pulsar                            | Apache Druid                            | PrestoDB                                              |
| --- | ---------------------- | ---------------------------------------- | --------------------------------------- | ---------------------------------------- | --------------------------------------- | ----------------------------------------------------- |
| 1   | **Core functionality** | Batch processing                         | Batch + Stream processing               | Message queueing + Streaming             | Real-time analytics database            | SQL query engine                                      |
| 2   | **Primary use case**   | Large-scale ETL                          | Real-time and batch analytics           | Event-driven microservices               | Real-time + historical queries          | Interactive querying                                  |
| 3   | **Data processing**    | Disk-based, MapReduce                    | In-memory processing                    | Stream and message processing            | Real-time ingestion                     | SQL queries across sources                            |
| 4   | **Latency**            | High                                     | Low (in-memory)                         | Low                                      | Low (optimized for OLAP)                | Low                                                   |
| 5   | **Scalability**        | High but requires tuning                 | High                                    | Very high (geo-replication)              | Horizontally scalable                   | Horizontally scalable                                 |
| 6   | **Data ingestion**     | Batch                                    | Batch + Stream                          | Stream                                   | Batch + Stream                          | Batch                                                 |
| 7   | **Strengths**          | High fault-tolerance, mature ecosystem   | Fast, in-memory computing, ML libraries | Unified messaging and streaming          | Time-series analysis, fast aggregations | Fast interactive queries across multiple data sources |
| 8   | **Weaknesses**         | High latency, not suitable for real-time | Complex for small-scale tasks           | Complex configuration, smaller ecosystem | Limited non-time-series flexibility     | Requires tuning for optimal performance               |
