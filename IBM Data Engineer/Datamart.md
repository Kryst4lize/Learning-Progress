- **Definition of Data Mart**: A data mart is a specialized segment of a larger enterprise [[Data Warehouse]], designed to serve a specific business function or community of users, such as sales, finance, or marketing. ([[Data Source]] [[Database Storage]])
    
- **Purpose of Data Marts**: They provide targeted support for tactical decision-making by offering relevant data quickly, saving users time in searching through larger data warehouses.
    
- **Structure**: Data marts typically use a relational database structure, often employing star or snowflake schemas. This includes a central fact table with business metrics surrounded by dimension tables that provide context.
    
- **Comparison with Other Data Repositories**:

| Data marts                               | Databases                                   |
| ---------------------------------------- | ------------------------------------------- |
| OLAP system - read extensive             | OLAP system - write extensive               |
| Use Txn DBs or Warehouse as data source  | Use operational application as source data  |
| Contain Clean, validated analytical data | Contain raw, unprocessed transactional data |
| Accumulate history for trend analysis    | May not always store history                |
| **Data marts**                           | **Datawarehouse**                           |
| Small data warehouse with tactical scope | Large data warehouse with strategic scope   |
| Lean and fast                            | Slow and large                              |
- **Types of Data Marts**:
    - **Dependent Data Marts**: Draw data from the enterprise data warehouse.
    - **Independent Data Marts**: Created directly from operational systems or external sources, bypassing the data warehouse.
    - **Hybrid Data Marts**: Combine data from both the data warehouse and operational systems.
- **Benefits of Data Marts**:
    - Provide relevant data efficiently.
    - Accelerate business processes with quick query responses.
    - Offer a cost-effective way to support data-driven decisions.
    - Ensure secure access and control over data.