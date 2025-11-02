Definition of NoSQL
- **Meaning**: The term NoSQL was coined during an event discussing new open-source distributed databases. It signifies "not only SQL," emphasizing that these databases are not limited to traditional SQL databases.
- **Nature**: NoSQL databases are characterized as [[Non-relational Databases]], meaning they do not adhere to the standard row and column structure of relational database management systems (RDBMS).

Characteristics of NoSQL Databases

- **Flexible Data Models**:
    - NoSQL databases can handle unstructured or semi-structured data, making them adaptable to various data types and formats.
- **Schema-less Design**:
    - Unlike relational databases, NoSQL databases do not require a fixed schema, allowing for easier modifications as application requirements evolve.
- **Scalability**:
    - They can scale horizontally, meaning that as data and traffic increase, additional servers can be added to manage the load without significant reconfiguration.
- **Fault Tolerance and High Availability**:
    - NoSQL databases are designed as distributed systems, which means they can continue to operate even if some components fail, ensuring that data remains accessible.

History of NoSQL

- **Early Years (1970-2000)**:
    - The database landscape was dominated by relational databases like Oracle, IBM DB2, Microsoft SQL Server, and MySQL.
    - Non-relational databases existed, such as IBM's IMS, but they were not widely adopted.
- **Dot-Com Boom (Late 1990s - Early 2000s)**:
    - The explosion of internet applications required databases that could handle millions of users, leading to performance and availability challenges.
    - This period saw significant innovation, with companies like IBM, Google, and Meta developing new technologies and publishing influential white papers.
- **Emergence of NoSQL Databases (Late 2000s)**:
    - New databases like Apache Cassandra and MongoDB emerged, often from open-source communities, to address the scalability needs of modern applications.
    - The concept of Database-as-a-Service (DBaaS) also gained traction, allowing users to offload database management tasks.

Reasons for Using NoSQL

- **Support for Evolving Use Cases**:
    - The flexible nature of NoSQL databases allows them to adapt to changing application requirements without the constraints of a fixed schema.
- **Increased Developer Productivity**:
    - Developers can work more efficiently with data structures that align with their application's specific needs for reading and writing data.
- **Diverse Use Cases**:
    - Businesses often employ a combination of NoSQL databases to meet different data management needs, leveraging the strengths of each type.

Examples of NoSQL Usage

- **Social Media Platforms**:
    - **Document Databases**: Used to manage user profiles, allowing for flexible storage of user information.
    - **Column Databases**: Employed to store user activity feeds, enabling efficient retrieval of large volumes of data.
    - **Key-Value Databases**: Help manage user sessions, providing quick access to frequently accessed data.
    - **Graph Databases**: Essential for maintaining relationships between users, such as friends and connections.
---
# Characteristic
1. **Introduction to NoSQL Databases**:
    
    - The video begins by explaining that NoSQL databases are characterized by their **[[Non-relational Databases]] architecture**. This fundamental trait differentiates them from traditional relational databases.
2. **Types of NoSQL Databases**:
    
    - NoSQL databases can be categorized into four main types:
        - **Key-Value Stores**: Simple data storage where each key is associated with a single value.
        - **Document Stores**: Store data in documents (often JSON-like), allowing for more complex data structures.
        - **Column-based Stores**: Organize data in columns rather than rows, optimizing for read and write performance.
        - **Graph Databases**: Focus on relationships between data points, making them ideal for associative data sets.
    - There is some overlap among these categories, and definitions may vary.
3. **Open-source Community**:
    
    - A significant aspect of NoSQL databases is their roots in the **open-source community**. This has been crucial for their growth and adoption in various industries.
    - Many companies offer commercial versions of their NoSQL databases while also supporting the open-source versions, such as:
        - **IBM Cloudant** for CouchDB
        - **Datastax** for Apache Cassandra
        - **MongoDB** for its own database.
4. **Common Characteristics**:
    
    - NoSQL databases are generally built to **scale horizontally**, which allows for easier data partitioning (or sharding).
    - They are often more specialized for specific use cases compared to relational databases, which are seen as more general-purpose.
