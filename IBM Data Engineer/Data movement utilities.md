[[Relational Model]] [[Database Architecture]] 
Reasons for Data Movement: 
- **Database Population**: Initial data entry into databases and tables.
- **Development and Testing**: Creating duplicate databases for testing purposes.
- **Disaster Recovery**: Making snapshots of databases to recover from failures.
- **Data Integration**: Generating new tables using data from external sources or files.
- **Updating Existing Tables**: Adding data to one or more existing tables.

Methods of Data Movement

1. **Backup and Restore**:
    
    - **Backup**: Creates a file or set of files that encapsulate all database objects and their data.
    - **Restore**: Recreates the original database from backup files.
    - **Preservation**: Backups include schemas, tables, views, user-defined data types, functions, stored procedures, constraints, triggers, security settings, and relationships.
2. **Import and Export**:
    
    - **Import**: Reads data from a file and performs insert statements into the target table.
    - **Export**: Retrieves data from a designated table and stores it in a chosen file.
    - **Interfaces**: Most databases provide command line utilities, management APIs, and graphical tools for these operations.
3. **Load Utilities**:
    - **Performance**: Load utilities can outperform import utilities by directly formatting pages into the database.
    - **Limitations**: They do not perform referential or table constraint checking, which may be necessary in some cases.

File Formats for Data Movement

- **Common Formats**:
    - **DEL**: Delimited ASCII, allows data exchange among various database and file managers.
    - **ASC**: Nondelimited ASCII, imports data from applications generating flat text files.
    - **PC/IXF**: Preferred method for data exchange within the database manager.
    - **JSON**: Increasingly supported for data import/export due to its popularity in web services.