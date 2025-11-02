Use this Information Model to depict a fully [[Relational Databases]] schema and data model to fully specify what its need to implement the relational database
# Information Model
## Definition :
- Represents entities abstractly 
- Including their properties , relationships, and operable functions of entities. 
- Provides a high-level and organized view of information,
- Enabling understand the structure and interconnections of data without delving into implementation details
## Aspect:
- Understanding different types of information
- Abstractly complexity of real-world entities
- Encompass broad concept
- Understand and define business concept and rules 
# Data model
## Definition: 
- **Blueprint** for translating conceptual information models into practical database structures. 
- It delves into specifics, defining the **organization, storage, and retrieval mechanisms** **for data** within a database system
## Aspect:
- Data model specify:
	Data elements
	Structures 
	Constraints
	Relationships
- Tailor to a particular DBMS, They define
	Schemas
	Tables
	Columns
	Data types
	Indexes
## Types:
- [[Relational Model]]
	Allow for data independence
	Store data in tables
	Provide logical, physical and storage independence
	Offer **Simplicity, Flexibility and ease of use**
- Entity-relationship model 
	Offer an alternative to the relational model
	Present database as a collection of entities
	Using ERD (entity relationship)
	
## Converting ERD into tables
An entity have many attributes 
	**Entity -> Tables name**
	**Attributes -> Columns** 
# Hierarchical model 
## Definition: 
- Serve as the physical implementation of information system
## Aspect:
- Physically structures in tree format
- Store relationship in the database 
- Struggle with many-to-many relationship (Due to tree format only have 1-1 or 1-many relation ship)
# Concept in database management 
Keyword :
- Logical data dependency: 
	Enables modification to the database structure without affect user data access
	Ex: Altering data types, adding field
- Physical data dependency
	Allow tweaking the internal database organization
	Ex: Change data storage type, Indexing strategy
- Physical storage dependency
	Allow moving or reorganizing data on physical devices without impacting application program processing the data