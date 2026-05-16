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
```

### Loops

* When we repeatedly want to perform similar type of operation.

1. For
2. While

### Inbuilt Data Structures in Python

* All numeric data types are immutable. Ex: 
    ```
    a = 4 # mem addr -> 1972 ; 
    a = 10 # mem addr -> 647 
    #Value of the object is not updated in the same address
* ```
    print(id(a)) # Prints the address where 'a' is pointing to
* The old value in the old address is picked up by the garbage collector

1. int : (int + int) -> int ; (int - int) -> int ; (int * int) -> int ; (int / int) -> float
2. float
3. complex -> contains real and imaginary part 
    ```
    a = complex(3, 4)
    print(a.real) # Prints 3
    print(a.imag) # Prints 4
4. string -> immutable, ordered data structure

    * Slicing -> str[start_idx : end_idx : step_size] -> By default step_size is +1.
    * Reverse -> str[ : : -1]
    * upper -> str.upper() -> Capitalize all characters in the string; To check -> st.isupper()
    * lower -> str.lower() -> Lower case all characters in the string; To check -> str.islower()
    * Replace -> 
        ```
        str1 = "I love Java"
        a = str1.replace("Java", "Python") 
5. list -> mutable, indexed, ordered, We can perform slices on lists

    * Append -> add element to the end of the list: l1.append(10)
    * Insert -> add element at a given index without overwriting: l1.insert(1, 50)
    *  Remove -> Remove element from the list : l1.remove(20)
    *  Clear -> Remove all elements from the list : l1.clear()
    *  Delete -> remove values from particular index : del l1[1]
    *  Pop -> remove last element from list : l1.pop()
   ``` 
    list[start_index : stop_index : step_count]
    list_rev[ : : -1]

6. tuple -> (10, 20, 30, 40, 50)
    * Tuples are immutable, indexed, ordered, We can perform slices on tuples, same way as lists
7. set -> {10, 30 ,50}
    * Sets are mutable, unordered, No indexing, No slicing, No duplicates, We cannot store other sets in a set
    * Mutable objects cannot be stored in a set.
    * Remove -> Removes data from the set : s1.remove(10)
    * Update -> Updates data in the set : s1.update({10, 20})
    * Union -> adds 2 sets : s1.union(s2)
    * Difference -> has elements that belongs uniquely to 1st set: s1.difference(s2)
    * Intersection: gets common elements between the 2 sets: s1.intersection(s2)
    * Disjoint -> if there are no common elements : s1.isdisjoint(s2)
8. dictionary -> It is used to store store data in key value pair format
    * Indexing of dictionary is done on the keys
    * Keys cannot be duplicate
    * Dictionary is mutable and values can be of any object type
    * But Dictionary keys are always immutable objects.
    * Keys -> Returns all the keys in the dictionary : dict.keys()
    * Values -> Returns all the values in the dictionary : dict.values()
    * Items -> Return key value pairs : dict.items()
    * From Keys -> Initializes keys using a list : dict.fromkeys(students, None) -> Initializes all keys to None
    * Update -> Updates the key value pair : dict.update({"Ravi" : 74})
9.  range
10. frozen set -> A set which is frozen, immutable
    * a = frozenset({1, 2, 3})
    * All properties of set are applicable in frozen set

### Functions

* They are Reusable block of code
```
def main(input arguments):
    return
```
* When a function returns nothing it means it returns None
* Order of arguments that are passed is important for positional arguments
* So how do you pass any number of positional arguments? *args -> meaning it can take more than 1 input; And args is of type tuple;
* Order of arguments does not matter in keyword arguments -> fun(age = 32, name = "Ravi")
* def fun(**kwargs) -> fun(name="Ravi", age=26) -> **kwargs will be of type dictionary
* Nested Functions are allowed in python
* Lambda functions : They are anonymous functions
  * lambda (set of inputs) : set of instructions
  * a = lambda x,y,z : x+y+z
  * type(a) -> function
  * Example        
    ```
        l1 = [9, 7, 6, 12, 20, 4, 3, 15] # Filter all values < 10
        a = list(filter(lambda x: x > 10, l1))

        a = reduce(lambda x, y : x + y, l1) # reduces the entire list to 1 value

        a = map(lambda x : x * 4, l1) # allows an operation to be performed on all the values of a list
    ```

### Miscellaneous Helpful Functions

1. Input
2. Range(start, stop, step)
3. Enumerate -> returns 2 values, index and value (used with lists and for loops)
4. Print Square * pattern
5. Print Hollow square * pattern

### Exception Handling

1. Types of errors
    1. Syntax error: This types of error occurs when there is a issue in the syntax of the code.
    2. Indentation error: This type of error occurs when there is not proper indentation in the code.
    3. Type error: This type of error occurs when the value is not of expected type.
        ```
        a = 1
        b = "2"
        c = a+b
        ```
    4. Value error: This type of error occurs when the value is not in the expected range or format.
        ```
        a = int("abcd")
        l1 = [10, 20, 30]
        a = l1.index(100)
        a,b = 1,2,3,4
        ```
    5. Zero Division error: When you try to divide by 0, then this error occurs
    6. Name error: When a variable is not defined and is being accessed, this error occurs
    7. Attribute error: This type of error occurs when you try to access an attribut that does not exist.
        ```
        s = "hello"
        s.reverse() # reverse() does not exist
        ```
    8. Index error: This type of error occurs when you try to access index out of range.
        ```
        l1 = [10, 30, 40]
        print(l1[8])
        ```

