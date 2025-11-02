- **Importance of Database Design**: A well-designed [[Relational Databases]] or [[Non-relational Databases]] is crucial for the success of data-driven projects, impacting data integrity, performance, and user satisfaction.
- **Database Design Process**:
    1. **Requirements Analysis**:
        - Collaborate with stakeholders to gather business information.
        - Identify base objects and their relationships (e.g., a person borrowing a book).
        - Use methods like reviewing existing data and interviewing users.
    2. **Logical Design**:
        - Transform requirements into entities, attributes, and relationships.
        - Ensure objects are represented as entities and characteristics as attributes.
        - Consider normalization to reduce data redundancy.
    3. **Physical Design**:
        - Define how the database will look, including data types, naming rules, and constraints.
        - Use tools like ERD designers to create entity relationship diagrams.
- **Normalization**:
    - Aim to achieve the third normal form for transactional efficiency in OLTP systems.
    - Create distinct entities for complex relationships (e.g., a loan entity for borrowing books).
- **Tools**:
    - Utilize tools like pgAdmin's ERD tool for designing ERDs and generating SQL scripts.