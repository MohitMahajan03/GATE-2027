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

1. On delete no action
2. on delete cascade
3. On delete set NULL
4. On update no action
5. On update cascade
6. On update set NULL

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