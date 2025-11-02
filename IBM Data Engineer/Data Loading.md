Data Loading Techniques

1. **Data Loading Strategies**:
    
    - **Full Loading**:
        - Used to start tracking transactions in a new data warehouse or to load initial history into a database.
        - There is no existing content before this process.
    - **Incremental Loading**:
        - Used after full loading to insert data that has changed since the last load.
        - Data is appended rather than overwritten, which is useful for accumulating transaction history.
2. **Types of Incremental Loading**:
    
    - **Stream Loading**:
        - Involves continuous data updates as new data arrives.
        - Triggered by events (e.g., real-time data from sensors) or measures (e.g., data size thresholds).
    - **Batch Loading**:
        - Refers to periodic updates made to the data warehouse, such as daily or weekly updates.
        - Can be scheduled using tools like Windows Task Scheduler or Cron jobs in Linux.
3. **Data Loading Methodologies**:
    
    - **Push Method**:
        - The source pushes data into the data warehouse.
        - Most suited for stream loading with real-time data.
    - **Pull Method**:
        - The data warehouse pulls data from the source by subscribing to receive it.
        - Useful for scheduled transactions and batch loading.
4. **Loading Techniques**:
    - **Serial Loading**:
        - Data is copied sequentially, one after the other.
        - This is the default method for loading data into a data warehouse.
    - **Parallel Loading**:
        - Data is loaded from different sources simultaneously or split into chunks for faster loading.
        - More efficient for large volumes of data or when data needs to travel long distances.