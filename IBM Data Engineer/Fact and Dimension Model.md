In the video on **Facts and Dimensional Modeling**, you will learn about the fundamental concepts of [[Data Warehouse]], specifically focusing on facts and dimensions. Here’s a detailed summary of the key points covered: ([[Information Model and Data Model]])

- **Definitions**:
    
    - **Facts**: Quantities that can be measured, such as sales amounts, temperature, or rainfall. They can also be qualitative, like weather conditions (e.g., "partly cloudy").
    - **Dimensions**: Attributes that provide context to facts, such as location, time, or product details.
- **Example**: A weather report illustrates how facts (temperature, humidity) and qualitative facts (weather conditions) are contextualized by dimensions (location and time).
    
- **Fact Tables**:
    
    - Contain facts of a business process and foreign keys linking to dimension tables.
    - Can include detailed facts (individual transactions) or aggregated facts (summarized data).
    - **Summary Tables**: Fact tables that contain aggregated data, such as quarterly sales totals.
- **Accumulating Snapshot Fact Tables**: Used to record events in a defined business process, capturing various stages of an order (e.g., order date, payment date, shipping date) in a single row identified by a unique order ID.
    
- **Dimension Tables**: Store dimensions that categorize facts and are linked to fact tables via foreign keys. Common types of dimension tables include:
    
    - **Product Tables**: Describe product attributes (make, model, color).
    - **Employee Tables**: Describe employee details (name, title).
    - **Temporal Tables**: Describe time-related data.
    - **Geography Tables**: Store location data (country, city).