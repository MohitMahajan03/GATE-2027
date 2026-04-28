# Practice Problems

## Basics of Programming and problem Solving

1. We first try to understand the probem statement through flowcharts and pseudo codes


### Flowchart

* A flowchart is a graphical representation of a process, system or an algorithm
* It uses symbols and arrows to show the sequence of the steps, needed to complete a task.
* There are useful in visualizing how to solve a problem and make the process easier to follow.

1. Oval -> start and stop
2. parallelogram -> input and output
3. rectangle -> process
4. Diamond -> condition
5. arrows -> direction of flow
6. cirle -> connector

### Pseudo Code

* A pseudo code is a simple way of describing an algorithm in plain language or a mix of code like and natural language instructions
* It does not follow any specific programming language syntax, making it easier to understand even for those without programming knowledge.
* pseudo code is often used as a step before writing actual code.

### Problems

1. Take a number input from user and print reverse of it
2. Check if a number input from user is a palindrome or not
3. Find the largest Number in the given list [10, 4 19, 11, 23]

### Program

4. Draw a Square full of stars providing n as side of square

``` 
n = int(input("Enter the number of stars for each side "))

for i in range(0, n):
    for j in range(0, n):
        print("*", end=" ")
    
    print()
```

5. Draw a Hollow Square of stars provided n as side of square

``` 
n = int(input("Enter the number of stars for each side "))

for i in range(0, n):
    print("*", end=" ")
    for j in range(0, n-2):
        if i == 0 or i == n-1:
            print("*", end=" ")
        else:
            print(" ", end = " ")
    
    print("*", end=" ")
    
    print()
```

6. Draw a rectangle of given length and breadth with "*"

```
n = int(input("Enter the length of the rectangle "))
m = int(input("Enter the breadth of the rectangle "))

for i in range(0, n):
    for j in range(0, m):
        print("*", end=" ")
    
    print()
```

7. Draw a right angled triangle.

```
n = int(input("Enter the length of the triangle "))

for i in range(0, n):
    for j in range(0, i+1):
        print("*", end=" ")
    
    print()
```

8. Draw an inverted right angled triangle

```
n = int(input("Enter the length of the triangle "))

for i in range(0, n):
    for j in range(0, n-i):
        print("*", end=" ")
    
    print()
```

9. Draw a pyramid pattern

```
n = int(input("Enter the length of the pyramid "))
space_count = 0
for i in range(0, n+1):
    space_count = (n*2)-i

    for j in range(0, n-i):
        print(" ", end="")
    for j in range(0, i):
        print("*", end=" ")
    
    print()
```

10. Draw a inverted pyramid pattern

```
n = int(input("Enter the length of the pyramid "))
space_count = 0
for i in range(n, 0, -1):
    space_count = (n*2)-i

    for j in range(0, n-i):
        print(" ", end="")
    for j in range(0, i):
        print("*", end=" ")
    
    print()
```

11. Draw right triangle with numbers

```
n = int(input("Enter the length of the triangle "))

for i in range(0, n):
    for j in range(0, i+1):
        print(j+1, end=" ")
    
    print()
```

12. Draw Floyd's triangle

```
n = int(input("Enter the number of rows "))

count = 1
for i in range(0, n + 1):
    for j in range(0, i):
        print(count , end =" ")
        count += 1
    
    print()
```

13. Draw a hollow right angled triangle

```
n = int(input("Enter the number of stars for each side "))

for i in range(0, n):
    for j in range(0, i + 1):
        if j == i or i == n-1 or j == 0:
            print("*", end=" ")
        else:
            print(" ", end = " ")
    
    print()
```

14. Inverted hollow right angled triangle

```
n = int(input("Enter the number of stars for each side "))

for i in range(n, 0, -1):
    for j in range(0, i):
        if j == i-1 or i == n or j == 0 or i == 0:
            print("*", end=" ")
        else:
            print(" ", end = " ")
    
    print()
```

15. Given List l1 = [10, 20, 30, 40, 50] calculate sum of list

```
l1 = [10, 20, 30, 40, 50]

print(sum(l1))
```

16. Find the largest element in the list l1 = [1, 9, 6, 4, 3, 11]

```
l1 = [1, 9, 6, 4, 3, 11]

print(max(l1))
```

17. Remove duplicate elements from a list l1 = [1, 2, 2, 1, 7, 3, 7, 6, 9]

```
l1 = [1, 2, 2, 1, 7, 3, 7, 6, 9]

l1 = list(set(l1))
print(l1)
```

18. Check if all elements in list is unique l1 = [1, 3, 2, 4, 5, 6]

```
l1 = [1, 3, 2, 4, 5, 6]

if (len(l1) == len(list(set(l1)))):
    print("All elements are unique")
else:
    print("Not all elements are unique")
```

19. Reverse a list l1 = [10, 20, 30, 40, 50]

```
l1 = [10, 20, 30, 40, 50]

l1 = l1[::-1]
print(l1)
```

20. Count all odd and even elements in list l1 = [4, 3, 9, 7, 6, 12, 13]

```
l1 = [4, 3, 9, 7, 6, 12, 13]

even = []
odd = []
for ele in l1:
    if ele%2 == 0:
        even.append(ele)
    else:
        odd.append(ele)
        
print("even numbers = ", len(even))
print("odd numbers = ", len(odd))
```

21. Find maximum difference between 2 consecutive elements in a list l1 = [1, 3, 9, 6, 12, 40, 13]

```
l1 = [1, 3, 9, 6, 12, 40, 13]

mins = []
for i in range(0, len(l1)):
    if i == 0:
        mins.append(l1[i] - l1[i + 1])
    elif i == (len(l1) - 1):
        mins.append(l1[i] - l1[i - 1])
    else:
        mins.append(l1[i] - l1[i - 1])
        mins.append(l1[i] - l1[i + 1])
        
print(min(mins))
```

22. Rotate a list by k, l1 = [1, 2, 3, 4, 5], k = 2

```
l1 = [1, 2, 3, 4, 5]
k = 2

ll = l1[:k+1]
print(ll)
rl = l1[k+1:]
print(rl)

l1 = rl + ll

print(l1)
```

23. Check whether a list is a subset of other list or not l1 = [1, 2, 3] l2 = [1, 2, 3, 4, 5] give True or False

```
l1 = [1, 2, 7] 
l2 = [1, 2, 3, 4, 5]

flag = True
for i in l1:
    if i not in l2:
        flag = False
        break

print(flag)
```

24. Check whether a tuple is a palindrome or not t1 = (1, 2, 3, 2, 1)

```
t1 = (1, 2, 3, 2, 1)

for i in range(0, len(t1)):
    if t1[i] != t1[len(t1)-1 - i]:
        print("Not a palindrome")
        exit()
print("It is a palindrome")
```

25. Merge 2 lists into a dictionary given -> keys = ['a', 'b', 'c'] and values = [1, 2, 3]

```
keys = ['a', 'b', 'c'] 
values = [1, 2, 3]

dict_ = {}

for i in range(0, len(keys)):
    dict_[keys[i]] = values[i]
    
    
print(dict_)



_________OR_________

keys = ['a', 'b', 'c'] 
values = [1, 2, 3]

dict_ = dict(zip(keys, values))
print(dict_)

```