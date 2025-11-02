**Overview of PostgreSQL:**
- **Definition**: PostgreSQL is an open-source object-relational database management system (ORDBMS).
- **Origin**: It originated from the POSTGRES project at the University of California over 30 years ago and has been utilized in various industries, including financial services, aviation, and medicine.
**Historical Development:**
- **Postgres95**: Released in 1994, it included an [[Struct Query Language (SQL)]] interpreter and was later renamed PostgreSQL.
- **Current Usage**: PostgreSQL is widely used in web applications as part of the LAPP stack (Linux, Apache, PostgreSQL, PHP).

**Key Features**

- **Open Source**: Being open-source allows users to modify and distribute the source code to meet specific business needs.
- **Object-Relational**: Supports object-oriented programming features like inheritance and overloading, simplifying design and promoting reuse of database objects.
- **Compatibility**: Compatible with most operating systems and supports multiple programming languages, making it easy to integrate with web applications.
- **Standards Compliance**: Adheres to ANSI-SQL standards, ensuring a robust relational database structure.

**Data Handling Capabilities**

- **Relational Constructs**: Supports standard relational database features such as keys, transactions, views, functions, and stored procedures.
- **NoSQL Functionality**: Offers support for JSON (structured data) and HSTORE (non-hierarchical data), allowing for flexible data management.

**Replication and High Availability**

- **Synchronous Replication**: Involves two nodes where changes made on Node 1 are immediately applied to Node 2, ensuring data consistency and high availability.
- **Asynchronous Replication**: A master node distributes changes to multiple read-only replicas, enhancing scalability. If the master node fails, one of the replicas can take over.
- **Commercial Additions**: Options like EDB PostgreSQL replication server provide multi-master read/write replication for greater flexibility.

**Scalability Enhancements**

- **Partitioning**: Allows large tables to be split into smaller sections, improving query performance.
- **Sharding**: Enables horizontal partitioning across multiple remote servers, facilitating the management of larger datasets.
---
- **PostgreSQL Overview**:
    
    - An open-source object-relational database management system known for reliability and flexibility.
    - Supports both relational and non-relational data types.
    - Commonly used for Online Transaction Processing (OLTP), data analytics, and geographic information systems.
- **Deployment Options**:
    
    - **Local Installation**: Can be installed on macOS, UNIX, or Windows servers.
    - **Virtualization and Containerization**: Allows self-management in virtual machines or containers for efficient resource use.
    - **Cloud Solutions**: Integrates with managed services like Amazon RDS, Google Cloud SQL, Microsoft Azure, and IBM cloud databases.
- **Connection Tools**:
    
    - **Psql**: Command-line interface for users comfortable with text-based interactions.
    - **pgAdmin**: Open-source graphical interface that simplifies database management with a user-friendly GUI.
    - Other commercial options include Navicat and DBeaver.
- **Psql Features**:
    
    - Facilitates connections to PostgreSQL servers and allows real-time execution of SQL commands.
    - Offers features like autocompletion and syntax highlighting.
- **pgAdmin Features**:
    
    - Comprehensive platform for database interaction, including creating databases, tables, and managing database objects.
    - Includes a query tool for executing SQL commands and viewing results.
    - Features an Entity Relationship Diagram (ERD) tool for visual database design.
- **Query Execution**:
    - The query tool allows users to input SQL queries and view results, with tabs for execution plans, messages, and notifications.
---
## Creating and Loading data
- Using psql :
```sql
--- CREATE table 
CREATE DATABASES employees;
\connect employees;
CREATE TABLE employees_details(name VARCHAR(20), startdate DATE, salary DECIMAL)
--- RESTORE (terminal)
psql file_dest < backup.sql
--- BACK UP (terminal)
psql file_dest > backup.sql
```
		- Using creating a database in pgAdmin: 
![[pgadmincreatedatabase.png]]
