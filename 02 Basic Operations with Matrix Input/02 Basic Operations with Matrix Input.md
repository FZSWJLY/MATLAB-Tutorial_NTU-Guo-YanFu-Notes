## 02基本操作与矩阵输入

### MATLAB Programming Modes

- Command line(in command window)
- Scripts(.m files)

### MATLAB as A Calculator

- Operator: + - * / ^
- Result is computed, and dislayed as ans
- Precedence rules:
  - Left-right within a precedence group
  - Precedence groups are (highest first):
    1. Parenthesis ()
    2. Power (^)
    3. Multiplication and division (*, /)
    4. Addition and subtraction (+, -)

### Exercise

- Calculate:

  - $$
    cos(\sqrt{\frac{(1+2+3+4)^{3}}{5}})
    $$

```matlab
cos(((1 + 2 + 3 + 4) ^ 3 / 5) ^ 0.5)
```

```
ans =

   -0.0050
```

```matlab
help sin
```

```
sin - 参数的正弦，以弧度为单位
    此 MATLAB 函数 返回 X 的元素的正弦。sin 函数按元素处理数组。该函数同时接受实数和复数
    输入。 对于 X 的实数值，sin(X) 返回区间 [-1, 1] 内的实数值。 对于 X 的复数
    值，sin(X) 返回复数值。

    Y = sin(X)

    See also sind, asin, asind, sinh, sinpi

    sin 的文档
    名为 sin 的其他函数
```

- $$
  sin(\sqrt{\pi })+ln(tan(1))
  $$

```matlab
sin(pi ^ 0.5) + log(tan(1))
```

```
ans =

    1.4228
```

- $$
  2^{(3.5×1.7)}
  $$

  

```matlab
sin(pi ^ 0.5) + log(tan(1))
```

```
ans =

   61.8199
```

- $$
  e^{sin(10)}
  $$

  

```matlab
(exp(1)) ^ sin(10)
```

```
ans =

    0.5804
```

- Your best friend - on-line help

### Elementary Math Functions

