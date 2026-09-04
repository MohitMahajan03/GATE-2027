# C Programming
# Solve all Home work
## Solve All Questions and Homework
## Intro to C programming

[Refer Intro C programming](../Introduction%20to%20C/notes.md)

### Identifiers

* Name of variable/function must always start with underscore or alphabet and followed by underscore/alphabets/digits

* C is a case sensitive language.

### Constants and Literals

* All declared variables are valid literals assigned to constants

```C
    int i = 40;
    float pi = 3.14;
    char ch = 'a';
    double x = 2.14567892;
    char ch[10] = "Hello";
```

* "%d" is a string constant, which is a format specifier

### Primitive Data Types

* Data type is defined by 3 things, The value it takes; Amount of memory required and iterpretation of value

* int
  * Size -> 2B/4B
  * Stored as 2's complement in the memory
  * Range -> -2<sup>n-1</sup> to 2<sup>n-1</sup>-1 where n is number of bits, so either 32 bit or 16 bit
  * Format specifier %d
  * unsigend range = 2<sup>32</sup>-1
  * short int -> 2B 
  * long int -> 8B
  * %lu -> long unsigned
* char
  * Size -> 1 byte
  * Stored as integers in ASCII code
  * Format specifier %c to print character and %d for printing ascii code
  * [Refer ascii table](ascii-table.png) Remember them!
* float
  * Size -> 4B and Double -> 8B and Long Double -> 16B
  * Stored as sign|exponent|mantissa
  * Format specifier for float and double -> %f; for long double -> %Lf
* operation between int and int give int
* operation between float and int give float
* operation between float and in give float

### Arithmetric Operators

* Precedence : The order of evaluation of operator is defined by the precedence rule
* Associativity : If precedence is same, then order of evaluation is decided by associativity
* [Refer the table here](precedence_table.png) 
* Unary operators
  * ++ and --
  * Only applicable on variables NOT applicable on constants and expressions
  * It updates the value of variables
  * Pre and post increments and decrements are allowed.

### Assignment operators

* =
* +=
* -=
* -=
* /=
* %=
* *=
* ">>="
* "<<="
* &=
* ^=
* |=

### Relational Operator

* These operators have left to right associativity
* Higher precedence
  * ">"
  * "<"
  * "<="
  * ">="
* Lower Precedence
* ==
* !=

### Logical Operators

* Higher Precedence
  * ! - NOT
* Lower Precedence
  * && - AND
  * || - OR

### Short Circuit Code

* Now given R1 && R2, if R1 is false, then the whole expression is false. So the compiler skips the check for R2 completely. This is called short circuting
* Now given R1 || R2, if R1 is true, then the whole expression is true. So the compiler skips the check for R2 completely. This is called short circuting

### Bit-wise Operator

```table
Operator     Meaning
&           Bitwise AND
|           Bitwise OR
^           Bitwise XOR
~           Bitwise NOT
<<          Left Shift
>>          Right Shift
```

```md
1. 5 & 17

 
  101 & 10001

  10001
  00101  = 00001


2. 5 | 17

  101 | 10001

  10001
  00101  = 10101

3. 5 ^ 17

  101 ^ 10001

  10001
  00101 = 10100

```

### Ternanry Operator

* expr1 ? expr2 : expr3

```C
    if (expr1)
      expr2;
    else
      expr3;
```
* expr1 can be relational expression or a normal expression


### Questions

1. 
```C
#include <stdio.h>

int main()
{
    int x = 8, y, b = 20;
    y = x++;
    y = ++x;
    y = x++*b;
    y = ++x*b;
    y = x--;
    y = --x;
    y = x--*b;
    y = --x*b

    printf("%d", x+y);
}
```

```text
y = 8, x = 9
y = 10, x = 10
y = 200, x = 11
y = 240, x = 12
y = 12, x = 11
y = 10, x = 10
y = 200, x = 9
y = 160, x = 8

x+y = 168
```

2.
```C
#include <stdio.h>
int main()
{
    int x = 0, y = 0, a;
    a = x && ++y;
    printf("%d %d", x, y)
    return 0
}
```

```md
* Answer is 0 and 0 due to code short circuiting
```
### MISC

* % Does not apply on float and double values
* Printf returns number of characters printed
* Scanf returns number of characters accepted
* c = a+++b -> c = a++ + b -> by longest prefix property

## Control flow statements

### if

* Syntax

```c
stmt0;
if(condition/expression)
{
  stmt1;
  stmt2;
}
else{
  stmt3;
  stmt4;
}
stmt5;
```
* NOTE
```c
// The semicolon terminates the "if" statement. The block is now a sequential block, and will always execute. The "expression" will always execute
// Therefore any else block present will throw an error "else without if" error
if(expression);
{
  stmt1;
  stmt2;
}
```

### switch

* Switch allows an expression to be tested for equality against list of values
* Each value in list is called as case
* If none of the case is true, default case executes and it is optional
* 
```c
switch(expression)
{
  case value : stmts;

  break;
}
```