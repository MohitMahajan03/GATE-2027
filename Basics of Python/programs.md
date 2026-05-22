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
26. Given a string "Hello", reverse it
```
s = "Hello"
s = s[::-1]
print(s)
```

27. Check if given string is palindrome s = "abba"
```
s = "abba"
r = s[::-1]
if r == s:
    print("string is a palindrome")
else:
    print("not a palindrome")
```

28. Count Vowels and Consonants
```
word = "Gate 2027"

vowels = 0
consonants = 0

for letter in word:
    if letter.lower() in ['a', 'e', 'i', 'o', 'u']:
        vowels += 1
        continue
    elif letter.isalpha():
        consonants += 1
    else:
        continue
    
    
print("Number of Vowels = ", vowels)
print("Number of consonants = ", consonants)
```

29. Remove duplicate characters from "Hello"
```
word = "Hello"
new_word = ""

for letter in word:
    if letter not in new_word:
        new_word += letter
        
print(new_word)
```
30. Find 1st non repeating character string = "aabbaccdef"
```
word = "aabbaccdef"

for letter in word:
    frq = word.count(letter)
    if frq == 1:
        print(letter)
        break
```
31. check whether 2 string are anagram or not. If s1 = "listen", then s2 = "tsilen" so characters in s1 and s2 are are same.
```
s1 = "listen"
s2 = "tsilen"

if sorted(s1) == sorted(s2):
    print("The strings are anagram")
else:
    print("Not an anagram")
```

32. Print the frequency of each character in string
```
 word = "aabbccdefabx"

word_dict = {}

for letter in word:
    word_dict[letter] = word.count(letter)
    
print(word_dict)
```
33. Print the longest word in the string s = "I am preparing for placements"
```
sentence = "I am preparing for placements"

words = sentence.split(" ")

counts = {}
counts["max"] = ""
for word in words:
    if len(word) > len(counts["max"]):
        counts["max"] = word
        
print(counts["max"])
```

34. Print all substrings of a string
```
# s1 = "abc"
# substrings = a, ab, abc, bc, c, b
word = "abc"

for i in range(0, len(word)):
    for j in range(i + 1, len(word) + 1):
        print(word[i : j])
```
35. Reverse a sentence. s = "I love programming"
```
sentence = "I love programming"

words = sentence.split(" ")

words = words[::-1]

sentence = " ".join(words)
print(sentence)
```
36. Print max element of the list using functions
```
def max_of_list(lst):
    return max(lst)
    
print(max_of_list([10, 20, 30, 40]))


OR 

def max_of_list(lst):
    max_ = lst[0]
    for num in lst:
        if num > max_:
            max_ = num
    return max_
    
print(max_of_list([10, 20, 30, 40]))

```
37. Print sum of all elements of list using functions
```
def sum_of_list(lst):
    return sum(lst)
    
print(sum_of_list([10, 20, 30, 40]))


OR


def sum_of_list(lst):
    sum_ = 0
    for num in lst:
        sum_ += num
    return sum_
    
print(sum_of_list([10, 20, 30, 40]))
```
38. A number is given in a list format and you need to add 1 to it
    * Input: [1, 2, 9]
    * Output: [1, 3, 0]
```
def add_one(lst):
    carry = 0
    lst = lst[::-1]
    lst[0] += 1
    if lst[0]//10 > 0:
        carry = lst[0]//10
        lst[0] = lst[0]%10
        
    # print(carry)
    if carry != 0:
        for num in range(1, len(lst)):
            # print(lst[num], carry)
            lst[num] += carry
            if lst[num]//10 > 0:
                carry = lst[num]//10
                lst[num] = lst[num]%10
            else:
                carry = 0
    if carry != 0:
        lst.append(carry)

    return lst[::-1]
    
    
print(add_one([9, 9, 9]))
```

39. Print missing number, input always starts with 0 and always only 1 number is missing
    * Input: [0, 1, 2, 3, 4, 6, 7, 8]
    * Output: 5