5. **Developer Appeal**:
    
    - Developers are attracted to NoSQL databases for their **ease of data modeling** and the flexibility of their schemas, which contrasts with the fixed schemas of relational databases.
    - This flexibility allows for more agile development, enabling quick adaptations to changing application requirements.
6. **Benefits of NoSQL Databases**:
    
    - **Scalability**: They can scale horizontally across clusters of servers, which is essential for handling large amounts of data and user requests.
    - **Performance**: NoSQL databases can provide fast response times, even under high concurrency and large datasets.
    - **High Availability**: Running on clusters with multiple copies of data enhances resilience and reduces the risk of downtime.
    - **Cost Efficiency**: They can significantly reduce costs compared to traditional databases, especially when deployed in cloud architectures.
    - **Flexible Schema**: The ability to have flexible schemas allows developers to implement new features quickly without database locking or downtime.
    - **Varied Data Structures**: Different data structures (e.g., key-value, document, graph) can be more suitable for specific application needs.
7. **Considerations for Using NoSQL**:
    
    - While NoSQL databases offer many advantages, there are still scenarios where relational databases (RDBMS) may be more appropriate due to specific requirements.
8. **Conclusion**:
    - The video concludes by summarizing the key points: NoSQL databases are non-relational, categorized into four types, rooted in the open-source community, and offer various benefits that make them increasingly popular in modern applications.
---
# NoSQL Database Types and Use Cases

After completing this reading, you will be able to describe the characteristics of several NoSQL database types, list their use cases, and identify frequently mentioned vendors associated with each NoSQL database type.

As you review each use case, you'll see frequently used NoSQL database vendors mentioned in parentheses following the listed use case. This information is not an endorsement. This information is for market awareness.

Gain the insights you need to be able to explain some of the technical considerations associated the use of MongoDB with a content management system (CMS).

|                              | Document store databases                                                                                                                                                                                                                                                                                                                                                                                                                                  | Key-value stores                                                                                                                                                                                                                                                                                                                               | Column-family stores                                                                                                                                                                                                                                                                                                                                                        | Graph databases                                                                                                                                                                                                                                                                                                                                                       | Wide-column stores                                                                                                                                                                                                                                                                                                         |
| ---------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Definition                   | Document-store databases, also known as document-oriented databases, store data in a document format, typically JSON or BSON (binary JSON), where each document contains key-value pairs or key-document pairs. These databases are schema-less, allowing flexibility in data structures within a collection.                                                                                                                                             | Key-value stores are the simplest NoSQL databases, storing data as a collection of key-value pairs, where the key is unique and directly points to its associated value.                                                                                                                                                                       | Definition: Column-family stores NoSQL databases, also referred to as columnar databases, organize data in columns rather than rows. These databases store columns of data together, making them efficient for handling large data sets with dynamic schemas.                                                                                                               | Graph NoSQL databases are designed to manage highly interconnected data, representing relationships as first-class citizens alongside nodes and properties.                                                                                                                                                                                                           | Wide-column store NoSQL databases organize data in tables, rows, and columns, like relational databases, but with a flexible schema.                                                                                                                                                                                       |
| Characteristics              | - Provides schema flexibility: Documents within collections can have varying structures, allowing for easy updates and accommodation of evolving data requirements.<br>- Performs efficient create, read, update, and delete (CRUD) operations: well-suited for read and write-intensive applications due to their ability to retrieve whole documents.<br>- Provides scalability: horizontal scalability by sharding data across clusters.               | - Delivers high performance: efficient for read and write operations, optimized for speedy retrieval based on keys<br>- Provides scalability: easily scalable due to their simple structure and ability to distribute data across nodes<br>- Uses caching for fast access<br>- Provides session management<br>- Works with distributed systems | - Uses column-oriented storage: Data is grouped by columns rather than rows, allowing for efficient retrieval of specific columns.<br>- Delivers scalability: Distributed architecture for high availability and scalability.                                                                                                                                               | Analyzes the data using a graph data model: relationships are as important as the data itself, enabling efficient traversal and querying of complex relationships.<br>- Fast performance for relationship queries: optimized for queries involving relationships, making them ideal for social networks, recommendation systems, and network analysis.                | - Use columnar storage: Data is stored in columns, allowing for efficient retrieval of specific columns rather than entire rows.<br>- Provide horizontal scalability and fault tolerance.<br>                                                                                                                              |
| Use cases                    | - Content management systems (CMS): CMS platforms like WordPress use document store databases for fast storage and access to content types such as articles, images, and user data. (MongoDB)<br>- E-commerce: E-commerce platforms need effective management of product catalogs with diverse attributes and hierarchies, accommodating the dynamic nature of e-commerce product listings. (Couchbase or Amazon DocumentDB, using MongoDB compatibility) | - Enhanced web performance by caching frequently accessed data (Using Redis or Memcached)<br>- E-commerce platforms, software applications, including gaming: Amazon DynamoDB provides a highly scalable key-value store, facilitating distributed systems' seamless operation by handling high traffic and scaling dynamically.               | - IoT applications manage massive amounts of sensor data efficiently due to their ability to handle time-stamped data at scale, referred to as time-series data analysis. (Apache Cassandra)<br>- Applications that store and analyze user preferences and behaviors usually deliver personalization. (HBase, part of the Hadoop ecosystem)<br>- Large-scale data analysis. | Social networks require efficient data management of relationships between users, posts, comments, and likes. (Neo4j)<br>- Recommendation systems: Organizations need a database structure that can create sophisticated recommendation engines, analyzing complex relationships between users, products, and behaviors for precise recommendations. (Amazon Neptune) | - Analyzing big data: Efficiently handling large-scale data processing for real-time big data analytics. (Apache HBase used in conjunction with Hadoop)<br>- Managing enterprise content: Large organizations databases need to manage vast amounts of structured data like employee records or inventory due. (Cassandra) |
| Frequently mentioned vendors | - MongoDB<br>- Couchbase<br>- Amazon DocumentDB                                                                                                                                                                                                                                                                                                                                                                                                           | - Redis<br>- Memcached<br>- Amazon DynamoDB                                                                                                                                                                                                                                                                                                    | - Apache Cassandra<br>- HBase                                                                                                                                                                                                                                                                                                                                               | - Neo4j<br>- Amazon Neptune<br>- ArangoDB Memcached<br>                                                                                                                                                                                                                                                                                                               | - Apache HBase<br>- Apache Cassandra                                                                                                                                                                                                                                                                                       |
## Expanded use case example: Using MongoDB for a content management system (CMS)

