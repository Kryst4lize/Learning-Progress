[[Data Ecosystem]]
**A Data Repository** is a general term that refers to data that has been collected, organized, and isolated so that it can be used for reporting, analytics, and also for archival purposes.
**Characteristic:**
- Store, manage and organize data
- Offer a structured network for retrieval and administration
- Categories : Relational database and Non-relational database
---
Databases, which can be [relational](Relational%20Databases.md) or [non-relational](Non-relational%20Databases.md), each following a set of organizational principles, the types of data they can store, and the tools that can be used to query, organize, and retrieve data.
The **different types of Data Repositories** include:
- Data Warehouses, that consolidate incoming data into one comprehensive store house.
    
- Data Marts, that are essentially sub-sections of a data warehouse, built to isolate data for a particular business function or use case.
    
- Data Lakes, that serve as storage repositories for large amounts of structured, semi-structured, and unstructured data in their native format.
    
- Big Data Stores ([[Big data]]), that provide distributed computational and storage infrastructure to store, scale, and process very large data sets.
    
- Data Lake House, A combination of Data Warehouses and Data Lakes, which offer more flexibility and Scalability with the data management and transaction  
**The ETL**, or Extract Transform and Load, Process is an automated process that converts raw data into analysis-ready data by:

- Extracting data from source locations.
    
- Transforming raw data by cleaning, enriching, standardizing, and validating it.
    
- Loading the processed data into a destination system or data repository.
    

**The ELT,** or Extract Load and Transfer, Process is a variation of the ETL Process. In this process, extracted data is loaded into the target system before the transformations are applied. This process is ideal for Data Lakes and working with Big Data.

**Data Pipeline**, sometimes used interchangeably with ETL and ELT, **encompasses the entire journey of moving data from its source to a destination data lake or application**, using the ETL or ELT process.

**Data Integration Platforms combine disparate sources of data, physically or logically, to provide a unified view of the data for analytics purposes.**

**Definition**: data integration as a discipline comprising the practices, architectural techniques, 
and tools that allow organizations to ingest, transform, combine, and provision data across 
various data types
![[Data_integration_Ilust.png]]