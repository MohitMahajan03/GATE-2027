# Basics of DBMS

## Introduction

### Introductory Questions

1. What is DBMS?
    * It is a software which is used to 
    * Ordering related data and organizing it into a meaningful collection.

2. What is a relational model?
    * In relational model, data is organized in form of a table

3. If filesystem is already present, why did you need DBMS?
    * Filesystem is good only to store small amounts of data
    
#### File system vs DBMS

* DB files are stored in the blocks of the disk
* The unit of transfer between main memory and secondary memory is 1 block
* File system I/O cost is high. Time consumed to transfer is large.
* Also, trying to access a record in the file system will take up lot of time.
* Concept of indexing is used in DBMS to reduce the I/O cost.
* An index file is created by DBMS that maps index to record, for faster retrieval
* Very difficult to access file system without knowing the structure. Also poses security threat if files shared with users
* This security threat is addressed by using the 3 tier architecture of DBMS
* This architecture provides data abstraction and data independence
* In file system, we always require the file/record in the main memory.
* In File system locks are acquired at file level -> Low concurrency.
* The lock is applied at record level in DBMS -> High concurrency

#### Terms used

* I/O cost for an access is defined in terms of number od memory blocs transferred from secondary memory to main memory

### DBMS Architecture

1. 1-tier architecture    -> refer 1-tier-architecture.png
    * Contains single computer, single level
    * It contains DB server and user API
    * Is not so secure

2. 2-tier architecture    -> refer 2-tier-architecture.png
    * Follows client server architecture
    * Consists of a 2 computer system
    * Client side consists of the User APIs
    * Server side contains DB server + database
    * Better security that 1-tier architecture, but not enough

3. 3-tier architecture    -> refer 3-tier-architecture.png
    * Follows client server architecture
    * Consists of 3 layers
    * client reaches out to DBMS Server
    * The server then processes the query then to the Database
    * Data Abstraction and Data independence is achieved.

#### Terms used

* Data abstraction: Hiding the internal details from the external user
* Data independence: Different levels of abstraction provides data independence
    * So changes made in a specific level, should not affect other levels.

### Database Models

* DB models are used to organize the information in different ways

1. Flat file model
2. Relational model
    * Data is stored in the form of tables called relations
    * E.F.Codd defined 13 different rules for a database to be called relational database.

3. Hierarchical model
4. Network model
5. Object oriented model

### Relational Model

#### Terms used

* Relation: The table structure used to store data
* Attributes/Fields: Columns present in the table
* Tuples/records: One single row of the entire relation/table
* Degree/Arity: Degree is number of attributes in a relation.
* Cardinality: Number of records in a relation
* Relational Schema: Abstract details of the relation
* Relational instance: What is relation/table at given instance

### Keys in RDBMS

* Keys are used to ensure data integrity and consistency and they are used to access records
* They are a set of attributes in the relation to identify each record uniquely.

