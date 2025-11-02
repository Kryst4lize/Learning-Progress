[[Struct Query Language (SQL)]], [[Database]], [[Query Optimization]], [[Database Storage]]
- **Definition of Index**: An index is a data structure that allows quick access to specific rows in a database table based on certain criteria, similar to a library catalog.
- **Performance Improvement**: Indexes significantly enhance the performance of database queries by allowing the database to locate relevant rows without scanning the entire table.
- **How Indexing Works**:
    - Indexes store pointers to each row in the table.
    - When a specific row is requested, the SQL processor uses the index to find it quickly.
- **Benefits of Indexing**:
    - Improved performance of select queries.
    - Reduced need to sort data.
    - Guaranteed uniqueness of rows when using unique indexes.
- **Disadvantages of Indexing**:
    - Use of disk space.
    - Decreased performance for insert, update, and delete operations due to the need to maintain the index.
- **Everyday Examples**:
    
    - **Library Example**: Finding a specific book in a large library, like the British Library with 25 million books, is made easier with indexes. Instead of searching through every book, you can go directly to the relevant section and shelf.
    - **Telephone Book**: Names are indexed by surname and first name, allowing you to quickly find a person by navigating to the correct section.
---
# Optimize using indexes
- **Purpose of Indexing**: Indexing improves query performance by allowing faster searches in a database, similar to how an index in a book helps locate information quickly.
    
- **Types of Indexes**:
    
    - **Primary Key Index**: Unique, non-nullable, and clustered; only one per table.
    - **Secondary Indexes**: Non-clustered, can have multiple columns, and can be unique or non-unique.
- **Creating Indexes**:
    
    - Use the `CREATE INDEX` statement to define an index.
    - The `DROP` statement is used to delete an index, but primary or unique key indexes must be dropped using the `ALTER TABLE` statement first.
- **Design Considerations**:
    - Understand how the database will be used and the most frequently used queries.
    - Consider the characteristics of the columns being indexed.
    - Choose appropriate indexing options to improve performance.
    - Where the storage was put (for instance, if indexes and data put in different disk, it can run parallel and boost the query performance)
- **Performance Optimization**: Efficient index design is crucial to avoid bottlenecks in database applications.
- - **Database Indexing**:
    - Indexes should be created for the most frequently queried fields. For instance, in a Campus Management Database, an index on the ‘courseId’ field allows for efficient student searches.
    - A compound index can be used to index multiple fields, which helps in sorting and searching more efficiently.
---





