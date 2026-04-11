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

* C is a sequential language. Each statement of the program is executed one after another in a sequential manner

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
* Integer -> (DOS 2 Bytes) 4 bytes = 4 * 8 = 32 bits -> format specifier "%d" -> Binary constants : int a = 0b101; Octal : int a = 015; Hexadecimal : int a = 0x12
    * Signed int ranges = 
    * Unsigned int ranges = 
    * short int ranges = size (2B)
    * long int ranges = size(8B) format specifier (%ld)
* Character -> 1 byte = 1 * 8 = 8 bits -> format specifier "%c" -> represented by ASCII (American Standard Code for information interchange) values
  * Ranges : A - 65 : Z - 90 ; a - 97 : z - 122 ; 0 - 48 : 9 - 57;
* Float -> 4 bytes -> 4 * 8 = 32 bits -> format specifier "%f" -> Follows IEEE-754 standard. -> refer image float_bit_format.png
* Double -> 8 bytes -> 8 * 8 = 68 bits -> format specifier "%lf"

### Types of operators

1. Arithmetic operator (+, -, *, /, %, =) -> Binary operators
   * int to int -> int
   * int to float -> float
   * float to float -> int
2. Relational operator (>, <, <=, >=, ==, !=)
3. Logical operator (&&, ||, !) -> ! is a unary operator.
4. Bitwise operator
5. Ternary operator / Conditional operator (&, |, ^, ~, <<, >>)
6. Unary Operator (-, !) -> Operators that are applied on single operand. Ex : -5, -9.

### Precedence rule

* In general, the C language uses the BODMAS rule to find find the value of an expression.

### Operators ++ and --

* These operators modify the value of the variable
* It is not applied on constants and expression.
* Post-increment -> x++; Pre-increment -> ++x;
* Post-decrement -> x--; Pre-decrement -> --x;

### Structure of C Program

1. Preprocessor Directive -> #include<stdio.h>
2. Global Variables
3. Helper Functions
4. Main function -> Place where program starts execution
5. Program Body -> enclosed in { } -> It creates a program block
   * Program block defines scope and visibility of a variable

### Control Flow Statements

* Types of Control Flow
    1. Conditional or selection or branching or decision
    2. Iterative statement
    3. Jump statement

1. Branching Statement
    * if(condition)
    * else
    * else if
    * nested if
    * switch case
    * ternary operator : Syntax -> expr1 ? expr2 : expr3; if expr1 is true, then return expr2, else return expr3

2. Iterative Staments -> Execution of repetative tasks
   * For loop
   * While loop
   * Do-While loop

### Functions

* It is a logical group of statments that forms a single logical unit
* Helps us give more structure to the to the program, to manage the code and reusability

1. Forward declaration -> declaring the function before the main function.
2. Function call -> Calling the functions
3. After the main function, function definition takes place
4. When function is called, control is transferred to the body of the function
5. The actual parameters are passed as values to the functions through the formal parameters. If the sctual parameter values are copied to the formal parameters, then the function follows call by value.
6. After function is executed, if there is any return value, a value is returned and control is tranferred back to callee function
7. Function nesting is possible in C

### Recursion

* It is a mathematical problem solving technique
* Solution of the problem is expressed as a smaller instance of the same problem
* In programming recursion is defined as a function which calls itself is defined as recursion
  
* Things to keep in mind:
    1. Base Condition : Conditions which terminates the recursion without recursive function call.
    2. Progress : The next recursive function call should be updated value, otherwise it leads to infinite function.

### Scopes and Lifetimes

* With every variable, 2 aspects are associated
    1. Scope: The place where we can access the variable is called the scope of hte variable
        * Local scope variable is restricted to within the {} enclosing it.

    2. Lifetime: Every time a function is in execution then the memory for the local variable is allocated. Upon termination of a function, memory is deallocated

* Compile time allocation : If memory is allocated during compilation then it is called compile time allocation. Global Variables

* Run time allocation : If memory is allocated during run time then it is called run time allocation. Local Variables

