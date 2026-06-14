# Linear Algebra 7 to 8 marks
## Basics of Determinants

### Determinants
* Only square Matrices have determinants and it is nothing but a real or complex number.
```
|A| = |a b| = (ad - bc)
      |c d|

      |2  3| = (-2 -12) = -14
      |4 -1|

      |(3 + 2i)  -i| = (3 + 2i)(3 - 2i) - (i.i) = 12
      |i   (3 - 2i)|


|B| = |a b c| = (a) |e f| -(b) |d f| + (c) |d e| 
      |d e f|       |h i|      |g i|       |g h|  
      |g h i|

```

* Calculating Determinants using SARRUS method
```
|1 -2  3|    1  -2   3   1  -2
|4  2  0| =  4   2   0   4   2
|1  2 -1|    1   2  -1   1   2

    Top to bottom Diagonally             Bottom to top Diagonally
[(1*2*-1) + (-2*0*1) + (3*4*2)] - [(1*2*3) + (2*0*1) + (-1*4*-2)]

= 22 -14 = 8
```
* Method of solving 4 x 4 Determinant (refer 4x4_det.png)
    * therefore sign applied will be sign a<sub>ij</sub> = (-1)<sup>i+j</sup>
    * Follow same as 3 x 3 matrix

### Class Sums

#### L1 -> Also refer Lecture-1.pdf

1. Find Determinant of 

```
|A| = |1  2  3| = 1  2  3  1  2
      |2  1 -2|   2  1 -2  2  1 
      |1 -4  1|   1 -4  1  1 -4

      [1 + (-4) + (-24)] - [3 + 8 + 4] = -42
```
```
|A| = |cosx  -sinx  0| = cosx  -sinx  0  cosx  -sinx
      |sinx   cosx  0|   sinx   cosx  0  sinx   cosx  
      |0       0    1|    0      0    1    0      0 

    [(cosx.cosx)] - [(-sinx.sinx)]
    = 1

```
```
|A| = |1 -2  3  0|
      |0  1  2  4|
      |-1 2  0  3|
      |0  2 -2  1|


      |1  2  4|    |2 -2 1|
      |2  0  3|  - |-2 3 0|
      |2 -2  1|    |1  2 4|

      [-(20) -(18)] - [-(20) + (21)]
      [-38] - [1] = -39

```

* For 4x4 matrix, we can use elementary operations to simplify the matrix and then find the determinants -> refer silde 14 Lecture-1.pdf

#### Elementary Operations

1. Elementary Row operations
      1. Ri <-> Rj
      2. Ri -> KRi where K is a constant
      3. Ri -> Ri + KRj

2. Elementary Column operations
      1. Ci <-> Cj
      2. Ci -> KCi
      3. Ci -> Ci + KCj

#### Note

1. We are free to apply only 3rd operation while solving determinants
2. If we interchange any 2 rows or columns in a matrix then value of it's determinant changes by -ve sign.
3. If we multiple with constant k in any row or column in a matrix then value of it's determinant changes by K times. We are not free to multiply by any constant in Determinant But, we can take out common factors row wise or column wise.

#### Properties of Determinants

1. If in a matrix all the elements in a row or column are 0 then its determinant = 0
2. If in a matrix any 2 rows or 2 columns are identical then it's determinant will be 0.
3. |ABC| = |A|.|B|.|C|
4. |A<sup>m</sup>| = |A|<sup>m</sup>, where m is a natural number
5. |A<sup>T</sup>| = |A|
6. |A+B+C| = No formula exists, expand manually
7. |A|<sup>-1</sup> = 1/|A|
8. |A<sup>-1</sup>| = 1/|A|
9. |A<sup>T</sup>| -> Interchange of rows and columns of a matrix keeping their order same is called transpose Ri<->Ci
10. |A<sup>-1</sup>| = (Adj A)/|A|
11. |a + l  b  c|   |a b c|   |l b c|
    |d + m  e  f| = |d e f| + |m e f|
    |g + n  h  i|   |g h i|   |n h i|

12. |a + l  b + m  c + n|   |a b c|   |l m n|
    |d        e      f  | = |d e f| + |d e f|
    |g        h      i  |   |g h i|   |g h i|

13. A = |1 -2  3|
        |2  1  4|
        |0 -1  2|

      if |A| = x, then |2A| = 2<sup>3</sup>x
      Because |KA| = K<sup>3</sup>|A|

      * So if A is of size nxn then |KA| = K<sup>n</sup>|A|

14. Max number of terms in the General Expansion of |A|nxn = ?
      ```
      |A|2x2 = |a b| = ad - bc
               |c d|
      Therefore there are 2! terms

      Similarly, in 3x3 there are 3! terms and 4! terms in 4x4 matrix

      Hence You will get n! number of terms in the general expansion of a |A|nxn.
      ```

15. Minimum number of terms in General expansion of |A|<sub>nxn</sub> = 1. The result can be 0 but it is 1 term still. keep in mind
 

#### Area of triangle of points (x1, y1) (x2, y2) (x3, y3)

```
Area = 1/2 |x1  y1  1|
           |x2  y2  1| 
           |x3  y3  1|
```

#### Differential of Determinant

```
d/dx  |a  b  c|    |a` b` c`|   |a  b  c |   |a  b  c |
      |d  e  f| =  |d  e  f | + |d` e` f`| + |d  e  f |
      |g  h  i|    |g  h  i |   |g  h  i |   |g` h` i`|
```

* We can differentiate row wise or column wise
