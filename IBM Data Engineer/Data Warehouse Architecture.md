[[Data Warehouse]] 
- **Use Cases for Data Warehousing**: The design of a data warehouse is influenced by various use cases, including report generation, exploratory data analysis, automation, machine learning, and self-serve analytics.
    
- **General Data Warehousing Architecture**: A typical architecture includes several layers:
    
    - **Data Sources**: These can be flat files, databases, or operational systems.
    - **ETL Layer**: This layer is responsible for extracting, transforming, and loading data.
    - **Staging and Sandbox Areas**: Optional areas for holding data and developing workflows.
    - **Enterprise Data Warehouse Repository**: The main storage for integrated data.
    - **Data Marts**: These are subsets of the data warehouse, often used in a "hub and spoke" model.
    - **Analytics Layer**: This includes business intelligence tools for data analysis.
- **Security**: Data warehouses enforce security measures for incoming data and data in transit. (red layer)
![[Data WareHouse Architecture.png]]
- **Vendor-Specific Reference Architecture**: Different vendors create proprietary architectures that are tailored to their tools and products, ensuring interoperability among components.
    
- **IBM Reference Architecture**: The video outlines IBM's specific architecture, which includes:
    
    - **Data Acquisition Layer**: Components for acquiring raw data from various source systems.
    - **Data Integration Layer**: A staging area for ETL processes and metadata management.
    - **Data Repository Layer**: Stores integrated data, typically using a relational model.
    - **Analytics Layer**: Often uses a cube format for easier data analysis.
    - **Presentation Layer**: Applications that provide access to data for different user groups.
- **IBM Tools**: The architecture is supported by various IBM products, including:
    - **IBM InfoSphere DataStage**: An ETL platform for real-time data integration.
    - **IBM InfoSphere MetaData Workbench**: For data flow reporting and impact analysis.
    - **IBM InfoSphere QualityStage**: Focused on data quality and governance.
    - **IBM Db2 Warehouse**: Manages both structured and unstructured data.
    - **IBM Cognos Analytics**: A business intelligence platform for reporting and data visualization.