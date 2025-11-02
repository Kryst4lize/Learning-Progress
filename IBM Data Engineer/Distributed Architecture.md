[[Relational Databases]] management systems, (RDBMSs), offer **distributed architectures** for critical or large-scale workloads where high availability or scalability is important, 

These distributed database architectures involve:
- Clusters of machines interconnected through a network
- Distributing data processing 
- Storage tasks. 
**Advantages:**
- Enhanced scalability
- Fault tolerance 
- Overall performance improvements
**Types of Database Architecture:**
- **Shared Disk Architecture**: Multiple database servers process workloads in parallel, connecting to shared storage (High bandwidth connection), 
	- Ensure workload distribution effectively
	- Ensure scalability when needed
	- Reroute clients when server failures
	- Maintain high availability
- **Shared Nothing Architecture**: Utilizes replication or partitioning techniques to distribute client workloads across nodes, promoting efficient resource utilization and fault tolerance.
- **Combination and specialize architecture** : A combination of those architecture and may **integrate specialized hardware components** (For examples, interconnected hardware management)

**Techniques for Managing Data: **
- **Database Replication**: Involves copying changes from one database server to replicas, improving performance and ensuring high availability during server failures.
- **Sharding**: Partitions large tables into logical segments placed on separate nodes, each shard/node possesses its compute resources, allowing parallel processing and improved performance as workloads increase.