**Categories of NoSQL Databases**: There are four main categories of [[NoSQL]] databases: **key-value**, **document**, **column**, and **graph**. Each category has unique characteristics suited for different applications.
# Key-Value Database Architecture:
- 
	- Data is stored as a **key** and an associated **value blob**.
    - Architecturally, key-value stores are represented as a **hash map**.
    - They are simple and efficient for basic **create, read, update, delete (CRUD)** operations.
- **Scalability**: Key-value databases typically scale well and can be easily sharded across multiple nodes, with each shard containing a range of keys and their values.
    
- **Limitations**:
    
    - They are not designed for complex queries that involve multiple pieces of data.
    - They support atomic operations only for single key operations.
    - The value blob is opaque, limiting flexibility in indexing and querying compared to other database types.
- **Use Cases**:
    
    - Ideal for scenarios requiring quick performance for basic CRUD operations where data is not interconnected.
    - Examples include:
        - **Storing session information** for web applications.
        - **User profiles and preferences** within applications.
        - **Shopping cart data** for online stores.
- **Unsuitable Scenarios**: Key-value databases are not suitable for:
    
    - Use cases with interconnected data and many-to-many relationships (e.g., social networks).
    - Scenarios requiring high consistency for multi-operation transactions involving multiple keys.
    - Cases where querying based on value rather than key is necessary, which may require document databases instead.
- **Popular Implementations**: Some well-known key-value NoSQL databases include:
    - **Amazon DynamoDB**
    - **Oracle NoSQL Database**
    - **Redis**
    - **Aerospike**
    - **MemcacheDB**