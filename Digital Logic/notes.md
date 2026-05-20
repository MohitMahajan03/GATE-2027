# Digital Logics

* 4 questions appeared in GATE

## Boolean Theorem and Logic Gates

### Introduction

* Base of Decimal number system = 10, So therefore we can use 10 symbols to represent decimal number system. [0 - 9]. 
* So if we want to represent a number with base r, then we can use [0 - (r-1)] digits to represent numbers
* Every position the digits are written have weight with respect to the base. Example 786 = 7 * 10<sup>2</sup> + 8 * 10<sup>1</sup> + 6 * 10<sup>0</sup>

### Binary Number system

* Numbers are represented in base 2 format (110)<sub>2</sub>
* Use approximations to quickly make conversions between decimal to binary and binary to decimal
    * Example, (42)<sub>10</sub> < 2<sup>6</sup>, Therefore in binary the number of bits required is 6  = (101010)<sub>2</sub>

### Digital Logic

* Any variable can hold either 1 or 0. So if we combine n variables then total number of bit combinations possible will be 2<sup>n</sup> and the highest value is (2<sup>n</sup> - 1).
  * Example: AB -> 00, 01, 10, 11 : Where A is MSB and B is LSB

### Boolean Theorems

1. 'OR' operations -> (+)
   * A + 0 = A = 0 + A
   * A + 1 = 1 + A = 1
   * A + ~A = 1 = ~A + A
   * A + A = A
   * A + A + A = A
   * ~A + ~A + ~A = ~A
   * 0 + 0 = 0

2. 'AND' operations -> (.)
    * A . 0 = 0 . A = 0
    * A . 1 = A
    * A . ~A = 0
    * A . A = A

3. Boolean laws
    * A(B+C) = AB + AC -> Distributive Law
    * A + (BC) = (A + B)(A + C) -> Distributive Law

4. Redundancy / Consensus Theorem (Important)
    * For this theorem to work, the expression should have a minimum of 3 terms
    * Atleast 1 variable should be present that has it's complement in one of it's term as well.
    * Example : AB + ~AC + BC
      * So here BC is the redundant term -> It is the product of the remaining 2 variables
      * Therefore, by the theorem, it can be omitted
      * AB + ~AC

5. DeMorgan Theorem
    * Works on whole complements
    * ~(A + B + C) = ~A.~B.~C
    * ~(ABC) = ~A + ~B + ~C

6. P.[P + Anything] = P
    * P.P + P.anything
    * P + P.anything
    * P[1 + Aything]
    * P.1
    * P

### Boolean Function

#### Sum of Products (SOP)

* Sum of all boolean product terms
* A = 1 and ~A = 0
* Considers function ouput 1

#### Product of Sum (POS)

* Product of all boolean sum terms
* ~A = 1 and A = 0
* Considers function output 0

#### Example

1. Function of A, B
```
A B f(A,B)  SOP      POS
0 0    1   ~A.~B     (A + B)
0 1    0   ~A.B      (A + ~B)
1 0    1   A.~B      (~A + B)
1 1    0   A.B       (~A + ~B)

SOP (∑)= ~A~B + A~B = ~B[~A + A] = ~B
POS (π)= (A + ~B)(~A + ~B) = ~B
```

### Basic Gates

1. NOT Gate also called as inverting buffer
    * It is a single input gate (refer not_gate.png)
    * Given A -> ~A
    * Truth table:
    ```
    Input A Output ~A
        0       1
        1       0
    ```
2. AND Gate
    * It is a minimum double input and single output gate (refer and_gate.png)
    * Truth table
    ```
    A B     Output = A.B
    0 0         0
    0 1         0
    1 0         0
    1 1         1
3. OR Gate
    * It is a minimum double input and single output gate (refer or_gate.png)
    * Truth table
    ```
    A B     Output = A+B
    0 0         0
    0 1         1
    1 0         1
    1 1         1
4. Commutative Law:
    * If the positions of the variables are interchanged, then the result of the expression does not change. Applicable for AND and OR
    * A.B = B.A
    * A+B = B+A
5. Associative Law:
    * If in a multi input expression, if the terms can be processed by executing the operation in a cumulative fashion, and the result is same as the direct multi input expression, then the operation holds associative law. AND and OR are associative
    * A.B.C = (A.B).C
    * A+B+C = (A+B)+C

### Arithmetic Gates

