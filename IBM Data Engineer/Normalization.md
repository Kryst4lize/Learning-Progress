Normalization Overview

- **Purpose**: Normalization organizes [[Data]] to reduce redundancy and improve data integrity.
- **Process**: Involves dividing larger tables into multiple related tables.

Normal Forms

1. **First Normal Form (1NF)**:
    - Each row must be unique.
    - Each cell must contain only a single value.
    - Example: A book table should have separate rows for different formats of the same book.
2. **Second Normal Form (2NF)**:
    - Must be in 1NF.
    - Separate groups of values that apply to multiple rows into new tables.
    - Example: Split book information from format information to eliminate data duplication.
3. **Third Normal Form (3NF)**:
    - Must be in 1NF and 2NF.
    - Eliminate columns that do not depend on the primary key.
    - Example: Create a separate publisher table to store publisher details that are not directly related to the book ID.

Additional Notes

- Higher normal forms (like **Boyce-Codd Normal Form**) exist but are less commonly used.
- Normalization is crucial for transactional systems (OLTP) to efficiently process and store transactions.
- In analytical systems (OLAP), data may be denormalized for performance reasons.