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