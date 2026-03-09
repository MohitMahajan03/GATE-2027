# Basics of Python

## Introduction

### Programming in Python

* Python is a High level language
* Python is both compiled and interpreted language
* An interpreter, checks code and executes it line by line
* The interpreter is slower than compiler
* The compiler picks up the entire code and converts it into byte code, and from there the interpreter, picks up byte code line by line and then convert it into machine language
* It is a dynamically typed language

### Print Function

* print() function by default has an end parameter "\n"
* The end parameter in the print function can be changed to any symbol/string of our choice. Ex: print("Hello", end = "_")
* Adding "," between 2 strings/variables the print() will add a " " in between while printing. This is done by the "sep" parameter, default = " ".
* The sep parameter is applied when comma separated values are passed to the print function. Ex: print("placement", "2027", sep = "_", end = "#")

### Variables

* They are named memory locations, to store data
* Variable name starts with (_, a-z, A-z), Never starts with numbers, cannot contain special characters (!,<>,@,#,$,%,^,&,*,-,=,+), variable names are case sensitive
* Variable names cannot be keywords
* Type of the variable will be decided during run time

### Operators

* Operators are special symbols in python which are used to perform operation on operands.

1. Arithmetic Operators : +, -, *, /, %, **, //
2. Relational Operators : ==, !=, <=, >=, <, >
3. Assignment operators : =, +=, -=, *=, /=, %=, **=, //=
4. Logical operators : AND, OR, NOT
5. Bitwise operators : &, |, ^, ~, <<, >>
6. Membership operator : in, not in
7. Identity operators : is, is not

### Control Statements

* These are the staments that can change the flow or order of instructions of execution of instructions in the program.

1. if
2. elif
3. else
4. match Ex:

    ```
    x = 10
    match x:
        case x if x > 0:
            print("Positive")
            
        case x if x < 0:
            print("Negatice")
            
        case x if x==0:
            print("Zero")

### Loops

* When we repeatedly want to perform similar type of operation.

1. For
2. While

### Miscellaneous Helpful Functions

1. Input
2. Range(start, stop, step)
3. Enumerate -> returns 2 values, index and value (used with lists and for loops)
4. 