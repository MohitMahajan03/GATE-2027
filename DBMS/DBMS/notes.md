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

[Refer Here for keys](../Basics%20of%20DBMS/notes.md#Keys%20in%20RDBMS)

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

[Refer Here for referential integrity constraint](../Basics%20of%20DBMS/notes.md###Keys%20in%20RDBMS)

#### H.W.

1. R{A1, A2, A3, ...  An} ; Candidate Keys [{A1}, {A1A2}, {A1A2, A2A3}]

```
If we hide A1 -> (n-1) Attributes
Number of superkeys = 2^(n-1)

For A1A2 -> 2^(n-2)
For A2A3 -> 2^(n-2)

Then for common keys -> A1A2A3 -> 2^(n-3)

= 2^(n-2) + 2^(n-2) - 2^(n-3)
```

2. R(A, B, C, D, F) Candidate Keys = {A} {B} {C}

```
For A -> 2^4 = 16
For B -> 2^4 = 16
For C -> 2^4 = 16

For AB -> 2^3 = 8
For BC -> 2^3 = 8
For AC -> 2^3 = 8

for ABC -> 2^2 = 4

Total number of super keys = 48 - 24 + 4 = 28
```

3. R(A, B, C, D, E, F) Candidate Keys = {A} {BC} {CD}

```
For A -> 2^5 = 32
For BC -> 2^4 = 16
For CD -> 2^4 = 16

For ABC -> 2^3 = 8
For ACD -> 2^3 = 8
For BCD -> 2^3 = 8

For ABCD -> 2^2 = 4

Total number of super keys = 64 - 24 + 4 = 44
```

4. R(A1, A2, .... An) Candidate keys = {A1} {A2} {A3}

```
For A1 -> 2^(n-1)
For A2 -> 2^(n-1)
For A3 -> 2^(n-1)

For A1A2 -> 2^(n-2)
For A2A3 -> 2^(n-2)
For A1A3 -> 2^(n-2)

For A1A2A3 -> 2^(n-3)

Total number of super keys = 3[{2^(n-1) - 2^(n-2)} + 2^(n-3)]

Also can be written as 2^(n-3)[3.2^2 - 3.2 + 1]
= 2^(n-3).[7]

```

5. R has 2 candidate keys with 1 and 2 attributes. there are 40 super keys, what is total attributes in R?

```
Let n be number of attributes

For 1 -> 2^(n-1)
For 2 -> 2^(n-2)

For 1&2 -> 2^(n-3)


40 = 2^(n-1) + 2^(n-2) - 2^(n-3)

40 = 2^(n-3)[4 + 2 - 1]
40 = 5.2^(n-3)

8 = 2^(n-3)

2^3 = 2^(n-3)

n-3 = 3
n = 6

Therefore, the Relation has 6 attributes!
```