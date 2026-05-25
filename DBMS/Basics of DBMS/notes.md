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

* I/O cost for an access is defined in terms of number od memory blocs tranferred from secondary memory to main memory

