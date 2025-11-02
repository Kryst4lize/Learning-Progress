Once the data you need has been gathered and imported, your next step is to make it analytics-ready. This is where the process of **Data Wrangling**, or Data Munging, Data transformation, comes in. After that is [[Data Loading]]. Data Wrangling involves a whole range of transformations and cleansing activities performed on the data. Transformation of raw data includes the tasks you undertake to:

- Structurally manipulate and combine data using Joins and Unions.
    
- Normalize data, that is, clean the database of unused and redundant data.
    
- Denormalize data, that is, combine data from multiple tables into a single table so that it can be queried faster.
    

Cleansing activities include:

- Profiling data to uncover anomalies and quality issues.
    
- Visualizing data using statistical methods in order to spot outliers.
    
- Fixing issues such as missing values, duplicate data, irrelevant data, inconsistent formats, syntax errors, and outliers.
    

A variety of software and tools are available for the data wrangling process. Some of the popularly used ones include Excel Power Query, Spreadsheets, OpenRefine, Google DataPrep, Watson Studio Refinery, Trifacta Wrangler, Python, and R, each with their own set of features, strengths, limitations, and applications.

---
# Transformation Technique
- **Data Transformation Techniques**:
    
    - Involves formatting data to meet application needs.
    - Common operations include:
        - **Data Typing**: Casting data to appropriate types (e.g., integer, float).
        - **Data Structuring**: Converting formats (e.g., JSON, XML to database tables).
        - **Anonymizing and Encrypting**: Ensuring privacy and security.
        - **Cleaning Operations**: Removing duplicates and filling missing values.
        - **Normalizing Data**: Ensuring comparability (e.g., using a common currency).
        - **Filtering, Sorting, Aggregating, and Binning**: Accessing data at suitable levels of detail.
        - **Feature Engineering:** creating KPIs for dashboards or machine learning
        - **Joining or Merging Data Sources**: Combining disparate data.
- **Schema-on-Write vs. Schema-on-Read**:
    
    - **Schema-on-Write**: Data must conform to a defined schema before loading (used in traditional ETL). -> Consistency and Efficiency, but limited versatility
    - **Schema-on-Read**: Schema is applied after reading raw data (used in modern ELT), allowing for more versatility. -> Enhance storage flexibility
- **Information Loss in Transformation**:
    - Information can be lost through:
        - **Lossy Data Compression**: E.g., converting floating-point values to integers.
        - **Filtering**: Permanent selection of data can discard information.
        - **Aggregation**: Loss of detail when summarizing data.
        - **Edge Computing Devices**: Potential for false negatives in data processing.