- Fuction list:

  http://www.mathworks.com/help/matlab/functionlist.html

  - [\[Arithmetic\]](https://ww2.mathworks.cn/help/matlab/arithmetic.html) 

  - [\[Trigonometry\]](http://www.mathworks.com/help/matlab/trigonometry.html)

  - [\[Exponents\]](http://www.mathworks.com/help/matlab/exponents-and-logarithms.html)

  - [\[Complex\]](http://www.mathworks.com/help/matlab/complex-numbers.html)

  - [\[Cartesian\]](http://www.mathworks.com/help/matlab/cartesian-coordinate-system-conversion.html)

### Embedding Functions

- Functions may be embedded into other functions,

  ![在这里插入图片描述](https://img-blog.csdnimg.cn/5511d07be68245ac85eb0ad1dfed3640.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA56iL5bqP5ZGY5bCP5YuH,size_12,color_FFFFFF,t_70,g_se,x_16#pic_center)


- Many lines of code can be condensed into one single command

### Variables

- Variables do <u>NOT</u> need to be declared before assignment

- A single "equal" sign (=) is the assignment operator:

  ![在这里插入图片描述](https://img-blog.csdnimg.cn/74aa2bbae1ac4994a52e24746f141c7c.png#pic_center)


1. Upper case/lower case make difference? Yes.
2. Can variable names can begin with a number?  No.

### Numeric Variable (Data) Type

![在这里插入图片描述](https://img-blog.csdnimg.cn/9803dc212dc343c6b3577643875ef46b.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA56iL5bqP5ZGY5bCP5YuH,size_20,color_FFFFFF,t_70,g_se,x_16#pic_center)


```matlab
who
```

```
您的变量为:

A    A2   ans  
```

```matlab
whos
```

```
  Name      Size            Bytes  Class     Attributes

  A         1x1                 8  double              
  A2        1x1                 8  double              
  ans       1x1                 8  double 
```

### Special Variable and Constants

- ans

- i, j: comlex number

- Inf: ∞

- eps: 2.2204e-016

- NaN: not a number

- pi: $\pi$

- To list keywords:

  ```matlab
  iskeyword
  ```

  ```
  ans =
  
    20×1 cell 数组
  
      {'break'     }
      {'case'      }
      {'catch'     }
      {'classdef'  }
      {'continue'  }
      {'else'      }
      {'elseif'    }
      {'end'       }
      {'for'       }
      {'function'  }
      {'global'    }
      {'if'        }
      {'otherwise' }
      {'parfor'    }
      {'persistent'}
      {'return'    }
      {'spmd'      }
      {'switch'    }
      {'try'       }
      {'while'     }
  ```

- What's the answer from MATLAB after typing?

  ```matlab
  x = 1 / 0
  ```

  ```
  x =
  
     Inf
  ```

  ```matlab
  x = log(0)
  ```

  ```
  x =
  
    -Inf
  ```

  ```matlab
  x = Inf / Inf
  ```

  ```
  x =
  
     NaN
  ```

### MATLAB Calling Priority

![在这里插入图片描述](https://img-blog.csdnimg.cn/6779dd3cf74142a7a403ed8b566b3792.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA56iL5bqP5ZGY5bCP5YuH,size_9,color_FFFFFF,t_70,g_se,x_16#pic_center)


```matlab
cos = 'This string.';
cos(8)
```

```
ans =

    'r'
```

```matlab
clear cos
```

### Numeric Display "Format"

```matlab
format long
pi
```

```
ans =

   3.141592653589793
```

![在这里插入图片描述](https://img-blog.csdnimg.cn/0f59b5fad9d743ddb3ff7c0a49d0cd47.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA56iL5bqP5ZGY5bCP5YuH,size_20,color_FFFFFF,t_70,g_se,x_16#pic_center)


```matlab
format longE
pi
```

```
ans =

     3.141592653589793e+00
```

```matlab
format rat
>> 3 / 13
```

```
ans =

       3/13  
```

### Exercise

- Calculate
  $$
  \frac{3}{13}+\frac{4}{14}+\frac{5}{15}
  $$

![在这里插入图片描述](https://img-blog.csdnimg.cn/ded2aadde6ef48948669fecf986ecfa4.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA56iL5bqP5ZGY5bCP5YuH,size_20,color_FFFFFF,t_70,g_se,x_16#pic_center)


```matlab
format rat
3 /13 + 4 / 14 + 5 / 15
```

```
ans =

     232/273   
```

```matlab
format long
3 /13 + 4 / 14 + 5 / 15
```

```
ans =

   0.849816849816850
```

### Command Line Terminal

- Observe the difference between

  ```matlab
  a = 10
  a = 10;
  ```

- ; at the end of a command suppresses output to the terminal

- ↑ display previous commands

### Some Functions

- clc: clear <u>command window</u> display
- clear: remove all variables in the <u>workspace</u>
- who: variables in the <u>workspace</u>
- whos: variables information in the <u>workspace</u>

### Array (Vector and Mrtrix)

- Row vector:

  ```matlab
  a = [1, 2, 3, 4]
  ```

- Column vector:

  ```matlab
  b = [1; 2; 3; 4]
  ```

- Try:

  ```matlab
  a * b
  b * a
  ```

- Key in the following matrix in MATLAB
  $$
  A = \begin{bmatrix}
  1 & 21 & 6\\ 
  5 & 17 &9 \\ 
  31 & 2 & 7
  \end{bmatrix}
  $$

```matlab
A = [1, 21, 6; 5, 17, 9; 31, 2, 7]
```

### Array Indexing

- Select a certain subset of elements inside a matrix
  $$
  A = \begin{bmatrix}
  1 & 21 & 6\\ 
  5 & 17 &9 \\ 
  31 & 2 & 7
  \end{bmatrix}
  $$

- What's the answer from MATLAB after typing?

  ```matlab
  A(8)
  A([1 3 5])
  
  A([1, 3]; [1, 3])
  
  A(3, 2)
  
  A([1, 3], [1, 3])
  ```

  ```
  9
  1 31 17
  
  1 31
  1 31
  
  2
  
   1 6
  31 7
  ```

### Replacing Entries

- Change the following elements in the matrix

![在这里插入图片描述](https://img-blog.csdnimg.cn/20556279932449bd8ea4eefadc41801f.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA56iL5bqP5ZGY5bCP5YuH,size_20,color_FFFFFF,t_70,g_se,x_16#pic_center)


```matlab
A = [1, 21, 6; 5, 17, 9; 31, 2, 7]

A(1, 2) = 76
A(3, 2) = 0

A(1, 2) = 0
A(1, 3) = 0
A(2, 2) = 0
A(2, 3) = 0

A(3, : ) = []
```

- The expression

  A () = []

  delete row or columns of A

### Colon Operator

- Want to create a long array: A = [1 2 3 ... 100]
- Create vectors or arrays, and specify for iterations
- Syntax: ![在这里插入图片描述](https://img-blog.csdnimg.cn/d97be032d350485e9e96f7ae385a72b0.png#pic_center)


- What's the answer from MATLAB after typing?

  ```matlab
  B = 1: 5
  B = 1: 2: 5
  B = [1: 5; 2: 3: 15; -2: 0.5: 0]
  str = 'a': 2: 'z'
  ```

  ```
  B =
  
       1     2     3     4     5
  B =
  
       1     3     5     
  B =
  
      1.0000    2.0000    3.0000    4.0000    5.0000
      2.0000    5.0000    8.0000   11.0000   14.0000
     -2.0000   -1.5000   -1.0000   -0.5000         0
  str =
  
      'acegikmoqsuwy'
  ```

### Array Concatenation

- Arrays can be formed through concatenation as long as the rectangular shape is preserved

  ![在这里插入图片描述](https://img-blog.csdnimg.cn/1f4a4fe152324f4483b0a80df681b224.png#pic_center)


- Create matrices A, B, C, AND D and concatenate them into F:

  ![在这里插入图片描述](https://img-blog.csdnimg.cn/44145bd4d63d4bf4974efffe0a3b9913.png#pic_center)


### Array Manipulation

![在这里插入图片描述](https://img-blog.csdnimg.cn/9fd69bba092a4c5eba6e5c261e19efc9.png#pic_center)


- Operation on array: + - * / ^ · '

- Type the following command and observe the results:

  ```matlab
  x1 = A + a
  y1 = A + B
  x2 = A / a
  y2 = A * B
  x3 = A ./ a
  y3 = A .* B
  x4 = A ^ a
  y4 = A / B
  x5 = A .^ a
  y5 = A ./ B
  C = A'
  ```

  ```
  x1 =
  
       3     4     5
       6     7     6
      11    10     9
  y1 =
  
       4     5     6
       6     9    13
      10    11     8
  x2 =
  
      0.5000    1.0000    1.5000
      2.0000    2.5000    2.0000
      4.5000    4.0000    3.5000
  y2 =
  
      10    20    24
      26    44    61
      50    80   106
  x3 =
  
      0.5000    1.0000    1.5000
      2.0000    2.5000    2.0000
      4.5000    4.0000    3.5000
  y3 =
  
       3     6     9
       8    20    36
       9    24     7
  x4 =
  
      36    36    32
      60    65    60
     104   114   108
  y4 =
  
      0.0714    0.2857    0.2143
      1.1667         0    0.5000
      3.2619   -0.2857   -0.2143
  x5 =
  
       1     4     9
      16    25    16
      81    64    49
  y5 =
  
      0.3333    0.6667    1.0000
      2.0000    1.2500    0.4444
      9.0000    2.6667    7.0000
  C =
  
       1     4     9
       2     5     8
       3     4     7
  ```

![在这里插入图片描述](https://img-blog.csdnimg.cn/000db4304fda49e0bc9f14b1caf92dee.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA56iL5bqP5ZGY5bCP5YuH,size_20,color_FFFFFF,t_70,g_se,x_16#pic_center)


### Some Special Matrix

- linspace () : linearly spaced vectors

- eye (n) : n×n identity matrix

- zeros (n1, n2) : n1×n2 zero matrix

- ones (n1, n2) : n1×n2 matrix with every entry as 1

- diag() : diagonal matrix

- rand () : uniformly distributed random numbers

- Typing the following command and observe the results:

  ```matlab
  linspace(0, 13, 6)
  ```

  ```
  ans =
  
           0    2.6000    5.2000    7.8000   10.4000   13.0000
  ```

### Some Matrix Related Functions

$$
A=\begin{bmatrix}
1 & 2 &3 \\ 
0 & 5 &6 \\ 
7 & 0 & 9
\end{bmatrix}
$$

- Typing the following command and observe the results:

  ```
  A = [1, 2, 3; 0, 5, 6; 7, 0, 9]
  max(A)
  max(max(A))
  min(A)
  sum(A)
  mean(A)
  sort(A)
  sortrows(A)
  size(A)
  length(A)
  find(A)
  ```

  ```
  A =
  
       1     2     3
       0     5     6
       7     0     9
  ans =
  
       7     5     9
  ans =
  
       9
  ans =
  
       0     0     3
  ans =
  
       8     7    18
  ans =
  
      2.6667    2.3333    6.0000
  ans =
  
       0     0     3
       1     2     6
       7     5     9
  ans =
  
       0     5     6
       1     2     3
       7     0     9
  ans =
  
       3     3
  ans =
  
       3
  ans =
  
       1
       3
       4
       5
       7
       8
       9
  ```


