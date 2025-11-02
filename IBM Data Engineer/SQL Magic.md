Overview of SQL Magic in Jupyter Notebooks

- **Magic Statements**: Special commands in [[Jupyter Notebooks]] that enhance functionality but are not standard Python code. They help solve common data analysis problems.

Types of Magic Statements

1. **Line Magics**:
    
    - Prefixed with a single percentage character (`%`).
    - Operate on a single line of input.
    - Examples:
        - `%pwd`: Prints the current working directory.
        - `%ls`: Lists all files in the current directory.
        - `%history`: Shows command history.
        - `%reset`: Resets the namespace by removing all user-defined names.
        - `%who`: Lists all variables in the namespace.
        - `%whos`: Provides detailed information about all variables.
        - `%matplotlib inline`: Displays matplotlib plots within the notebook.
        - `%timeit`: Times the execution of a single statement.
2. **Cell Magics**:
    - Prefixed with two percentage characters (`%%`).
    - Operate on multiple lines of input and can execute code in different programming languages.
    - Examples:
        - `%%html`: Allows writing HTML code in a cell.
        - `%%javascript` or `%%js`: Executes JavaScript code.
        - `%%bash`: Executes bash commands.

Using SQL Magic

- To use SQL Magic, you need to install the `iPython_SQL` library:
    
    ```python
    !pip install iPython_SQL
    ```
    
- Load the SQL extension in your notebook:
    
    ```python
    %load_ext sql
    ```
    
- Establish a connection to the SQL server:
    
    ```python
    %sql sqlite:///HR.db
    ```
    
- After establishing the connection, you can run SQL queries using:
    - Line magic: `%sql`
    - Cell magic: `%%sql`

Example of SQL Magic Usage

- To display the contents of an employee table in the HR database, you would first connect to the database and then execute your SQL query.