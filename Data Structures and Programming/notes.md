# Data Structures and Programming 5 to 6 marks

* Data Structure is organization and management
* It specifies the storage format and 
* It performs operations on them that enables effective access and modification 

## Types of Data structures

1. Linear -> elementes are arranged in linear or sequential fashion
   * Array
   * linked list
   * Queue
   * Stack
2. Non-linear -> elements are arranged in non linear fashion / Heirarchical fashion
   * Binary Tree
   * Binary Search Tree
   * AVL Tree 
   * Heaps
   * Graph
   * Hashtable


## Arrays

* Array is a linear data structure
* Array elements are stored in memory in sequential manner
* It has continous and static memory allocation
* Array is a collection of same data type
* All elements in an array are accessed through the index
* Starting address of the array is also called as <b>Base Address</b>
* Total size of array = (Size of datatype) * (Number of elements to be stored in the array)
* Memory address = (Base Address) + ([Size of Datatype] * Index)
* Number of elements = Upper Bound - Lower Bound + 1
* Number of elements before A[i] = (i - Lower Bound)

1. A[1..... 100] Base Address = 1000, 2 bytes occupied by each element, A[78]?

```
elements before A[i] = 78 - 1 = 77
Memory address = 1000 + (2 * 77) = 1154
```

### 2 Dimensional Arrays

* Elements in 2 D arrays are stored as row major and column major order in the memory
* Row major Address = Base address + [number of elements * number of elements in each row + no of elements arranged in last row]

1. A[1...30][1..40] Base Address = 1000; Size = 2B; Find Address of A[20][19]

```
elements before = 19(40) + 18 = 778
total size = 778*2 = 1556

Address = 1000 + 1556 = 2556

```

* Column major Address = Base address + [number of elements * number of elements in each column + no of elements arranged in last column]

1. A[1...100][1...100]; BA = 1000; Size = 2B; Find address of A[50][48] in column major order

```
elements before = 47*100 + 49 = 4749
total size = 4749 * 2 = 9498

Address = 1000+9498 = 10498
```

## HW

### L1