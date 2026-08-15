# Data Structures and Programming 5 to 6 marks

DO ALL HOMEWORK QUESTIONS!!

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

### Sparse Matrix

* Sparse matrix is a matrix in which relatively few entries are non-zero

#### Lower Triangular Matrix

* Lower Triangular matrix : elements above principle diagonal are zero. Always a square matrix. So, for every i < j in A[i][j] = 0
* Row major order
   * Given nxn matrix number of non zero elements = n(n+1)/2
   * Address = BA + [[i(i-1)/2 + {j-1}] * Size]

* Column major order
   * Given nxn matrix, total elements from 1st column till j-1 columns = n + n-1 + n-2 + n-3 ... + n-j-2 = (j-1)/2 [n + (n-j-2)] = n(j-1) - (j-1)(j-2)/2
   * Address = BA + [n(j-1) - (j-1)(j-2)/2 + (i-j)] * size

* Upper Triangular matrix: Elements below the principle diagonal are zero

* IN GENERAL if a[lb1 ... ub1][lb2 ... ub2]
   * Row major order Address = BA + [(i-lb1) * (ub2-lb2+1) + (j-lb2)] * size
   * Column major order Address = BA + [(j - lb2) * (ub1-lb1 + 1) + (i-lb1)] * size 

* Bound Adjustment, If the bound does not start from 1, adjust lower bound to 1 and all other bounds correspondingly, also apply the same adjustment for the questions
   * Ex A[-5][-19] Find A[10][7]-> A[1][25] and A[16][13]


#### Upper Triangular Matrix

* Upper Triangular matrix : elements below principle diagonal are zero. Always a square matrix. So, for every i > j in A[i][j] = 0

* Column major order
   * Given nxn matrix number of non zero elements = n(n+1)/2
   * Address = BA + [[j(j-1)/2 + {i-1}] * Size]

* Row major order
   * Given nxn matrix
   * Address = BA + [n(i-1) - {(i-1)(i-2)/2} + (j-i)] * size

### 3-D Array

* So in C, 3D Arrays are stored in the form of frames. A frame is one set of 2D array.
* So a 3x3x3 matrix will have 3 frames of 3x3 matrices.
* A[i][j][k] -> i : Frame, j : row, k : columns
* for an nxnxn matrix Address = BA + [(i-1) * n<sup>2</sup> + (j-1)*n + (k-1)] * size
* In general Address = BA + [(i-1) * # of rows * # of cols + (j-1)* # of cols + (k-1)] * size
* Considering A[LB1 ... UB1][LB2 ... UB2][LB3 ... UB3] Address of A[i][j][k]
   * Address = BA + [(i-LB1)(UB2-LB2+1)(UB3-LB3+1) + (j-LB2)(UB3-LB3+1) + (k-LB3)] * Size

### Advantages of Arrays

1. Random accessing of elements
2. Cache friendly data structure

### Disadvantages of Arrays

1. Static allocation
2. Memory wastage occurs
3. Time consuming process for shifting the elements in the array

## Stacks

1. Stack is a linear data structure
2. Stack is one ended data structure operations are performed only on end indexed by top
3. operation on stack are push and pop
4. stack works on LIFO principle (Last in First out)
5. top is the only index on the stack. it is incremented upon push and decremented on pop.

### Implementation of stack

```c
# define max 100;
int a[max];
int top;

void init()
{
   top = -1;
}

int isEmpty()
{
   if(top == -1)
      return 1;
   else
      return 0;
}

int isFull()
{
   if(top == max-1)
      return 1;
   else
      return 0;
}

void push(int x)
{
   if(top == max-1)
   {
      printf("stack is full");
      return;
   }
   top = top + 1;
   a[top] = x; 
}

int pop()
{
   int data;
   if(top == -1)
   {
      printf("stack is empty");
      return -1;
   }
   data = a[top];
   top--;
   return data;
}
```

### Applications of stack

1. Permutation Generator
2. Recursion
3. Expression in Computers -> Infix, Prefix, Postfix
4. Parsing
5. Push Down Automata (PDA)

#### Permutation Generator

* Stack can generate different permutations in which element will be entered in given order but it can be popped any time

1. 
```text
total possible permutations with abc = abc, acb, bac, bca, cab, cba

You cannot change insertion order of abc, therefore stack operations for every permutation is as follows

abc = push(a) pop push(b) pop push(c) pop
acb = push(a) pop push(b) push(c) pop pop
bac = push(a) push(b) pop pop push(c) pop
bca = push(a) push(b) pop push(c) pop pop
cab = push(a) push(b) push(c) pop -> cannot pop a as it is at the bottom
cba = push(a) push(b) push(c) pop pop pop

```

2. 
```text
How many permutations are possible with abcd
out of = cbad, cbda, cabd, cadb, cdba, cadb
cabd not possible -> Through eye balling
cadb not possible -> Through eye balling
cdab not possible -> Through eye balling
```


* Number of permutations generated by n distinct alphabet given in order
   * Catalan number Cn = (1/n+1) <sup>2n</sup>C<sub>n</sub>
   * C3 = (i/4)<sup>6</sup>C<sub>3</sub> = (i/4) * (6!/3!(6-3)!)

#### Expressions in Computer

* C follows Associativity and Precedence rule
* Order of evaluation of operator is decided by precedence rule
   1. ()
   2. ^ right to left
   3. / * left to right
   4. + - left to right
   5. = right to left
   
* Infix : a+b -> operand op operand
* Prefix (Polish) : +ab -> op operand operand
* Postfix (Reverse Polish) : ab+ -> operand operand op

#### Infix to Prefix

* A-B/C*D^E -> A-(B/C)*(D^E) -> A-(B/C)*(^DE) -> A-(/BC)*(^DE) -> A-(*/BC^DE) -> -A*/BC^DE

#### Infix to Postfix

* A-B/C*D^E -> A-(B/C)*(D^E) -> A-(BC/)*(DE^) -> A-(BC/DE^)* -> A-(BC/CD^*) -> ABC/DE^*-


## HW

### L2

1. arr[-15 ti 15][-7 to 7] find address of arr[10][5] in column major order if starting address is 500 and size is 4 bytes

2. Consider a 1D array with 101 elements. if base address of the array is 108 and size of each array element is 4 bytes then address of a[7] is? array index starts from -25

3. Consider a 2D array[28 to 39][-3 to 10] with natural numbers stored. find element at location arr[35][10] in row major order and column major order

And more in ppt