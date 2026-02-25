# This subject introduces the functionality of Computer and C languages

## Introduction

### Block Diagram of a Computer System

* View block_diagram.png

* Humans provide instructions to the computer and the computer executes them.
* A program is sa sequence of instructions
* Computer understands only binary data also known as "Machine Language"
* Assemble language uses mnemonic instructions to represent machine code instructions.
* The assembly language is also called Low level language (as it is more closer to the hardware)
* It allows manipulation of hardware elements like register, memory etc.
* They also help in developing operating systems, device drivers and embedded systems.
* High level languages are programming languages which are understood by humans, Which uses letters and symbols to represent logic and instructions in a program.

* It uses english words and mathematical symbols rather then mnemonic codes.
* High level -> Assembly -> Low level -> Machine

### C Programming

* C is considered as a middle level language because it has features of both low-level and high level languages.

* It gives access to developers to manipulate the hardware, hence it is a middle level language.

* C is used to build system programs, device drivers, Compilers and assemblers, embedded systems, IoT devices, Application software, databases, Games, Networking protocols and web servers.

### System Programs

* They are Programs that helps in translation of High Level Language to Low Level Language.
* View translation.png

#### Preprocessor

* Helps in including support files into the program
* Help in defining macros to help in holding numeric value
* It runs before the acutal compilation.

#### Compiler

* The compiler converts the high level program to target assembly program.
* Output of a compiler is an object code (Assembly code), Which is not executable.
* It identifies syntax errors

#### Assembler

* The assembler generates the assembly level program from the object code
* Therefore, It generates relocatable Machine code from object code.
* Relocatable means, the code can be executed in an part of the main memory.
* Therefore, output of assembler is a .exe file or an executable file.

#### Linker and Loader

* Linker combines all code files together before the execution
* Loader is the system program that loads the program, data and related subroutines into the memory for execution

#### Executable File

* It consists of Machine instruction code. Which can be executed by the processor.

## Data Types and Operators

1. Macro
    * They are defined using preprocessor directives and primarily used for code substitution and generation
    * Increases readability and maintainability of the code
    * Example '''# define size 100'''

### Number System

1. Decimal Number System -> 40 = 4 * 10 + 0 * 0 = 40
2. Binary Number System -> 10100 = 2<sup>4</sup> * 1 + 2<sup>3</sup> * 0 + 2<sup>2</sup> * 1 + 2<sup>1</sup> * 0 + 2<sup>0</sup> * 0 = 20.
3. Octal Number System -> Number system having base 8. (0, 1, 2, 3, 5, 6, 7)
    * (47)<sub>10</sub> -> 57<sub>8</sub>
4. Hexadecimal Number System -> Is a base 16 notation of numbers
    * 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, A, B, C, D, E, F
    * (64)<sub>10</sub> -> (40)<sub>16</sub>

### Types of Integers (Fundamentals)

1. In C language, there are 2 types of integers -> Signed and Unsigned integers.
2. To represent the sign, the 1 bit (MSB) is reserved.
3. If MSB is 0, then the number is a positive number
4. if MSB is 1, then the number is negative number.

#### 2's complement representation

* To represent any number as a negative number in binary, then we have to find the 2's complement of that number
* It is done in following the steps below
  1. Take 1's complement of the number. Ex: 010 -> 101
  2. Then add binary 1 to the number -> 101 + 1 = 110
* Now 110 is the negative number of 010
* if a signed number is given (already in 2's complement form), what will be the decimal equivalent value?
    1. First, how will you determine it is a negative number? MSB = 1
    2. Then you can apply 2's complement again to get back positive number
    3. Then convert the positive binary number to Decimal number

* The 2nd way to do this is -> if 1011 is a Negative number in 2's complement form.
    1. Directly expand the number in the form of Decimal number.
    2. Interpret the MSB as negative number. Ex: 1011 -> -8 + 0 + 2 + 1 = -5

### Intro to C programming

* A token is a sequence of characters having a logical meaning to C language. Example : Keywords, operators, constants, identifiers, special symbol.
* Keywords : Words that are reserved by the C language, that cannot be used for any other purposes.
* Identifiers: They are name given to variables and functions: naming conventions -> alphabet, underscore/numeric, alphabet/numeric.

### Data Types and their sizes in C

* Group of 8 bits is called byte
* Integer -> 4 bytes = 4 * 8 = 32 bits -> format specifier "%d" -> Binary constants : int a = 0b101; Octal : int a = 015; Hexadecimal : int a = 0x12
* Character -> 
* Float -> 

### Types of operators

1. Arithmetic operator
2. Relational operator
3. Logical operator
4. Bitwise operator
5. Ternary operator / Conditional operator

### Structure of C Program

1. Preprocessor Directive -> #include<stdio.h>
2. Global Variables
3. Helper Functions
4. Main function -> Place where program starts execution
5. Program Body -> enclosed in { } -> It creates a program block
   * Program block defines scope and visibility of a variable

### Unstructured Info

1. in b10001 -> first "1" from left is the MSB (Most Significant bit) and first "1" from right is the LSB (Least Significant bit)
2. Decimal to binary conversion -> refer image decimal_to_binary.png
3. Think in powers of 2 while converting decimal to binary, it is faster : Ex 98 = 64+32+0+0+0+2+0 = 1100010
4. Decimal to octal -> Take the decimal number and keep dividing by 8, take the remainder after each division to (Exactly like decimal to binary)
5. Conversion of Octal to Decimal is as same as Binary to Decimal, just instead of powers of 2, we use powers of 8
6. Decimal to Hexadecimal, and Hexadecimal to Decimal follow the same pattern.
7. Declarative statement is a statement that define data type and name of the variable
8. Types of statement
    1. Declarative
    2. Arithmetic (Relational, bitwise)
    3. Input and output statement
    4. Control statement

### Good Problems

1. If 111111..... n-times, what is the decimal value? = 2<sup>n(n+1)/2</sup> + 1. (Solved it on my own!!)
2. 12012 is a ternary operator, what is it's decimal value?