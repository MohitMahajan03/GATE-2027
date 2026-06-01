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



### Home work

#### L2

1. Cover Functional dependency