1. XOR Gate (Exclusive OR gate)
   * Only defined for 2 inputs (refer xor_gate.png)
   * A⨁B = ~AB + A~B
   * AB⨁BC = ~(AB).BC + AB.~(BC)
   * Truth table
    ```
    A B     Output = A⨁B
    0 0         0
    0 1         1
    1 0         1
    1 1         0
    ```
    * Commutative Law holds for XOR Gate
    * Associative Law does not hold for XOR Gate, as it takes only 2 inputs. But it is DEFINED by default that it holds associative law, to calculate multi input XOR operation.
        * A⨁B⨁C = (A⨁B)⨁C or (B⨁C)⨁A
    * Properties of XOR Gate
        * A⨁A = 0 = ~AA + A~A
        * A⨁~A = 1
        * A⨁0 = A = ~A.0 + A.~0
        * A1 = ~A = ~A.1 + A.~1

    * Exchange properties of XOR Gate
        * If A⨁B = C given, then A⨁C = B, then C⨁B = A
    * A⨁A⨁A⨁A.... n times
        * Then o/p for n being even = 0
        * Then o/p for n being odd = A
    * XOR Acts as buffer and inverting buffer if one of the inputs is set as 0 or 1 respectively

2. XNOR Gate (Exclusive NOR gate)
    * It is defined for 2 inputs only (refer xnor_gate.png)
    * A⊙B = ~A~B + AB
    * Truth table
    ```
    A B     Output = A⊙B
    0 0         1
    0 1         0
    1 0         0
    1 1         1
    ```
    * ~(A⨁B) = A⊙B
    * Commutative law holds for XNOR gate
    * Associative Law holds for multi input XNOR Gate -> It is DEFINED to calculate multiple inputs
    * Properties of XNOR Gate
        * A⊙A = 1
        * A⊙~A = 0
        * A⊙1 = A
        * A⊙0 = ~A
    * Exchange properties of XNOR gate
        * If A⊙B = C then A⊙C = B and C⊙B = A
    * A⊙A⊙A⊙A.... n times
        * Then o/p for n being even = 1
        * Then o/p for n being odd = A
    * XNOR Gate also acts as an inverting buffer if one of the inputs is set as 0.
### Universal Gates

1. NAND Gate
2. NOR Gate


### Misc Info

* Maximum number of n bits in any format, it's equvalent value in decimal is equal to (weight<sup>n</sup> - 1)<sub>10</sub>
  * Example: 1111<sub>2</sub> = (15)<sub>10</sub> = (2<sup>4</sup> - 1)
  * This works with any number system as well
* DeMorgan's Law 
  * ~(A.B) = (~A + ~B)
  *  (~A + ~B) = ~(A.B)

### Home Work

#### L1

1. (173)<sub>10</sub> = (10101101)<sub>2</sub>
2. (222)<sub>10</sub> = (11011110)<sub>2</sub>
3. (1011101)<sub>2</sub> = (93)<sub>10</sub>
4. Only B, C are valid numbers

#### L2

1. AB + ~AC + BC + AC + ~C 
   * AB + C(~A + A) + BC + ~C
   * AB + BC + C + ~C
   * AB + BC + 1
   * 1

2. A + BC + CD + ~AB + ABC + AB
    * A + BC + CD + ABC + B(A + ~A)
    * A + BC + CD + ABC + B
    * A(1 + BC) + BC + CD + B
    * A + B(1 + C) + CD
    * A + B + CD

3. AB + ABC + ~ABC + ~AB
    * B(~A + A) + BC(~A + A)
    * B + BC
    * B(1 + C)
    * B

#### L3

1. (A + B + ~C)(A + B + C)(~A + B + C)
    * [(A + B) + ~C.C][~A + B + C]
    * (A + B)(~A + B + C)
    * B + A.(~A + C)
    * B + AC

2. (A + ~B + ~C)(~A + B + ~C)(A + B + ~C)
    * (A + ~B + ~C)[(B + ~C)]
    * ~C + (A + ~B).B
    * ~C + AB

3. AB + ~ABC 
    * B(A + ~AC)
    * B[(A + ~A).(A + C)]
    * B(A + C)
    * AB + BC

4. (A + B + C)(~A + B + C)(A + ~B + C)(~A + ~B + C)
    * [(A + C)+ B.~B][(~A + C) + B.~B]
    * (A + C)(~A + C)
    * C + A.~A
    * C

5. A + BC + ~ABC + ~A~BC + CD
    * A + BC(1 + ~A) + ~A~BC + CD
    * A + BC + ~A~BC + CD
    * BC + (A + ~A)(A + ~BC) + CD
    * BC + (A + ~BC) + CD
    * BC + A + ~BC + CD
    * A + C(B + ~B + D)
    * A + C

6. (A + B)(B + C)(~A + ~C)
    * [A.~A + A.~C + ~AB + B~C](B + C)
    * [](B + C)


#### L4

1. ~A~BC + BCD + ~ACD
    * ~A~BC + BCD (Redundancy Theorem)
    * C[~A~B + BD]