```
def check_miss(lst):
    for i in range(len(lst)):
        if lst[i] != i:
            return i

print(check_miss([0, 1, 2, 3, 4, 6, 7, 8]))



OR


def check_miss(lst):
    n = len(lst)
    sum1 = (n*(n+1))/2
    sum2 = sum(lst)
    
    return int(sum1 - sum2)

print(check_miss([0, 1, 2, 3, 4, 6, 7, 8]))

```

40. Check whether given list is sorted or not
```
def check_sorting(lst):
    for i in range(1, len(lst) - 1):
        if lst[i - 1] > lst[i] or lst[i + 1] < lst[i]:
            return False
    return True

print(check_sorting([0, 1, 2, 3, 4, 10, 7, 8]))
```

41. Move zeros to the end of the list
    * Input: [7, 0, 9, 0, 0, 1, 2]
    * Output: [7, 9, 1, 2, 0, 0, 0]
```
def sort_zeros(lst):
    count = 0
    for i in range(len(lst)):
        if lst[i] != 0:
            count += 1
    i = 0
    while i < count:
        print("current ele = ",lst[i])
        if lst[i] == 0:
            for j in range(i + 1, len(lst)):
                lst[j - 1] = lst[j]
                
            lst[j] = 0
            print("index = ", i)    
            print(lst)
            
        else:
            i += 1
    return lst

print(sort_zeros([7, 0, 9, 0, 0, 1, 2]))
```

42. Longest length of consecutive 1's
    * Input: [1, 1, 0, 1, 1, 1]
    * Output: 3
```
def count_ones(lst):
    count = 0
    max_ = 0
    for i in lst:
        if i == 1:
            count += 1
        else:
            if count > max_:
                max_ = count
            count = 0
    
    if count > max_:
        max_ = count
    return max_
    
print(count_ones([1, 1, 0, 1, 1, 1]))
```

43. Count number of digits in a number using recursion

```
def count(n, count_s = 0):
    if n == 0:
       return count_s
    
    count_s += 1
    return(count(n//10, count_s))
    
print(count(1000000))
```

44. Print Fibonacci series using recursion

```
def fib(n):
    if n <= 1:
        return n
    
    return fib(n-1) + fib(n-2)

print(fib(7))
```

45. Print numbers from n to 1 and 1 to n

```
def show(n):
    if n == 0:
        return 0

    print(n)
    show(n-1)
    print(n)
```

46. Reverse a number using recursion

```
def reverse(n, rev = 0):
    if n == 0:
        return rev
        
    else:
        return reverse(n//10, ((rev * 10) + n%10))
    
    
print(reverse(1234))
```
47. Reverse string using recursion

```
def rev(s):
    if len(s) <= 0:
        return s
    return rev(s[1:]) + s[0]
```

48. Check whether a string is palindrome or not using recursion

```
def palindrome(s):
    if len(s) <= 1:
        return True

    if s[0] != s[-1]:
        return False

    return palindrome(s[1:-1])

print(palindrome("madam"))
```
49. Calculate Power of a number using recursion

```
def power(x, n):
    if n == 0:
        return 1
    
    return x * power(x, n-1)

print(power(5, 2))
```

50. Calculate sum of digits in a number using recursion

```
def sums(n):

    if n == 0:
        return 0

    return sums(n//10) + n%10
    
    
print(sums(65))
```

51. Check if array is sorted or not using recursion

```
def order(lst):
    if len(lst) < 2:
        return True

    if lst[-2] > lst[-1]:
        return False

    return order(lst[:-1])

print(order([4, 5, 6, 7, 8]))
```

52. Convert decimal to binary using recursion

```
def dectobin(n):
    if n == 0:
        return ""

    return dectobin(n//2) + str(n%2)

print(dectobin(16))
```

53. Print first occurence of a uppercase character in a string using recursion

```
def is_upper(s):
    if len(s) == 0:
        return False

    elif s[0].isupper():
        return s[0]

    return is_upper(s[1:])

print(is_upper("maa"))
```