Content management systems (CMS) intelligently collect, govern, manage, and enrich enterprise content, including HTML pages, images, articles, and more. Content management systems help companies deploy their content efficiently and securely across any cloud and within any application.

Good content management means that team members can quickly add, update, and remove content from the database and the associated pages that feature that content. Examples include pushing out breaking news, updating current news, including weather forecasts, pushing advertising content, updating college admission policies, launching new city services, and more.

For example, using MongoDB as a backend database for a content management system (CMS) is a practical choice when you need to manage and serve a variety of content types, especially in scenarios where you expect frequent schema changes or scaling requirements.

Next, let's check out some of the aspects of managing content using a content management system, specifically using MongoDB.

### Content structure using MongoDB

In MongoDB, you represent content as documents. Each document corresponds to a piece of content, such as an article, image, video, or page. You can use the subdocuments in the document to organize the content hierarchy and structure.

#### Example of structuring: Storing a blog post

When storing a blog post, you will store core attributes like title, content, created at, and the image URL. Then, using an array field, you can store tags. The comments on that post are stored as an array of objects.

1. `// Collection: posts`
2. `{`
3. `"\_id":1,`
4. `"title":"Sample Blog Post",`
5. `"content":"This is the content of the blog post...",`
6. `"author":{`
7. `"name":"John Doe",`
8. `"email":"john@example.com",`
9. `"bio":"A passionate blogger.",`
10. `"created\_at":"2023-09-20T00:00:00Z"`
11. `},`
12. `"created\_at":"2023-09-20T08:00:00Z",`
13. `"tags":["mongodb","blogging","example"],`
14. `"comments":[`
15. `{`
16. `"text":"Great post!",`
17. `"author":"Emily Johnson",`
18. `"created\_at":"2023-09-20T10:00:00Z"`
19. `},`
20. `{`
21. `"text":"Thanks for sharing!",`
22. `"author":"James Martin",`
23. `"created\_at":"2023-09-20T11:00:00Z"`
24. `}`
25. `]`
26. `}`
### Metadata and indexing using MongoDB

