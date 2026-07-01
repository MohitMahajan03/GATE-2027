# DBMS for GATE 8 - 10 marks -> Scoring

## Introduction to DBMS

* Database is a collection of related data
* DBMS is a software used to manage and access the DB files more efficiently, interface between user and DB files

### Flat File System vs DBMS

```
Refer Filesystem VS DBMS from (DBMS/Basics of DBMS/notes.md)
```

### Basic Terms used

* Relation: The table structure used to store data
* Attributes/Fields: Columns present in the table
* Tuples/records: One single row of the entire relation/table
* Degree/Arity: Degree is number of attributes in a relation.
* Cardinality: Number of records in a relation
* Relational Schema: Abstract details of the relation
* Relational instance: What is relation/table at given instance
* Schema: DB Table Definition and abstract details of the table
* Relational Instance: It is the record set of DB table at a particular instance
* Candidate key: Minimal set of attributes Which is used to identify each tuple uniquely
* Prime Attribute: Attribute belonging to some candidate key of a relation
* Non Prime Attribut: Attribute not belonging to any candidate key of a relation

### Rules of DBMS

1. Data should be in Tabular format
2. No 2 rows or columns should be same

### Keys

```
Refer Filesystem VS DBMS from (DBMS/Basics of DBMS/notes.md)
```
* Number of super keys in a set of candidate keys = 2<sup>number of attributes of relation are not part of candidate key</sup>
    * Ex:
    ```
    R{A B C D E F} ; Candidate keys {AB, BC}

    Considering AB Super keys set are-> C D E F -> 2^4
    Considering BC Super keys set are-> A D E F -> 2^4
    Considering ABC Super keys set are -> DEF -> 2^3

    total number of keys = 2^4 + 2^4 - 2^3 (Since ABC will be counted twice)
    Total number of super keys = 24

    Very nicely explained in L2 at 40 mins

#### H.W.

1. R{A1, A2, A3, ...  An} ; Candidate Keys [{A1}, {A1A2}, {A1A2, A2A3}]