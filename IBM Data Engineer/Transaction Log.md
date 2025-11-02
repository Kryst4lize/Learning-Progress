# Transaction Log
- **Purpose of Transaction Logs**:
    - They track all transactions ([[Struct Query Language (SQL)]]) that modify the database, aiding in recovery ([[Restore and Backup]]) from accidental deletions or system failures.
- **Recovery Process**:
    - Involves using a backup and transaction logs to restore the database to a consistent state.
    - The process called "roll forward recovery" applies committed transactions from logs to the restored database.
- **Storage Recommendations**:
    - It's best practice to store transaction logs separately from database objects to enhance performance and recoverability.
    - Some RDBMSs allow automatic mirroring of logs for better recoverability.
- **Logging Configuration**:
    
    - Transaction logging is enabled by default in some systems (e.g., Db2, SQL Server) but may need manual configuration in others (e.g., MySQL).
- **Log Formats**:
    
    - Transaction logs are typically in binary format and may require specialized tools to view (e.g., `mysqlbinlog` for MySQL).
- **Log Record Structure**:
    - Each log entry generally includes:
        - Log transaction ID
        - Database record type
        - Log sequence number
        - Previous log sequence number
        - Details of the changes made