You can use the indexing capabilities of MongoDB to optimize content retrieval. You can create indexes on fields commonly used for filtering or searching, such as keywords, publication date, or content type, or use MongoDB's text index support for text search queries on fields containing string content. Text indexes improve performance when searching for specific words or phrases within string content.

For example, you want to provide searching capability on the content of your blogs. You will first create a text index:

`db.articles.createIndex( { subject: "text" } )`

And then you can provide a query such as:

`db.posts.find( { $text: { $search: "digital life" } } )`

where MongoDB will look for stemmed versions of these words: digital or life

### Scaling your CMS using MongoDB

As your CMS grows, MongoDB can help you scale. You can use sharding for horizontal scaling or use zone-based sharding for global distribution.

#### Using sharding for horizontal scaling (increased capacity)

Let's consider a company that currently has 100 million customers. This company expects to expand its customer base to 200 million customers. This increase in the number of customers means that the company will need to double its IT data storage hardware. The company can scale vertically, which can cost exponentially more as the hardware cost isn't linear with the performance. The following diagram shows that the company can scale horizontally and use sharding to manage the databases.

![Left single cluster displaying 100m customer with growth to 200 millions customerers scaled horizontally to become a shared cluster.](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMSkillsNetwork-CS0101EN-Coursera/images/Sharding.png)

However, the use of sharding for horizontal scaling provides the company with double the throughput at double the cost.

---
# Deployment 
## On-premises deployment

On-premises deployment involves hosting the entire database infrastructure within the organization's physical location or a dedicated data center.

![Example of two databases deployed on-premises connected to a single data center brain.](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMSkillsNetwork-CS0101EN-Coursera/images/200543.012-01.png)

### Example

An organization manages customer relationship data using an on-premises Oracle Database installed on dedicated servers within its corporate data center.
### Advantages

**Full control:** Organizations have complete control over hardware specifications, software configurations, and security measures.

**Compliance:** On-premises solutions might be necessary for industries with stringent regulatory or compliance requirements.

### Challenges

**Upfront costs:** High initial investments in hardware, infrastructure, and skilled personnel.

**Scalability:** Limited scalability compared to cloud alternatives, which might result in challenges during periods of rapid growth.

## Cloud deployment

Cloud deployment involves utilizing cloud service providers to host and manage databases over the internet.

![Illustration that communicates built-in data goverence exists with cloud, hybrid cloud, and on-premises deployments.](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMSkillsNetwork-CS0101EN-Coursera/images/200543.012-02.png)

### Example

A startup leverages Amazon Web Services (AWS) to deploy and host its e-commerce database, utilizing Amazon relational database service (RDS) for scalability and managed database services.

### Advantages

**Scalability:** Resources can be scaled up or down based on demand, providing flexibility and cost savings.

**Cost-effectiveness:** Pay-as-you-go pricing allows organizations to pay only for the resources they consume.

**Automation:** Cloud providers handle routine maintenance tasks, updates, and backups.

### Challenges

**Connectivity dependencies:** Relies on internet connectivity, which might pose issues in areas with limited or unreliable access.

**Security concerns:** Requires robust security measures to protect sensitive data from unauthorized access.

## Hybrid deployment

Hybrid deployment combines on-premises and cloud solutions, allowing organizations to distribute data and workloads based on specific needs.

![Unlocked cloud image connecting to computers, tablets, smartphones and cameras.](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMSkillsNetwork-CS0101EN-Coursera/images/200543.012-03.png)

### Example

A financial institution stores sensitive customer information, such as account balances, in an on-premises database while utilizing a cloud-based service, like AWS Lambda, for processing non-sensitive data analytics workloads.

### Advantages

**Flexibility:** Companies can keep sensitive data on-premises while using the cloud for scalable and dynamic workloads.

**Disaster recovery:** Companies can use cloud storage for backups, enhancing disaster recovery capabilities.

### Challenges

**Integration complexity:** Integration complexities require effective integration between on-premises and cloud environments for seamless operation.

**Management overhead:** Monitoring and managing two different environments might increase administrative complexity.

## Database as a service (DBaaS)

