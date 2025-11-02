**History of MySQL**

- MySQL was developed by MySQL AB, a Swedish company, and named after the co-founder's daughter, Monte Widenius. It was acquired by Sun Microsystems, which was later acquired by Oracle Corporation
- It gained popularity in the late 1990s as part of the LAMP stack, which was foundational for many popular websites.

**Key Attributes of MySQL**
- MySQL is known for its reliability, scalability, and ease of use, making it a widely adopted database solution across various applications.
- It supports multiple operating systems and programming languages, employing standard SQL syntax with additional extensions for enhanced functionality.


**Storage Engines**
- **InnoDB**: The default storage engine, supporting transactions, row-level locking, clustered indexes, and foreign key constraints, providing a balance of performance and reliability.
- **MyISAM**: Suitable for read-heavy workloads with fewer updates, using table-level locking, which may hinder performance in read-write environments.
- **NDB Engine**: Designed for high availability and redundancy, supporting multiple MySQL server instances in a cluster.

**Clustering Options**
- **Clustering Definition**: Clustering connects multiple independent computing resources to work as a unified system.
- **Options**:
    - **InnoDB with Group Replication**: Allows one read-write primary server and multiple secondary servers, with MySQL Router for load balancing.
    - **MySQL Cluster Edition with NDB**: Provides a highly available and scalable solution with multiple server nodes accessing data nodes stored in memory.
--- 
- **MySQL Overview**:
    
    - MySQL is an open-source relational database management system (RDBMS).
    - It allows for the creation, management, and interaction with databases.
    - Available in various deployment options: free community edition, commercial editions, and cloud services.
- **Applications of MySQL**:
    
    - Used by large-scale websites (e.g., Facebook, YouTube, Twitter) for its scalability and reliability.
    - Popular among e-commerce platforms (e.g., Shopify, Magento) for handling product data and transactions.
    - Favored by small and medium-sized businesses for internal databases and CRM systems.
- **Administration Tools**:
    
    - **MySQL Command Line Interface (CLI)**:
        - Facilitates interaction with the MySQL server through commands.
        - Used for server interaction, permissions management, and database monitoring.
    - **MySQL Workbench**:
        - A desktop application that integrates SQL development, administration, and database design.
        - Useful for database developers, administrators, and data analysts.
    - **phpMyAdmin**:
        - A web-based GUI for MySQL database management.
        - Popular among web hosting providers and individual users for its accessibility.
- **Comparison of Tools**:
    - MySQL Workbench is a comprehensive toolkit for database design and development.
    - phpMyAdmin is simpler and more accessible for users with limited technical expertise.
---
# Storage engines in MySQL

A storage engine is a software component that handles the operations that store and manage information in a database. MySQL is unusual among relational databases because it supports multiple storage engines.

Each storage engine has a particular set of operational characteristics, including the types of locks to manage query contention and whether the storage engine supports transactions. These properties have implications for database performance, so choose your storage engine based on the type of data you want to store and the operations you want to perform.

Most applications require only one storage engine for the whole database, but you can specify the storage engine on a table-by-table basis if your data has different requirements.

## Storage engines available in MySQL

|             |                                                                                                                                                                                                                                                                                                                                                                                                      |
| ----------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Engines** | **Description**                                                                                                                                                                                                                                                                                                                                                                                      |
| InnoDB      | - Default storage engine for MySQL 5.5 and later.<br>- Suitable for most data storage scenarios.<br>- Provides ACID-compliant tables and FOREIGN KEY referential-integrity constraints.<br>- Supports commit, rollback, and crash recovery capabilities to protect data.<br>- Supports row-level locking.<br>- Stores data in clustered indexes which reduces I/O for queries based on primary keys. |
| MyISAM      | - Manages non-transactional tables.<br>- Provides high-speed storage and retrieval.<br>- Supports full-text searching.                                                                                                                                                                                                                                                                               |
| MEMORY      | - Provides in-memory tables, formerly known as HEAP.<br>- Stores all data in RAM for faster access than storing data on disks.<br>- Useful for quick lookups of reference and other identical data.                                                                                                                                                                                                  |
| MERGE       | - Treats groups of similar MyISAM tables as a single table.<br>- Handles non-transactional tables.                                                                                                                                                                                                                                                                                                   |
| EXAMPLE     | - Allows developers to practice creating a new storage engine.<br>- Allows developers to create tables.<br>- Does not store or fetch data.                                                                                                                                                                                                                                                           |
| ARCHIVE     | - Stores a large amount of data.<br>- Does not support indexes.                                                                                                                                                                                                                                                                                                                                      |
| CSV         | - Stores data in Comma Separated Value format in a text file.                                                                                                                                                                                                                                                                                                                                        |
| BLACKHOLE   | - Accepts data to store but always returns empty.                                                                                                                                                                                                                                                                                                                                                    |
| FEDERATED   | - Stores data in a remote database.                                                                                                                                                                                                                                                                                                                                                                  |

## Commands for working with Storage Engines

If you’re a DBA working with storage engines in MySQL, you should be familiar with the following common commands.

### SHOW ENGINES

Displays status information about the server’s storage engines. Useful for checking whether a storage engine is supported, or what the default engine is.

`mysql> SHOW ENGINES;`

![Screenshot shows status information of server storage engines](https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-DB0231EN-SkillsNetwork/Readings/images/showengines.png)

### CREATE TABLE

Creates a table using the storage engine specified in the ENGINE clause, as shown in the following examples:

`CREATE TABLE Products (i INT) ENGINE = INNODB;`

`CREATE TABLE Product_Codes (i INT) ENGINE = CSV;`

`CREATE TABLE History (i INT) ENGINE = MEMORY;`

If you do not specify the `ENGINE` clause, the `CREATE TABLE` statement creates the table with the default storage engine, usually **InnoDB**.

### SET

For databases with non-standard storage needs, you can specify a different default storage engine using the set command.

Set the default storage engine for the current session by setting the default_storage_engine variable using the SET command. For example, if you are creating a database to store archived data, you can use the following command:

`SET default_storage_engine=ARCHIVE;`

To set the default storage engine for all sessions, set the default-storage-engine option in the my.cnf configuration file.

### ALTER TABLE

You can convert a table from one storage engine to another using an `ALTER TABLE` statement. For example, the following statement set the storage enigne for the Products table to Memory:

`ALTER TABLE Products ENGINE = MEMORY;`

**InnoDB** is suitable for most data storage needs but setting and working with different storage engines in **MYSQL** gives you more control over how your data is stored and accessed. Using the most appropriate storage engine for your data brings operational benefits like faster response times or efficient use of available storage.