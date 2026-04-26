# Basics of Computer Systems

### Components of a Computer

1. CPU -> Central Processing Unit
   * They are also called as processor or microprocessor
   * Brain of the computer system.
   * It is comprised of Control Unit and Algorithmic and Logic Unit
2. Memory
    * Consists of Primary (RAM) and Secondary (HD, SSD) memories
    * RAM is temporary memory
    * HD and SSD is Permanent memory
3. I/O devices
   * These are input output devices
   * Input devices consists of keyboard, microphone, camera, etc
   * Ouput devices consists of monitor, printer, speaker, etc
   * Storage devices consists of pendrives, CDs, etc
4. System Buses
    * It is a wired connection between components of computer
5. CPU Registers
   * It is set of memory inside the CPU, to help carry out processing

### Computer Architecture

* Conceptual design and fundamental operational structure

### Computer Organization

* Deals with physical devices and their interconnections
* With a perpective of improving the performance

### Digital Computer

* Computer which takes input in form of binary and gives output in binary
* Binary is a number system where all the numbers are denoted by only 2 digits 0 and 1
* Program and data are fed to the computer in binary
* The compiler converts the program and data into binary

### Main Memory (RAM)

* All programs that need to be run are loaded into the main memory
* It is used to store current running programs and their data

### Data in Computer System

* Data that goes to the CPU can be of a number or character, both of them will be in binary format
* Numbers are of the following forms
   * unsigned
   * signed -> Fixed Point and Floating Point
   * Fixed Point -> sign magnitude, 1's complement, 2's complement
   * Floating point -> Single Precision, Double Precision
* Character are of the following forms
   * ASCII
   * EBCDIC
* Unsigned Numbers -> No sign of positive or negative
* Signed Number -> Numbers that can be positive or negative
* Arithmetic Numbers -> Numbers on which Arithmetic operations can be performed, these are Signed Numbers
* Fixed Point -> Directly represented in Binary
* Floating Point -> 1 * mantissa * 2<sup>exponent</sup>

### ASCII

* American standard Code for information interchange
* It is an encoding system to represent characters into binary
* ASCII encoding consists of 8 bits

### EBCDIC

* Extended Binary Coded for information interchange
* Uses 8 bits for encoding

### Numbers and Units

* Nibble -> 4 bits
* Byte -> 8 bits
* LSB -> Least Significant bit
* MSB -> Most Significant bit

### Number System

* A number system of base-b will have digits from 0 to b-1
* Types of Number systems
   * Binary -> Base 2 -> range 0, 1
   * Octal -> Base 8 -> range 0, 7
   * Decimal -> Base 10 -> range 0, 9
   * Hexadecimal -> Base 6 -> range 0, F

### Checking validity of Numbers

1. (1234)<sub>6</sub> -> valid
2. (2329)<sub>9</sub> -> invalid
3. (62AC)<sub>16</sub> -> valid
4. (1012)<sub>3</sub> -> valid
5. (3431)<sub>4</sub> -> invalid
6. (1265)<sub>5</sub> -> invalid
7. (6215)<sub>6</sub> -> invalid
8. (8294)<sub>10</sub> -> valid

### Binary Number System

#### Binary to Decimal

* We need to multiply each binary digit by 2 <sup>digit position</sup> and add all the products to get the decimal equivalent
* if n bit binary number is b<sub>n-1</sub>, ..., b<sub>1</sub>, b<sub>0</sub>, then decimal = <sub>0</sub><sup>n-1</sup>E(b<sub>i</sub> * 2 <sup>i</sup>)

#### Decimal to Binary

* Divide the given decimal by 2, and note the remainders everytime, till you are left with 0 or 1
* Then note all the digits from the last remained to the 1st remainder, you will get your binary number

### Units and Conversions

* Kilo -> in terms of memory 2<sup>10</sup> -> in terms of distance 10<sup>3</sup> 
* Mega -> in terms of memory 2<sup>20</sup> -> in terms of distance 10<sup>6</sup>
* Giga -> in terms of memory 2<sup>30</sup> -> in terms of distance 10<sup>9</sup>
* Tera -> in terms of memory 2<sup>40</sup> -> in terms of distance 10<sup>12</sup>
* second = 1
* millisecond = 1/10<sup>3</sup> = 10<sup>-3</sup>
* microsecond = 1/10<sup>6</sup> = 10<sup>-6</sup>
* nanosecond = 1/10<sup>9</sup> = 10<sup>-9</sup>
* picosecond = 1/10<sup>12</sup> = 10<sup>-12</sup>
* 1us = 10<sup>-6</sup>sec = 1/1M
* milli = 10<sup>-3</sup>sec = 1/1K
* nano = 10<sup>-9</sup>sec = 1/1G

### Terminologies

#### CPU cycle
* In one cycle, CPU can perform only 1 operation
* Time taken for a cycle is call CPU cycle time

#### Memory Cycle
* In one memory cycle, memory can perform 1 operation

#### Memory Access Time
* Time taken for 1 read/write to happen in the memory

#### Throughput
* Number of operations performed in 1 unit of time

#### Speedup or Performance Gain
* This metric is used to compare machines or techniques or softwares or hardwares, etc which perform same task.
* Performance is calculated as 1/time_taken

### Memory Access

#### Memory Address

* The Main Memory, (RAM) is divided into blocks called cells, so that data access can be easily done by tje CPU
* The cells are numbered from 0 onwards, so the CPU, queries data/instruction from the specific memory address
* For each memory access, CPU sends address to the memory and tells it to perform either read or write operation.

### Basics of Operating Systems

* OS is a software that interfaces between user and hardware
* It provides a set of utilities to simplify application development/execution

#### Services of OS
* User interface
* Program Execution
* I/O Operation
* File-System Manipulation
* Inter Process Communication
* Error Detection
* Resource Allocation
* Accounting
* Protection and Security

#### Multitasking OS
* It assigns multiple programs to run sequentially while switching context really fast, that it gives the illusion of multitasking

### HW

* Binary to Decimal
1. (1101)<sub>2</sub> = 13
2. (10110)<sub>2</sub> = 22
3. (1101110)<sub>2</sub> = 110
4. (10101)<sub>2</sub> = 21
5. (1100)<sub>2</sub> = 12
6. (101)<sub>2</sub> = 5
7. (11001)<sub>2</sub> = 25

* Decimal to Binary
1. 27 = 11011
2. 19 = 10011
3. 33 = 100001
4. 50 = 110010

* Units and Conversions
1. 128 * 64M = 2<sup>7</sup> * 2<sup>6</sup> * 2<sup>20</sup> = 8G
2. 2G/64 = 2 * 2<sup>30</sup> / 2<sup>6</sup> = 32M
3. 1ms = 10<sup>-3</sup> seconds
4. 1us = 10<sup>-3</sup> ms
5. 1 sec = 10<sup>6</sup> us
6. 5 us = 5 * 10<sup>-3</sup> ms
7. 0.5 ms = 500 us
8. 0.02 us = 20 ns
9. 0.0004 ms = 0.4 us = 400 ns