* In different scopes, 2 local variables, can have the same name, But not in same scope

* Global Variable can be accessed anywhere in the program, Lifetime of global variable is until the program is running

### Storage Classes

* Memory Layout of a C program: When a program is in execution then it uses different sections of the memory explained as follows
    1. Code Area : Linker and Loader loads the exe file in this area for execution.
    2. initialized Data Segment : All data which has initial value defined, like Global variables. (Compile time allocation)
    3. Heap : Memory allocated by compiler for local and global variables. The user can also allocate and deallocate the memory. (Runtime allocation), using malloc and calloc and free
    4. Stack : Memory allocated in stack is also dynamically allocated i.e at runtime. Local variables are stored in stack. Activation record is stored in the Stack

* Storage Class depends on:
    1. The area of memory where a variable is stored
    2. The scope of a variable
    3. Lifetime of the variable
    4. Initial value of a variable

* Types of Storage classes:
    1. auto :
        * auto is short for automatic.
        * auto is default storage class of local variable. Ex: auto int a;
        * auto variables are stored in stack.
        * As soon as we call the function, local variable allocation takes place. And upon termination of function, memory is deallocation takes place.
        * Initial value is garbage value
        * Scope is within the function and lifetime is as long as function is in execution.
    2. static :
        * Default storage class for global variable. Ex: static int a;
        * Static variable stored in Initialized data segment, with initial value 0
        * Lifetime of static variable is as long as the program is running
        * Local variable can also be static variable
        * If local variable is declared as static, then it preserves it's value during multiple function calls.
        * Local static variable is initialized only once
    3. register :
        * It is a memory within the processor
        * Because register is inside the processor, data in registers can be accessed very fast
        * Only local variables can have register storage class, register int a;
    4. extern : Short for external
        * extern keyword extends scope of the variable. Such that the global variables can be accessed in other program files

### Pointers

* C language allows a access of address of a variable
* Pointer variable is a variable that holds the address of another variable of same data type
* Declaration -> int *ptr = &a ;
* printf("%p", ptr); -> prints address of a
* printf("%d", *ptr); -> prints value of a

### Pointers to pointer

```
    int a = 10;
    int *ptr;
    int **ptr1;
    ptr = &a;
    ptr1 = &ptr;
```

### Array

* An array is a variable that can hold multiple values of same data type.
* It is a derived data type from primitive data types.
* Array stores elements in consecutive memory locations
* Declaration, Initialization, accessing array elements
    ``` 
        int a[10] = {1, 2, 3, 4, 5, 6, 7, 8, 9, 0};
        for (int i = 0; i < 10; i++)
        {
            printf("%d", a[i]);
        }
    ```
* a[0] is also called as the base address of the array
* So for integer array a -> a[1] is present at 1004 since int -> 4 bytes
* Address = Base address + (Size of datatype * position)
* Array of characters is a string
* 2D array -> int a[10][10];

### Array Addressing

* Each memory location has an address, and is assigned 1 Byte, Therefore it byte addressed
* Let's assume and integer array's starting address is at 1000
* Then the 1st index address is from 1000 to 1003, then 2nd index address starts from 1004 to 1007 and so on.
* Therefore general formula to calculate any address is = Base address + (size of datatype * index value)

### 2D Arrays

* Arrays are always stored in sequential order in the memory
* internally 2D arrays are mapped in 1D in the memory sequentially
* All of the elements are stored in single sequency row wise for example: int a[2][2] = {{1, 2}, {3, 4}} is saved as 1, 2, 3, 4 in the memory layout

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
9. Break can only be used in switch and loops
10. Continue can skip remainder of the body of the loop and go on with the next iteration

### Good Problems

1. If 111111..... n-times, what is the decimal value? = 2<sup>n(n+1)/2</sup> + 1. (Solved it on my own!!)
2. 12012 is a ternary operator, what is it's decimal value?
3. Will "short a = 10;" and "long a = 10;" work? Yes they work