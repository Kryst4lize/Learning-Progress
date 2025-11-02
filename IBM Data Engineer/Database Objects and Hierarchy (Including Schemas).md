# Database Hierarchy 
This is a hierarchy of a [[Relational Databases]]: 
```markdown-tree
Instance
	Database
		Schema
			Tables
			Constraints
			Indexes
			
```
## Database Objects
- **Instances**: An instance is a logical boundary for organizing databases and their objects. Multiple databases can exist within a single instance.
- **Schemas**: A schema is a logical grouping of database objects that helps prevent naming conflicts and organizes data effectively.
	- User schemas: contain database objects like tables, views, functions 
	- System schemas: contain configuration and metadata for the database
- **Database Objects**: These include **tables, views, indexes, functions, triggers, and packages**, which are essential for data storage and management. [[Relational Databases]]
	- **Tables**: Store data in rows and columns.
	- **Constraints**: Enforce rules on data (e.g., uniqueness).
	- **Indexes**: Improve performance and ensure data uniqueness.
	- **Keys**: Uniquely identify rows in tables and define relationships.
	- **Views**: Represent data from one or more tables without permanent storage.
	- **Aliases**: Alternative names for database objects.
	- **Triggers**: Actions performed in response to changes in a table.
	- **Log Files**: Store transaction information.
- **[[Constraints]] and [[IBM/IBM/Indexes]]**: Constraints enforce rules on data (e.g., uniqueness), while indexes improve data retrieval performance.
