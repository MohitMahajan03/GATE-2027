# C Programming
## Solve All Questions
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
  * Range -> -2<sup>n-1</sup> to -2<sup>n-1</sup>-1 where n is number of bits, so either 32 bit or 16 bit
  * Format specifier %d
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

### MISC

* % Does not apply on float and double values