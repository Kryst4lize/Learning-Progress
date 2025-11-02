- **Definition**: Document-based [[NoSQL]] databases store data in documents, typically in JSON or XML format. Each document is a flexible schema, meaning that no two documents need to have the same structure.
    
- **Architecture**: These databases build on the Key-Value model, allowing the value to be visible and queried. They support indexing and querying of document contents, enabling key and value range lookups and analytical queries through methods like MapReduce.
    
- **Scalability**: Document databases are horizontally scalable, allowing for sharding across multiple nodes, usually based on a unique key in the document.
    
- **Transaction Support**: They generally guarantee atomic transactions only for single document operations, which means that transactions involving multiple documents may not be supported.
    
- **Use Cases**:
    
    - **Event Logging**: Each event can be stored as a separate document, capturing all relevant information.
    - **Online Blogging**: Users, posts, and comments can each be represented as documents, containing pertinent data like usernames and timestamps.
    - **Operational Datasets**: They are well-suited for web and mobile applications, particularly with unstructured data.
- **Limitations**: Document databases are not ideal for scenarios requiring ACID transactions across multiple documents or when data naturally fits a normalized/tabular model.
    
- **Popular Implementations**: Some widely used document NoSQL databases include IBM Cloudant, MongoDB, Apache CouchDB, and Couchbase.