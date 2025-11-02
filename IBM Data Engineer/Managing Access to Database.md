# Managing Access 
- **Managing Access to Databases**:
    
    - Users need permissions to access database objects after authentication ([[Database Security]].
    - Permissions can be granted to individual Users, Groups or Roles ([[Database Security#Users, groups, roles]])
- **Granting Permissions**:
    
    - Use the SQL `GRANT CONNECT` command to allow a user or group to connect to a database.
    - The `GRANT` command is used to provide specific privileges (e.g., select, insert, update, delete) on tables.
- **Revoking Permissions**:
    
    - The `REVOKE` statement is used to remove previously granted permissions.
    - Permissions can be denied using the `DENY` statement to override any existing grants.
- **Types of Permissions**:
    - Permissions range from basic access (select) to more advanced actions (create, alter, drop).
    - Fine-tuning access is possible by combining user permissions with group or role permissions.	