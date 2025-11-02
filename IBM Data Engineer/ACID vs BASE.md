[[Relational Databases]] [[Non-relational Databases]] [[NoSQL]]

ACID Model:
- **Acronym Breakdown**:
    - **Atomic**: All operations in a transaction succeed, or none do (rollback).
    - **Consistent**: Data integrity is maintained after transactions.
    - **Isolated**: Transactions do not interfere with each other.
    - **Durable**: Completed transactions persist despite failures.
- **Use Cases**:
    - Primarily used in **relational databases**.
    - Ideal for applications requiring high data integrity, such as **financial institutions** (e.g., money transfers).
BASE Model:
- **Acronym Breakdown**:
    - **Basically Available**: Focuses on data availability rather than immediate consistency.
    - **Soft State**: Data may change over time without immediate consistency.
    - **Eventually Consistent**: Data will become consistent over time, but not immediately.
- **Use Cases**:
    - Common in **NoSQL databases**.
    - Suitable for applications needing high availability, such as **social media platforms** and services like **Netflix** and **Uber**.
Key Differences:

- **ACID** emphasizes data consistency, making it suitable for critical transactions.
- **BASE** prioritizes availability, allowing for flexibility in data consistency.

Both models have their advantages and disadvantages, and their applicability depends on specific business needs.