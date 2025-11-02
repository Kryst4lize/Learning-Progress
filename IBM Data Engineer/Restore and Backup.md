- **Definition**: Backup and restore refer to the processes of creating copies of data to protect against loss and restoring that data when needed. This is crucial for maintaining data integrity and availability.

Common Scenarios for Backup and Restore

- **Data Recovery**: Protecting against data loss from unexpected events like system failures or accidental deletions.
- **Data Transfer**: Moving data between different databases, which may involve changing RDBMS or sharing data with business partners.
- **Development and Testing**: Creating copies of data for use in development or testing environments.

Types of Backups

1. **Logical Backup**:
    
    - **Description**: Involves creating a file that contains Data Definition Language (DDL) commands (like `CREATE TABLE`) and Data Manipulation Language (DML) commands (like `INSERT`).
    - **Advantages**:
        - Allows for granular backups (e.g., individual tables or databases).
        - Can reclaim wasted space during the restore process, resulting in a cleaner version of the database.
    - **Disadvantages**:
        - Can be time-consuming for large databases.
        - May impact the performance of other queries during the backup process.
    - **Tools Used**: Import, export, dump, and load utilities.
2. **Physical Backup**:
    - **Description**: Creates a copy of all physical storage files and directories associated with a database, including data files, configuration files, and log files.
    - **Advantages**:
        - Generally faster and smaller than logical backups.
        - Useful for large databases that require quick recovery times.
    - **Disadvantages**:
        - Cannot easily recover individual tables if the backup contains data for multiple objects.
        - The backup file is specific to the RDBMS, limiting restoration to similar systems.
    - **Common Use**: Often used in conjunction with specialized storage systems and cloud environments.

Customization of Backups

- **Backup Scope**: You can choose to back up:
    - Entire databases
    - Specific schemas
    - Individual tables
    - Subsets of data from tables
    - Collections of other database objects
- **Backup Frequency**: You can set how often backups occur based on your needs.

Additional Backup Options

- **Compression**: Reduces the size of backup files, which is beneficial for large databases or remote backups. However, it may increase the time taken for backup and restore operations.
- **Encryption**: Secures backup files to prevent unauthorized access, but may also add time to the backup and restore processes.

Validation and Security

- **Backup Validation**: Always check that backup files are valid and that the restore plan is effective. This is critical to avoid data loss during recovery.
- **Security Measures**: Ensure that the transfer and storage of backup files are secured at the same level as the original database data to protect against breaches.

Summary of Key Takeaways

- Backup and restore processes are essential for data protection and recovery.
- Understanding the differences between logical and physical backups helps in choosing the right approach for your needs.
- Customization options allow for tailored backup strategies that fit specific requirements.
- Always prioritize validation and security to safeguard your data.

---
# Backup Policies

|                    | **Hot Backups**                                                                                                                                 | **Cold Backups**                                                                                                                    |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| **Backup Types**   | - Performed while the database is active.<br>- No impact on user availability.<br>- May cause performance degradation and data integrity risks. | - Require the database to be offline.<br>- Safer for data integrity but affects user availability.<br>- Recovery process is longer. |
| **Backup Storage** | Hot backups are typically stored on available servers                                                                                           | Cold backups are stored on external drives or offline servers                                                                       |

- **Backup Storage**:
    - Hot backups are typically stored on available servers.
    - Cold backups are stored on external drives or offline servers.
- **Backup Frequency**:
    - Depends on data change frequency and business impact of data loss.
    - Example: Less frequent backups for stable data (e.g., product info) vs. more frequent for dynamic data (e.g., customer orders).
- **Backup Scheduling**:
    - Schedule backups outside of peak access hours.
    - Consider full backups on weekends and incremental/differential backups daily.
- **Automation**:
    - Utilize RDBMS features for scheduling or automating backups.
- **Cloud Database Backups**:
    - Options vary by RDBMS and cloud provider (e.g., automated backups, manual backups).
    - Third-party tools are available if built-in options are insufficient.
---
