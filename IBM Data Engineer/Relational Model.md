## Concept
Involve two fundamental concept
- Set
- Relation
### Sets
A set is a collection of unique elements without a specified order, comprising items of a similar type, usually curly braces denote sets with the elements listed inside or described using set builder notation with a condition
- High application in Math , Algebra, Geometry, Probability
**Operations:** 
- Membership : $a\in{A}$ $\longrightarrow$ An object belong to set A
- Subset: $A\subseteq{B}$ $\longrightarrow$ Every element of A in B 
- Union: $A\cup{B}$ $\longrightarrow$ The set of elements in A, in B
- Intersection: $A\cap{B}$ $\longrightarrow$ The set of elements have common in both A and B 
- Difference: $A \backslash B$ $\longrightarrow$ Elements in A but not in B
- Empty: $\varnothing$ $\longrightarrow$ Empty set
- Power set: $P(A)$ $\longrightarrow$  Set of all possible subsets of A
- Universal set: $U$ $\longrightarrow$ Contains all considered objects
### Relation
Relation is a mathematical concept based on sets describe the connection between sets, and crucial in set theory and logic 
**Aspect**:
-  Binary relation : Establish a connection between two elements in a set 
	For examples : ${3,5} \in A, 3<5$
- Ordered pair : Subset of the Cartesian product and represent binary relation
**Properties:**
- Reflexivity: $\forall x . R(x,x)$
- Transitive: $\forall x,y,z. R(x,y)\wedge R(y,z) \Rightarrow R(x,z)$
- Asymmetric: $\forall x,y . \rightharpoondown R(x,y)  \vee   \rightharpoondown R(y,x)$ 
Using Venn diagram
- Visual presentation of logical relationship between sets 
### Relation schema
Specifies:
- The name of a relation 
- Name and type of each columns
### Relation instance
- Real world data stored in table
## Constraints
- **Relational Model Constraints**: These are rules that ensure data integrity in a relational database.
    
- **Types of Constraints**:
    
    - **Entity Integrity Constraint**: Ensures that the primary key is unique and cannot have null values. [[IBM/IBM/Indexes]] was use to implement that
    - **Referential Integrity Constraint**: Defines relationships between tables, ensuring that foreign keys correctly reference primary keys.
    - **Semantic Integrity Constraint**: Enforces the correctness of the data's meaning within the database.
    - **Domain Constraint**: Checks that attribute values fall within a valid range or set of values.
    - **Null Constraint**: Ensures that certain attributes cannot have null values.
    - **Check Constraint**: Limits the values that can be entered for a specific attribute based on defined criteria.

