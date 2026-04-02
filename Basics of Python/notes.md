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





### Miscellaneous Helpful Functions

1. Input
2. Range(start, stop, step)
3. Enumerate -> returns 2 values, index and value (used with lists and for loops)
4. Print Square * pattern
5. Print Hollow square * pattern