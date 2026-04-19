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

### L3

1. (A + B + ~C)(A + B + C)(~A + B + C)
