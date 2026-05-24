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
|1 -2 3|    1  -2   3   1  -2
|4  2 0| =  4   2   0   4   2
|1 2 -1|    1   2  -1   1   2

    Top to bottom Diagonally             Bottom to top Diagonally
[(1*2*-1) + (-2*0*1) + (3*4*2)] - [(1*2*3) + (2*0*1) + (-1*4*-2)]

= 22 -14 = 8
```
* Method of solving 4 x 4 Determinant (refer 4x4_det.png)
    * therefore sign applied will be sign a<sub>ij</sub> = (-1)<sup>i+j</sup>
    * Follow same as 3 x 3 matrix

### Class Sums

#### L1 -> Also refer notebook

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