2. Exception Handling: It is used to gracefully handle the error or exceptions that occur
* Any code that may cause error, should be written in the "try" block.
* The "try" block will throw the error to the "except" block and "except" block will handle the exception
```
try:
    a = int(input("Enter the 1st number"))
    b = int(input(Enter the 2nd number"))
    c = a/b
except Exception as e:
    print(e)

print(c)

```
* Finally block: This block of code gets executed irrespective of whether exception has occurred in try "block" or not
    ```
    try:
        a = int(input("Enter a number"))
        c = 10/a
        print(c)
    except Exception as e:
        print(e)
    finally:
        print("Hello")
    
    ```
* Else block: This block of code gets executed when there is no exception in the try block.

```
try:
    a = int(input("Enter the number))
    c = 10/a
    print(c)
except Exception as e:
    print(e)

else:
    print("Else executed")

finally:
    print("Finally")
```

### Object Oriented Programming

* Class -> Blueprint
* Objects -> instances generated from the blueprint

```
class Student:
    def __init__ (self, name, roll_no, cls): # Constructor
        self.name = name
        self.roll_no = roll_no
        self.cls = cls

stud1 = Student("Deb", 123, 10)
```

#### Principles of OOP

1. Abstraction
    * The act of representing essential features without including background details is called abstraction.
2. Encapsulation
    * The wrapping up of data and it's associated functions into a single unit/class is called encapsulation
3. Inheritance -> (Refer types_of_inheritance.png)
    * When one class wants to inherit the properties or methods of another class then it is called as inheritance.
    * Simple inheritance : One class is inheriting properties of only 1 other class
    * Multiple inheritance: If one class is inheriting properties from multiple classes.
    * Multilevel inheritance: When there are multiple levels of inheritance
    * Heirarchical inheritance: When more than 1 class inherits from 1 class
    * Hybrid inheritance: Mix of multilevel and heirarchical inhertance.

    ```
    Access Modifier    name    Access level
    public             name     It can be accessed anywhere
    protected          _name    It can be accessed in class or subclass
    private            __name   It can be accessed only in the class
    ```

    ```

4. Polymorphism
    * Representing the same thing in multiple forms is called as polymorphism
    ```
    class Animal:
        def sound():
            print("Hello")
    class Dog (Animal):
        def sound():
            print("bark")
    class Cat (Animal):
        def sound("Meow")
    
    def get_sound(animal):
        animal.sound()
    
    get_sound(Dog())
    get_sound(Cat())
    ```

### Iterator

* An iterator it is a data stream that helps in accessing the data one by one.
* An iterator is created by sending a list to the iter class
    ```
    it = iter(lst)
    print(next(it))
    ```

```
class NewIterator:
    def __init__(self, maxvalue):
        self.maxvalue = maxvalue
        self.current = 1

    def __iter__ (self):
        return self

    def __next__(self):
        if self.current <= self.maxvalue:
            val = self.current
            self.current += 1
            return val
        else:
            raise Stop Iteration


obj = NewIterator(s)

for i in obj:
    print(i)
```

* Creating a Range
```
class NewRange:
    def __init__(self, start, end):
        self.start = start
        self.end = end

    def __iter__(self):
        return self
    
    def __next__(self):
        if self.start >= self.end:
            raise StopIteration
        
        val = self.start
        self.start += 1
        return val
```
* Creating a reverse iterator
```
class ReverseIterator:
    def __init__(self, maxvalue):
        self.maxvalue = maxvalue
        self.current = self.maxvalue

    def __iter__ (self):
        return self

    def __next__(self):
        if self.current >= 0:
            val = self.current
            self.current -= 1
            return val
        else:
            raise Stop Iteration
```

* Creating a Fibonacci Iterator
```
class FiboIterator:
    previous = 0
    def __init__(self, maxvalue):
        self.maxvalue = maxvalue
        self.current = 1

    def __iter__ (self):
        return self

    def __next__(self):
        if self.current <= maxvalue:
            val = self.current + previous
            previous = self.current
            self.current = val
            return val
        else:
            raise Stop Iteration
```


### Generator

* A Generator is a function using which you can create an iterator easily.
```
def mygen():
    yiedl 1 # yield will return this value and pause
    yield 2
    yield 3

obj = mygen()

print(next(obj))
```

* Creating a Fibonnaci Generator
```
def fib(n):
    a = 0
    b = 1
    for _ in range(n):
        yield a
        a,b = b, a+b

print(list(fib(5)))
```

* Creating even number generator
```
def even(n):
    for i in range(0, n, 2):
        yield i

print(list(even(10)))
```

* Generator of Squares

```
def squares(n):
    for i in range(0, n+1):
        yield i**2

print(list(squares(5)))
```