
- **Purpose of System Objects**:
    
    - System objects are essential for storing metadata about databases, which helps in understanding database performance and configuration.
    - Metadata includes information such as database names, table structures, data types, and access privileges.

- **Types of System Objects**:

| [[Db2]]                                                                                                                                                                                                                     | [[PostgreSQL]]                                                                                                                             | [[MySQL]]                                                                                                                                                    |
| :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------- |
| - Uses a **catalog** to store tables of data about all defined objects in the system.<br>- The **directory** contains internal control data used during normal operations, including database descriptors and access paths. | - Employs a **system catalog**, which is a schema with tables and views that <br>provide metadata about all other objects in the database. | - Utilizes a **system schema** with four system databases: `information_schema`, `mysql`, `performance_schema`, and `sys`, each containing read-only tables. |


- **Configuration Files**:
    
    - Configuration files are crucial for initializing databases with specific parameters during startup.
    - These files store settings such as:
        - Location of data and log files.
        - Port numbers for service connections.
        - Performance-related settings like memory allocation and connection timeouts.
    - Each RDBMS has its own naming conventions for these files:
        - **Db2**: Uses `SQLDBCONF`.
        - **MySQL**: Uses `my.ini` on Windows and `my.cnf` on Linux.
        - **PostgreSQL**: Uses `postgresql.conf`.
- **Modifying Configuration Settings**:
    - For on-premises RDBMS:
        - To change settings, you must stop the database service, edit the configuration file, and then restart the service to apply the changes.
    - For cloud-based RDBMS:
        - Configuration options can be adjusted dynamically through a graphical interface, allowing for real-time scaling of resources without needing to edit files.