[[Data Warehouse]] 
- **Ongoing Process**: Populating a data warehouse is an ongoing process that includes an initial load followed by periodic incremental loads. Full refreshes are rare and typically only occur during major schema changes or catastrophic failures.
    
- **Fact and Dimension Tables**:
    
    - **Fact Tables**: These are dynamic and require frequent updates, as they contain transactional data (e.g., sales).
    - **Dimension Tables**: These are more static and do not change often (e.g., lists of cities or stores).
- **Automation Tools**: Various tools can automate the process of keeping the data warehouse current, such as:
    
    - **Db2 Load Utility**: Faster than inserting rows one at a time.
    - **ETL Data Pipeline Tools**: Tools like Apache Airflow and Apache Kafka can automate data loading.
    - **Custom Scripts**: You can write scripts using languages like Bash, Python, and SQL to build and schedule your data pipeline.
- **Preparation Steps**: Before populating the data warehouse, ensure:
    
    - The schema is modeled.
    - Data is staged in tables or files.
    - Mechanisms for verifying data quality are in place.
- **Initial Load Process**:
    
    - Instantiate the data warehouse and its schema.
    - Create production tables and establish relationships between fact and dimension tables.
    - Load transformed and cleaned data from staging tables or files.
- **Incremental Loads**: After the initial load, automate subsequent incremental loads using scripts. Schedule these loads based on your needs (daily or weekly) and include logic to detect new or updated data.
    
- **Change Detection**: Changes in the source system can be detected using:
    
    - Timestamps for new or modified records.
    - Mechanisms in relational database management systems to identify changes.
- **Periodic Maintenance**: Data warehouses require periodic maintenance (monthly or yearly) to archive data that is not frequently used. This can be scripted for efficiency.
    
- **Example of Manual Population**:
    
    - A simplified example involves creating a sales star schema with dimension tables (e.g., DimSalesPerson) and a fact table (e.g., FactAutoSales).
    - Use SQL commands to create and populate these tables, establishing relationships between them.