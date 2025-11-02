Keyword: [[Data Cubes and Operation Foundation]], [[Information Model and Data Model]]
- **Star Schema**:
    - **Structure**: Consists of a central **fact table** surrounded by **dimension tables**. ([[Fact and Dimension Model]])
    - **Fact Table**: Contains foreign keys that link to primary keys in dimension tables. It holds measurable data (facts) related to a business process.
    - **Dimension Tables**: Provide context to the facts, such as time, product, or store information.
    - **Visualization**: The schema resembles a star, with the fact table at the center and dimension tables radiating outwards.
    - **Usage**: Commonly used to create specialized data warehouses known as [[Datamart]].
![[StarSchema.png]]
- **Snowflake Schema**:
    - **Structure**: An extension of the star schema that normalizes dimension tables into multiple related tables.
    - **Normalization**: Involves breaking down dimension tables into child tables to reduce redundancy and improve data integrity.
    - **Example**: A dimension table for stores might be split into separate tables for cities, states, and countries.
![[SnowflakeModel.png]]
Design Considerations for Star Schema:

1. **Select a Business Process**: Identify the process you want to model (e.g., sales, manufacturing).
2. **Choose Granularity**: Determine the level of detail needed (e.g., individual transactions vs. monthly summaries).
3. **Identify Dimensions**: Define attributes that provide context (e.g., date, product, store).
4. **Identify Facts**: Determine what is being measured (e.g., sales amount, quantity sold).