Overview of Database Security
[[Relational Model]] [[Non-relational Databases]]
- **Importance**: Ensuring the security of data in databases is crucial for database management. It involves identifying risks and applying security measures at all system levels.

Security Levels

1. **Physical Security**:
    
    - Assess who has access to the server location.
    - Implement security measures for on-premise servers or rely on cloud providers for managed environments.
2. **Operating System Security**:
    
    - Regularly patch the operating system with tested updates.
    - Harden the OS configuration to reduce vulnerabilities.
    - Continuously monitor for unauthorized access.
3. **RDBMS Security**:
    - Apply updates and utilize all available security features.
    - Limit administrative privileges to a small group of trusted users.

Authentication and Authorization

- **Authentication**:
    
    - Process of verifying user identity (e.g., using a username and password).
    - Some systems allow external authentication methods (e.g., PAM, LDAP, Kerberos).
- **Authorization**:
    - Granting permissions to users for accessing database objects.
    - Use roles to assign privileges to groups of users, allowing for easier management.

Principle of Least Privilege

- Only grant users access to the minimum amount of data necessary for their tasks.
- This reduces the risk of unauthorized access to sensitive information.

Monitoring and Auditing

- Track user access and actions within the database.
- Analyze this data against your security plan to identify potential gaps or threats.

Encryption

- Adds an additional layer of security to protect data.
- Important to comply with industry regulations regarding encryption standards. ([[Govern and Compliance]])
- Consider the performance impact of encryption and decryption processes on operations.

Application Security

- Ensure that applications interacting with databases are secure.
- Regularly test and monitor for vulnerabilities, such as SQL injection attacks.
- ---
# Users, groups, roles
## Users

- **Definition**: A database user is an account that has permission to access certain database objects.
- **Creation**: Users can be created directly within the database or authenticated externally (e.g., using operating systems or identity management services like Kerberos or LDAP).
- **Permissions**: When a user is created, they usually have minimal permissions unless they are the creator of the database.

User Management

- **Storage**: Usernames are stored in system or catalog tables, which should not be edited directly.
- **Management Tools**: RDBMSs provide SQL commands or user interface tools for managing users.

## Groups

- **Definition**: User groups are logical collections of users that simplify management.
- **Implementation**:
    - In systems like Postgres, groups are defined within the database.
    - In SQL Server and Db2, database groups can be mapped to administrative groups in the operating system.
- **Use Case**: Useful for managing user access, especially in environments like Amazon RDS, where VPC security groups can be utilized.

## Roles

- **Definition**: Database roles are similar to groups and provide a set of permissions to users assigned to that role.
- **Predefined Roles**: Many RDBMSs come with predefined roles (e.g., database owner, backup operator) that can be assigned to users.
- **Custom Roles**: Users can create custom roles tailored to specific job functions (e.g., a salesperson role with access to relevant tables).

## Security Management

- **Simplification**: Assigning permissions to groups or roles rather than individual users simplifies security management tasks.
- **Efficiency**: If a job role changes or a new user joins, it’s easier to update permissions for a group or role than to adjust them for each individual user.

## Principle of Least Privilege

- **Guideline**: When assigning users to groups or roles, only grant the permissions necessary for their job functions.
- **Reassessment**: Regularly review role permissions to ensure they are appropriate and create more granular roles if needed.
---