* Types of keys
    1. Candidate key
        * The minimal set (if nothing can be removed from the key set without losing it's property of being a key) of attributes that make up a key is a candidate key.
        * A relation can have more than 1 candidate key
        * Candidate keys CAN take null values
        * A relation can have atmost 1 primary key

    2. Primary key
        * The values of Primary key are always unique and NOT null
        * Primary key is also a candidate key
    3. Alternate key
        * The candidate keys except Primary Key are all Alternate keys
    4. Super key
        * Every key of a relation is a Super key
        * They may or may not be minimal
        * All candidate keys are part of super key set
    5. Foreign key
        * A set of attributes that references Primary key or alternate key of the same relation or different relation is called as Foreign key
        * The relation that has Foreign key is the referencing relation, and the relation with the original primary key is the referenced relation.

    ``` 
    Referential integrity constraint, is a situation where there exists a Foreign key value for which there is no primary key to refer to
    ```

    6. Simple key
        * A key which is formed using single attribute is a simple key
    7. Composite key
        * These keys are formed using more than 1 attribute
    8. Prime attribute
        * All attributes belonging to the set of candidate key are called prime attributes
    9. Non-Prime attributes
        * Attributes not belonging to the set of candidate key is called Non-prime attributes

### Referential integrity Constraint

* This constraint occurs during deletion and updation of records in the following situations

1. On delete no action -> On deletion of primary key, no action to be taken is enforced on parent table by referencing table
2. on delete cascade -> On deletion of primary key, delete all data with respect to primary key in referencing table
3. On delete set NULL -> On deletion of primary key, set Foreign key with respect to the referenced records as NULL
4. On update no action -> On update of primary key, no action to be taken is enforced on parent table by referencing table
5. On update cascade -> On update of primary key, delete all data with respect to primary key in referencing table
6. On update set NULL -> On update of primary key, set Foreign key with respect to the referenced records as NULL

### Functional Dependency

* It defines the relationship between attributes, it is represented as X -> Y
* Given a relation R(A, B, C, D, E), then FD represents relationships, like
    * A -> B
    * BC -> D
    * C -> E

#### Armstrong's Axioms

1. Reflexivity: If X is a superset of Y
2. Augmentation: If X -> Y exists then ZX -> YZ
3. Transitivity: If X -> Y and Y -> Z then X -> Z 

4. Decomposition: if X -> YZ then X -> Y and X -> Z vice versa is not true!
5. Union: If X -> Y and A -> B then XA -> YB 

#### Trivial FD

* FD X -> Y is called trivial iff X is a superset of Y

#### Non Trivial FD

* FD X -> Y is called a non-trivial FD if set X intersection st Y is NULL.

### Normalization

* It is the process of reducing the redundancy from any relations so that it eliminates anomalies and ensures data integrity and efficient database operations.
* These anomalies include -> insertion anomaly, Deletion anomaly, updation anomaly.

1. First normal form
    * No composite attribute should be present and no multivalued attribute should be present
    * So, all values must be atomic -> only 1 data point per attribute per tuple
2. Second normal form
    * The relation must be in 1 NF and must not contain any partial dependency
    * if Proper subset of candidate -> Non prime attribute, then partial dependency exists in that relation
3. Third normal form
    * The relation should be in 1 NF and every non trivial Functional dependency X -> Y should have X as a super key or Y as a Prime Attribute
4. Boyce Codd normal form
    * For a relation to be in BCNF, in every non-trivial functional dependency X->Y, X must be a suoer key
5. Fourth normal form
    * It is related to multivalued dependency
6. Fifth normal form
    * It is related to lossless join

### Join Operations

* Join operatoins are used to join tables based on some conditions

1. Cross join (X) -> Refer cross_join.png
    * It combines each row from the first table with each row from the second table
    * There are no join criteria

#### Types of join operations
1. Inner join
    * In an inner join, includes only those tuples that satisfy the matching criteria
    1. Theta join
        * Theta can use any conditions in the selection criteria
        * So first cross join takes place, and then the tuples are filtered based on the condition
    2. Equi join
        * A equi join is a theta join using the equality operator. It always works on equality condition
    3. Natural join
        * Natural join is performed on the equality condition on all attributes between the relatoins
        * A natural join removes the duplicated columns involved in the equality comparison so only one of each compared column names remains.
2. Outer join
   * In outer join along with the tuples that satisgy the matching criteria we also include tuples that do not match the criteria (from left side, or right side or from both the relations)
   1. left outer join -> refer left_outer_join.png
        * All tuples of natural join of the relation and from the left relations are included during the join even though they failed the join condition
   2. Right outer join -> refer right_outer_join.png
        * All tuples of natural join of the relation and from the right relations are included during the join even though they failed the join condition
   3. Full outer join -> refer full_outer_join.png
        * All tuples of R natural join S and the tuples from R and S that failed the join condition

 
### Decomposition of a relation -> Refer decomposition.png

* Splitting a relational table into smaller sub relation is called decompostion
* For a decomposition to be called a correct decomposition, following properties must be satisfied

1. Lossless join decompostion
    * On natural join of the decomposition, the entire relation should be get back 
2. Dependency preserving, if it is a subset

### Commands in SQL

* Create table -> create new table
* Alter table -> add, or remove attributes
* Drop table -> deletes the table
* Insert -> inserts new data
* Delete -> delete record
* Update -> updates the tuple
* Select -> extracts data from the database
* truncate -> delete all rows from the table, but keeps the structure
* count -> counts the number tuples in the valid condition. considers NULL values
* sum -> Calculates the sum of a numerical column in the database. Ignores NULL values
* avg -> Calculates average of a numerical column. Ignores ULL values
* min -> gets min values
* max -> gets min values

* NOTE:
    * We cannot select any attribute in SELECT Clause along with aggregate function until those attributes are in GROUP BY clause.
    * If Aggregate function is along with GROUP BY clause, then aggregate function is applied on each group
    * WHERE condition is applied on each tuple whereas HAVING condition is applied on each group
    * HAVING condition can be used without GROUP BY, then HAVING condition is applied onto all tuples, which indirectly acts like a WHERE clause

### SQL Clauses

* Refer sql_clauses.png

### Order of Execution

1. From
2. Where
3. Group By
4. Having
5. Select
6. Order By

### Nested Queries

* It is Query inside query, They are of 2 types

1. Independent Nested Query
    * If the inner query does not use any attribute from the outer query, then it is an independent Nested Query
2. Correlated Nested Query
    * If the inner query requires a specific attribute defined in the outer query for processing, then it is called as a Correlated query

Refer -> order_of_execution.png

### Operators

* These are boolean operators that returns true or false

1. IN:
    * Returns true if tuple under consideration is present in set of tuples
    * Complement of IN is NOT IN. 
2. ANY:
    * Will work with other comparison operators. Returns true only if atleast one tuple from the set of tuples satisfy the comparison condition with respect to given tuple.
    * "IN" is equivalent to "=ANY"

3. ALL:
    * ALL operator works with arithmetic operators
    * All the tuples should be true for ALL to return true, even if 1 tuple fails condition, then False is returned
    * It will always return true if inner query result is empty
    * "NOT IN" is equivalent "<> ALL"

4. EXISTS:
    * Return true if there are any inner query results, and false if there are no tuples in the inner query result
    * Complement of "EXISTS" is "NOT EXISTS"

### Transaction

* Transaction is a sequence of logically related operations
* EX: Transfer 500 from Account A to Account B
```
    1. Read current bank balance of A
    2. if A>=500
    3. A = A - 500
    4. Write A
    5. Read B
    6. B = B + 500
    7. Write B
    8. Commit
```

### Schedule

* Time ordered sequence of operations of two or more transactions called schedule
* Ex:
```
S1: R1(A), R2(A), W1(A), R1(B), W1(B), R2(B)

T1      |      T2
R1(A)   |
        |      R2(A)
W1(A)   |
R1(B)   |
W1(B)   |
        |      R2(B)
```

* There are 2 types of Schedules
    1. Serial Schedule: Start the execution of a new transaction only after the complete execution of previously started transaction. Output of schedule is always correct but throughput is low
    2. Concurrent Schedule: Operations of 2 or more transactions can execute in interleaved manner. Throughput is increased, But output may be incorrect.
* Equivalent Schedules: For 2 schedules to be equivalent, every read must be same in both the schedules and final data update of every item should be similar in both the schedules
* Serializable Schedule : Iff a schedule is equivalent to at least one of the serial schedule (over the transactions)
* Non-Serializable Schedule : If the schedule is not equivalent to any of the serial schedule then it is a non-serializable schedule.

```

Learn some examples

Refer serialization.png

```

* Classifications of schedules
    1. Irrecoverable
    2. recoverable -> cascade and rollback, lost - update is possible
    3. Cascadeless rollback recoverable -> no cascade rollback, lost - update is possible
    4. Strict recoverable schedule -> no cascade rollback and no lost update
    5. Conflict Serializable
    6. View Serializable

### ACID properties

* ACID Properties must be followed for integrity of the database transactions

1. A -> Atomicity
    * Either execute all operations of the transaction or none of them
    * Recovery management component must be used if a transaction fails to maintain atomicity
2. C -> Consistency
    * Before and after execution of transactions the database should be consistent
3. I -> Isolation
    * If 2 or more transactions are exeuting concurrently, then they all must be unaware of each other.
    * There should be no influence of 1 transaction over the other.
    * To ensure isolation condition, a non-serializable schedule should never be allowed execute.
4. D -> Durability
    * All updates performed by a successful transaction must persist even if system fails in later point of time.


### Index Files

* Index files are used to reduce IO cost
* Categories of Indices
    1. Dense index -> 1 index entry per record is maintained
    2. Sparse index -> For a set of records there will be only 1 entry per record file
* Types of indices
    1. Primary Index -> generally sparse
        * When Search key attribute values are unique in database file and records of the file are sorted based on attribute values
    2. Clustering Index -> always sparse
        * When search key attribute values are not unique
    3. Secondary Index -> always dense
        * Search key attribute values may or may not be unique, but records of the file are not ordered based on search key values.
* If DB file is too large, and single level index file does not provide significant improvement, with respect to reduction in IO cost, then we may use multi level index

### B tree

* The order of a node of a B tree is defined as maximum number of child pointer it can have
* If 'm' is the order of a node of B tree then.
    1. maximum number of child pointer a node can have = m
    2. maximum number of keys a node can have = m
    3. minimum number of child pointer a non root node can have = [m/2]
    4. minimum number of keys a non-root node can have = [m/2] - 1
    5. minimum number of child pointer a root node can have = 2
    6. minimum number of keys a root node can have = 1

### B+ tree

* In B+ tree order of a leaf node and  order of a non-leaf node is defined differently.
* Order of a non leaf node is defined as the maximum number of child pointer a non leaf node can have
* order of a leaf node of a B+ tree is defined as maximum number of keys a leaf node can have
* In B tree all nodes will store key values and record pointers, corresponding to those key values
* In B+ tree internal node will only hold the key values, and those key values are dummy key values used just for search operation. All keys with record pointers are stored in the leaf nodes


### Home work

#### L2

1. Cover Functional dependency

```
A functional dependency occurs when the value of one attribute (or a set of attributes) uniquely determines the value of another attribute. This relationship is denoted as:

X → Y

Here, X is the determinant, and Y is the dependent attribute. This means that for each unique value of X, there is precisely one corresponding value of Y.

Example:
StudentID -> StudentName
StudentID -> StudentAge
```

* Trivial Functional Dependency
    * In Trivial Functional Dependency, a dependent is always a subset of the determinant. i.e., If X → Y and Y is the subset of X, then it is called a trivial functional dependency.
    * Symbolically: A→B is a trivial functional dependency if B is a subset of A.
    * The following dependencies are also trivial: A→A & B→B
    * Here, {roll_no, name} → name is a trivial functional dependency, since the dependent name is a subset of determinant set {roll_no, name}. Similarly, roll_no → roll_no is also an example of trivial functional dependency.

* Non-trivial Functional Dependency
    * In Non-trivial functional dependency, the dependent is strictly not a subset of the determinant. i.e. If X → Y and Y is not a subset of X, then it is called Non-trivial functional dependency.

    * Example: Id -> Name, Name -> DOB

* Properties of Functional Dependency (Also known as Armstrong's axioms)

    1. Reflexivity
        * Axiom of Reflexivity: If A is a set of attributes and B is a subset of A, then A holds B. If B⊆A then A→B. This property is trivial property.
    2. Augmentation
        * Axiom of Augmentation: If A→B holds and Y is the attribute set, then AY→BY also holds. That is adding attributes to dependencies, does not change the basic dependencies. If A→B, then AC→BC for any C.
    3. Transitivity
        * Axiom of Transitivity: Same as the transitive rule in algebra, if A→B holds and B→C holds, then A→C also holds. In the dependency A→B we say that A functionally determines B. For example, if X→Y and Y→Z, then X→Z.

* Terminologies
    1. Closure of an attribute set
        * The attribute closure of an attribute set can be defined as a set of attributes that can be functionally determined from it.
        * Helps to identify all possible attributes that can be derived from a set of given attributes.
        * It can be computationally expensive, especially for large datasets.
        * Helps in database design by showing how attributes and tables are related, which can improve query performance.
        * It becomes complex to manage as the number of attributes and tables increases.
        * R(A, B, C, D, E)
        ```
            A -> B
            BC -> D
            C -> E

            AC+ = {A, C, B, D, E}
        ```
        * If X+ contains all the attributes of the relation, then X is the super key of the relation

    2. Equality of 2 Functional dependency sets
        * Equivalence of functional dependencies means two sets of functional dependencies (FDs) are considered equivalent if they enforce the same constraints on a relation. This happens when every FD in one set can be derived from the other set and vice versa using inference rules like Armstrong's axioms.
        * Equivalent FDs result in the same set of valid relations and preserve the same data integrity.
        * It helps in normalization and optimizing database design without losing any constraints.
    3. Canonical Cover
        * Managing a large set of functional dependencies can result in unnecessary computational overhead. This is where the canonical cover becomes useful.
        * A canonical cover is a minimal set of functional dependencies that is equivalent to the original set.
        * It contains no redundant dependencies or extraneous attributes.
        * It is also known as the minimal cover or irreducible form of functional dependencies.

        ```
        F = A -> B
            BC -> D
            C -> E
            AC -> D

        AC -> D is redundant and can be removed without losing any property of the Relation F and hence forming a canonical cover
        ```