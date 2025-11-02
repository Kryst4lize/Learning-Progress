## Primary Keys

- **Definition**: A primary key is a unique identifier for each row in a table.
- **Selection**:
    - It can be a naturally occurring unique attribute (e.g., `book_id`, `employee_id`).
    - If no unique attribute exists, you can create a new column to serve as the primary key.
    - A combination of columns can also be used as a primary key if they uniquely identify each row (e.g., `site_id` and `employee_id`).
- **Creation**:
    - Can be defined when creating a table using the `PRIMARY KEY` clause in the `CREATE TABLE` statement.
    - Can also be added to an existing table using the `ALTER TABLE` statement with the `ADD PRIMARY KEY` clause.

## Foreign Keys

- **Definition**: A foreign key is a column in a table that links to the primary key of another table, establishing a relationship between the two tables.
- **Example**: In a library database, a `copy` table may reference the `book_id` from a `book` table to indicate which books are owned.
- **Creation**:
    - Can be defined during table creation using the `FOREIGN KEY` clause.
    - You can specify the referenced table and primary key column.
- **Referential Integrity**:
    - Ensures that the foreign key value must exist in the referenced primary key table.
    - You can define actions for updates and deletions (e.g., no action, cascade delete, or set to null).