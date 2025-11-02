[[Struct Query Language (SQL)]] [[Relational Databases]]
- **ACID Transactions**:
    - ACID stands for:
        - **Atomic**: All changes must be successful or none at all.
        - **Consistent**: Data must remain in a consistent state before and after the transaction.
        - **Isolated**: No other processes can change the data while the transaction is in progress.
        - **Durable**: Changes made by the transaction must persist.
- **Transaction Process**:
    
    - A transaction is an indivisible unit of work that can consist of one or more SQL statements.
    - To start a transaction, the command `BEGIN` is used (implicitly in db2 on Cloud).
    - After executing SQL commands, you can either:
        - **COMMIT**: Save all changes if successful.
        - **ROLLBACK**: Undo all changes if any command fails.
- **Real-World Example**:
    
    - When making a purchase (e.g., buying boots), multiple SQL statements are executed:
        - Update the buyer's account balance.
        - Update the store's account balance.
        - Update the inventory.
    - If any of these updates fail, the entire transaction should fail to maintain data consistency.
- **SQL Integration**:
    - SQL commands can be called from various programming languages (e.g., Java, Python) using specific database access APIs.