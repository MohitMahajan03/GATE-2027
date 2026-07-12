# DBMS for GATE 8 - 10 marks -> Scoring

# Complete all Home work!!

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

### Functional Dependency

[Refer This image](functional_dependency.png)

* Trivial FD: [Refer](../Basics%20of%20DBMS/notes.md###Keys%20in%20RDBMS)

* Non-Trivial FD: [Refer](../Basics%20of%20DBMS/notes.md###Keys%20in%20RDBMS)

### Inference Axioms (Armstrong's Axioms)

1. if Y is subset of X, then X->Y (Reflexivity)
2. If X->Y, then XW->Y or XW->YW (Augmentation)
3. If X->Y and Y->Z, then X->Z (Transitivity)
4. If X->Y and YW->Z, then XW->Z (Puedotransitivity)
5. if X->Z and X->Y, then X->YZ (Additivity or Union)
6. If X->YZ, X->Y and X->Z (Projectivity or Decomposition)

### Closure

[Refer](../Basics%20of%20DBMS/notes.md)


### Membership Test

1. Does F{XY->Q} exist given F={XY->W, Y->Z, WZ->P, WP->QR, Q->X}

```
{XY}+ -> {XYWZPQR}
So {XY}+ has closure on Q, therefore XY->Q exists
```

### Covering

* F covers G if all the dependencies of G can be derived from F
* F = {A->B, B->C} ; G = {A->C}
```
A->B and B->C, Therefore A->C
Hence F covers G
```

1. Does F cover G or G covers F 
```
F = {A->B, B->C, C->A}
G = {A->BC, B->AC, BC->A, AB->C}

F covering G
G
{A}+ = {ABC}, {B}+ = {BAC}, {BC}+ = {BCA}, {AB}+ = {ABC}
F
{A}+ = {ABC}, {B}+ = {BCA}, {BC}+ = {BCA}, {AB}+ = {ABC}

Only F can cover G
```

2. F = {A->BCDEF, BC->ADEF, B->F, D->E, AD->E} ; G = {A->BC, B->F, BC->AD, D->E}

```
F covering G

G
{A}+ = {ABCDEF}, {B}+ = {BF}, {BC}+ = {BCADEF}, {D}+ = {DE}
F
{A}+ = {ABCDEF}, {B}+ = {BF}, {BC}+ = {ABCDEF}, {D}+ = {DE}


G covering F
Yes, same as above as all keys are getting covered

G = F as F covers G and G covers F

```

### Redundant FD [Extra FD]

* if we have F = {A->B, B->C, A->C}
* Here we know that if we remove A->C, we can still derive AC from the Set of the F
* So, Therefore A->C is redundant FD

1. F = {X->Y, Y->X, Y->Z, Z->Y, X->Z, Z->X}
```
Excluding X->Y to check if X will be covered by Y

{X}+ = {XZY} -> Yes

Remove X->Y

F = {Y->X, Y->Z, Z->Y, X->Z, Z->X}

Excluding Y->X

{Y}+ = {YZX} -> Yes
Remove Y->X

F = {Y->Z, Z->Y, X->Z, Z->X}

Excluding Y->Z

{Y}+ = {Y} -> No
Keep Y->Z

Excluding Z->Y

{Z}+ = {ZX} -> No
Keep Z->Y

Excluding X->Z

{X}+ = {X} -> No
Keep X->Z

Excluding Z->X
{Z}+ = {ZY}

Keep Z->X

Final F = {Y->Z, Z->Y, X->Z, Z->X}

```

### Extraneous Attributes
x
* Given F = {A1A2 -> B}
```

Excluding A2 from F

Then iff A1 -> B Then A2 is extraneous attribute

```

### Canonical Cover

* Canonical Cover of F is F if
    * Every FD of F is simple -> Right side of every FD of F has only 1 attribute
    * F is left-reduced
    * F is non redundant


1. Find Canonical Cover for R(V,W,X,Y,Z); F = {V->W, VW->X, Y->VX, Y->Z}

```
F = {V->W, VW->X, Y->V, Y->X, Y->Z}


Checking Left Redundancy
excluding V in VW->X

{W}+ = {W}

V is required

-----------------------

excluding W in VW->X

{V}+ = {VWX}

Therefore W is redundant FD

F = {V->W, V->X, Y->V, Y->X, Y->Z}

-------------------------

Checking Non Redundancy

Excluding V->W

{V}+ = {V} Requireed

-------------------

Excluding V->X

{V}+ = {VW} Required

------------------

Excluding Y->V

{Y}+ = {YZX} Required

-----------------

Excluding Y->X

{Y}+ = {YVWX}

Redundant

F = {V->W, V->X, Y->V, Y->Z}

-----------------------

Excluding Y->Z

{Y}+ = {YVXW} 
Reqired

Final FD = {V->W, V->X, Y->V, Y->Z}

```

2. Find Canonical Cover for R(A,B,C,D,E,F,G); F = {BCD->A, BC->E, A->F, F->G, C->D, A->G}

```
F = {BCD->A, BC->E, A->F, F->G, C->D, A->G}

Checking Left Redundancy
excluding B in BCD->A

{CD}+ = {CD}

B is required

-----------------------

excluding C in BCD->A

{BD}+ = {BD}

C is required

-----------------------

excluding D in BCD->A

{BC}+ = {BCDAE}

Therefore D is extra, removing D

F = {BC->A, BC->E, A->F, F->G, C->D, A->G}

---------------------------------------------

BC->E Required Eyeballing, because, {B}+ = B, and {C}+ = {CD} 

-------------------------

Checking Non Redundancy

BC->A; Required Eyeballing, because, {BC}+ = {BCDE}

-------------------

BC->E; Required Eyeballing, because, {BC}+ = {BCAFGD}

------------------

A->F Required Eyeballing, because, {A}+ = {AG},

-----------------

F->G Required Eyeballing, because, {F}+ = F

--------------------

C->D Required Eyeballing, because, {C}+ = C

-----------------------

A->G Redundant Eyeballing, because, A->F and F->G exists

Final FD = {BC->A, BC->E, A->F, F->G, C->D}

```

### Normalization

* Done to reduce redundancy and thereby reduce anomalies

### H.W.

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

6. Find All CK using closure R(A,B,C,D,E,F); FD = {AB->C, C->D, CD->BE, DE->F, EF->A}

```
1. {AB}+ -> {ABCDEF}
2. {C}+ -> {CDBEFA}
3. {BDE}+ -> {DEFABC}
4. {BEF}+ -> {BEFACD}

```

7. R(E,F,G,H,I,J,K,L,M,N); FD = {EF->G, F->IJ, EH->KL, K->M, L->N} find key for R

```
{EF}+ -> {EFGIJ}     x
{EFH}+ -> {EFGHIJKLMN}   \/
```
8. R(A,B,C,D,E,F); FD = {AB->C, C->DE, E->F, F->B}

```
{AB}+ -> {ABCDEF}
{AC}+ -> {ACDEFB}
{AE}+ -> {AFBCDE}
{AF}+ -> {AFBCDE}
```

9. R(A,B,C,D,E); FD = {A->B, B->C, C->D, D->A}

```
{AE}+ -> {ABCDE}
{BE}+ -> {BCDAE}
{CE}+ -> {CDABE}
{DE}+ -> {DABCE}
```

10. R(A,B,C,D,E); FD = {A->B, A->C, CD->E, B->D, E->A}

```
{AC}+ -> {ACBDE}
{BC}+ -> {BCDEA}
{BD}+ -> {BDE}    x
{CD}+ -> {CDEAB}
```