DBaaS provides a fully managed database solution where the service provider handles administrative tasks, allowing organizations to focus on application development.

![Illustration that shows an application communicating through a public network and database as a service (API) with the data.](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMSkillsNetwork-CS0101EN-Coursera/images/200543.012-04.png)

### Example

A software development company uses Microsoft Azure SQL Database as a DBaaS solution to host and manage its relational databases, allowing developers to focus on application development rather than database administration tasks.

### Advantages

**Reduced overhead:** Organizations benefit from reduced administrative tasks, including maintenance, backups, and updates.

**Rapid deployment:** Quick deployment without the need for in-depth database expertise.

### Challenges

**Limited control:** Organizations have less control over underlying infrastructure, which might be a concern for some organizations.

**Data security:** Trusting a third-party provider with sensitive data raises security and privacy considerations.

## Containerized deployment

Containerization involves packaging the database and its dependencies into containers for consistent deployment across various environments.

![Illustration displaying one Docker container running Mongo DB with one Docker volume and two workers, each with one Docker container and one Docker volume.](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMSkillsNetwork-CS0101EN-Coursera/images/200543.012-05.png)

### Example

A tech company adopts Docker containers to deploy its microservices-based application, with each microservice encapsulating a specific function and a separate container running a MongoDB database.

### Advantages

**Portability:** Containers ensure consistent operation across development, testing, and production environments.

**Resource efficiency:** Lightweight containers consume fewer resources compared to traditional virtual machines.

### Challenges

**Orchestration complexity:** Production-scale deployment requires knowledge of container orchestration tools like Kubernetes.

**Learning curve:** Teams might need to familiarize themselves with containerization concepts and tools.

## Serverless deployment

Serverless architecture provisions and scales database resources automatically based on demand, with organizations paying for actual usage.

![An illustration that compares traditional deployment to serverless deployment, with serverless deployment showing the front-end logic separated from the back-end logic, security, and database.](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBMSkillsNetwork-CS0101EN-Coursera/images/200543.012-06.png)

### Example

A mobile app developer utilizes Google Cloud Firestore as a serverless NoSQL database for storing user data, where the database scales automatically based on demand, and the developer only pays for the data storage and operations used by the app.

### Advantages

**No manual provisioning:** No need for manual provisioning or maintenance of server resources.

**Cost savings:** Efficient resource utilization leads to cost savings as organizations only pay for the resources consumed.

### Challenges

**Limited control:** Organizations have less control over underlying infrastructure, which might concern some organizations.

**Applicability:** Serverless might not be suitable for all types of databases or workloads due to architectural constraints.

## Recap

- The choice of a database deployment option depends on organizational priorities, budget constraints, scalability needs, and how the company manages the nature of the data. It's essential to carefully evaluate these options in alignment with specific use cases to ensure optimal performance and efficiency.
    
- On-premises deployment involves hosting the entire database infrastructure within the organization's physical location or a dedicated data center, providing full control and compliance with regulatory requirements but with high upfront costs and limited scalability.
    
- Cloud deployment uses cloud service providers to host and manage databases. Cloud deployment offers scalability, cost-effectiveness, and automation. However, cloud deployments have connectivity dependencies and can be prone to security concerns.
    
- Hybrid deployment combines on-premises and cloud solutions, allowing organizations to distribute data and workloads based on specific needs, providing flexibility and enhanced disaster recovery capabilities; however, effective integration between on-premises and cloud environments requires increased administrative complexity and costs.
    
- Database as a Service (DBaaS) provides a fully managed database solution where the company's choice service provider handles administrative tasks. When using DBaaS, organizations focus on application development but usually have limited control over underlying infrastructure and data security.
    
- Containerized deployment involves packaging the database and its dependencies into containers for consistent deployment across various environments, which can ensure consistent operations and resource efficiency—however, if containerization practices are not already in place, the company will need time for employees to gain knowledge of container orchestration tools and implement them.
    
- Serverless deployment provisions and scales database resources automatically based on demand, with organizations paying for actual usage, eliminating manual provisioning and maintenance of server resources, and leading to cost savings. However, companies usually have limited control over the underlying infrastructure, and serverless deployments might not be technically suitable for all databases or workloads.