2. ~[(A + ~B)(B + ~C)(~A + C)]
    * ~(A + ~B) + ~(B + ~C) + ~(~A + C)
    * ~AB + ~BC + A~C

3. A + BC + ~AC
    * BC + (A + ~A)(A + C)
    * BC + (A + C)
    * C(1 + B) + A
    * A + C

4. ~AB + AC + ~BC 
    * ~AB + C(A + ~B)
    * ~(A + ~B) + C(A + ~B)
    * [(A + ~B) + ~(A + ~B)].[~(A + ~B) + C]
    * ~AB + C

5. ~A~B + ~B~C + ~AC
    * ~B~C + ~AC (redundancy Theorem)

6. ~AB + BC + B~C -> B
    *  

7. AB + A~BC + ~BC
    * AB + ~BC(A + 1)
    * AB + ~BC

#### L5

1. ~(A~B(~AB + ~BC + A~BD + A~B~D))
    * NOTE : P.[P + anything] = P
    * ~(A~B(~AB + ~BC + A~B(D + ~D)))
    * ~(A~B(~AB + ~BC + A~B))
    * ~(A~B)
    * ~A + B

2. ~A~B + AC + ~BC
    * ~A~B + AC -> Redundancy theorem

3. AB + A~BC + ~A~C
    * A(B + ~BC) + ~A~C
    * A((B + ~B)(B + C)) + ~A~C
    * AB + AC + ~A~C

4. AB + A~BC + ~B~C
    * A((B + ~B)(B + C)) + ~B~C
    * A(1.(B + C)) + ~B~C
    * A(B + C) + ~B~C
    * AB + AC + ~B~C
    * A(B + C) + ~(B + C)
    * (~(B + C) + A).(~(B + C) + (B + C)) 
    * A + ~B~C
    * (A + ~B)(A + ~C)

5. AB + ~A(~B + D) + BD
    * Now, B(~B + D) -> BD
    * Therefore AB + ~A~B + ~AD

6. A~B[ABC + ~BC + A~BC + BCD]
    * A~B[ABC + ~BC + BCD]
    * A~B[C(AB + ~B) + BCD]
    * A~B[C(A + ~B) + BCD]
    * A~B[AC + ~BC + BCD]
    * A~B[C(A + ~B + BD)]
    * A~B[C(A + ~B + D)]
    * A~B[AC + ~BC + CD]
    * A~BC + A~BC + A~BCD
    * A~BC + A~BCD
    * A~BC[1 + D]
    * A~BC

7. ~A~B + A~B + B~C -> ~(BC)
8. A + ~AB + ~AC -> A + B + C
9. A~B + A~C +~A~BC -> A~C + ~BC

#### L6

1. f(A, B, C) = ∑(1, 2, 4, 6) = π(0, 3, 5, 7)
```
A B C   SOP         POS
0 0 0   ~A~B~C      (A + B + C)
0 0 1   ~A~BC       (A + B + ~C)
0 1 0   ~AB~C       (A + ~B + C)
0 1 1   ~ABC        (A + ~B + ~C)
1 0 0   A~B~C       (~A + B + C)
1 0 1   A~BC        (~A + B + ~C)
1 1 0   AB~C        (~A + ~B + C)
1 1 1   ABC         (~A + ~B + ~C)

SOP ∑ = ~A~BC + ~AB~C + A~B~C + AB~C
POS π = (A + B + C)(A + ~B + ~C)(~A + B + ~C)(~A + ~B + ~C)
```

2. f(A, B, C) = ∑(0, 2, 5, 7) -> ~f(A, B, C) = π(0, 2, 5, 7) = ∑(1, 3, 4, 6)
3. if f(A, B, C) = ∑(1, 2, 3, 6) then ~f is/are?
    * π(1, 2, 3, 6)
    * ∑(0, 4, 5, 7)
4. f(A, B, C) = π(0, 2, 4, 5, 7) then ~f is/are?
    * ∑(0, 2, 4, 5, 7)
    * π(1, 3, 6)
5. ~A + ~AB + ~A~BC + A~B~C
6. ~A~B[~A~C + ~B~C + B~CD + ~A~CD]
    * ~A~B[~A~C + ~B~C + B~CD]
    * ~A~B~C[~A + ~B + BD]

#### L7 -> refer video lecture for HW
#### L8 -> refer video lectire for HW

1. (A⨁B)⨁(~B⨁C)⨁(A⨁~C)⨁(A⨁B)
    * A⨁A⨁A = A
    * B⨁~B⨁B = 1⨁B = ~B
    * C⨁~C = 1
    * A⨁~B⨁1 = A⨁B

