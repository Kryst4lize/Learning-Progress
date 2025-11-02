Key Concepts [[Entity Relationship Diagram (ERD)]] [[Struct Query Language (SQL)]]

1. **Entity-Relationship Diagram (ERD)**:
    - Understanding ERDs is crucial for visualizing the relationships between tables in a star schema.
    - The star schema consists of a central fact table linked to various dimension tables.
2. **Materialized Views**:
    - A materialized view is created by denormalizing or joining tables from a star schema.
    - It allows for faster querying since the data is precomputed and stored.
    - Materialized views can be refreshed on a schedule or on-demand, which is beneficial for complex queries or large datasets.
3. **CUBE and ROLLUP Operations**:
    - These operations are used in SQL to generate summary reports.
    - **CUBE**: Generates all possible combinations of the specified dimensions, providing a comprehensive summary.
	![[CubeOperation.png]]
    - **ROLLUP**: Provides a hierarchical summary, focusing on a single permutation of the dimensions, resulting in fewer rows than CUBE.
    ![[ROLLUPOperation.png]]

Practical Scenario

- The scenario involves creating live summary tables for January sales at ShinyAutoSales.
- The existing star schema in the "sasDW" data warehouse is explored, focusing on the "fact auto sales" table and its relationships with dimension tables (Date, Auto Category, and Salesperson).

Steps in the Process

1. **Querying the Fact Table**:
    
    - Start by querying the "fact auto sales" table to view the first 10 rows, which include sales amounts and foreign keys.
2. **Exploring Dimension Tables**:
    
    - Query the auto category dimension table to understand the different automobile classes and their subclasses (new vs. used).
    - Query the salesperson dimension table to identify distinct salesperson names.
3. **Creating a Denormalized View**:
    
    - Select relevant columns from the fact and dimension tables to create a denormalized view.
    - This view combines human-readable data, making it easier to analyze.
4. **Materializing the View**:
    
    - Create a materialized view called "Denormalized sales" to store the denormalized data for further analysis.
5. **Applying CUBE and ROLLUP**:
    - Use the CUBE operation to generate a summary of sales amounts by auto class and salesperson.
    - Compare the results with the ROLLUP operation, noting that ROLLUP provides fewer rows and focuses on hierarchical summaries.