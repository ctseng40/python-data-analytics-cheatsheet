# NumPy Cheat Sheet
[NumPy](http://www.numpy.org) is a library for the Python programming language, adding support for large, multi-dimensional arrays and matrices, along with a large collection of high-level mathematical functions to operate on these arrays.

## Table of Contents
1. [Installation](#introduction)
2. [Importing NumPy](#importing-numpy)
3. [Creating Arrays](#creating-arrays)
4. [Inspecting Your Array](#Inspecting-Your-Array)
5. [Array Mathematics](#Array-Mathematics)
6. [Array Manipulation](#Array-Manipulation)
7. [Aggregate Functions](#Aggregate-Functions)
8. [Copying Arrays](#Copying-Arrays)
9. [Subsetting, Slicing, Indexing](#Subsetting-Slicing-Indexing)

## Installation

Detailed installation guide can be found [here](https://numpy.org/install/).

**CONDA**

If you use conda, you can install NumPy from the defaults or conda-forge channels:
```
# Best practice, use an environment rather than install in the base env
conda create -n my-env
conda activate my-env

# If you want to install from conda-forge
conda config --env --add channels conda-forge

# The actual install command
conda install numpy
```

**PIP**

If you use pip, you can install NumPy with:
```
pip install numpy
```

## Importing NumPy
```
import numpy as np
```

## Creating Arrays

1D Array
```
a = np.array([1, 2, 3]) 
>>> [1 2 3]
```

2D Array
```
b = np.array([(1, 2, 3), (4, 5, 6)])
>>> [[1 2 3]
     [4 5 6]]
``` 
     
Create an array of zeros
```
zeros = np.zeros((3, 4))
>>> [[0. 0. 0. 0.]
     [0. 0. 0. 0.]
     [0. 0. 0. 0.]]
```

Create an array of ones
```
ones = np.ones((3, 4))
>>> [[1. 1. 1. 1.]
     [1. 1. 1. 1.]
     [1. 1. 1. 1.]]
```

Create an array of evenly spaced values (step value)
```
c = np.arange(0, 30, 5)
>>> [ 0  5 10 15 20 25]
```

Create an array of evenly spaced values (number of samples)
```
d = np.linspace(0, 1, 12)
>>> [0.         0.09090909 0.18181818 0.27272727 0.36363636 0.45454545
 0.54545455 0.63636364 0.72727273 0.81818182 0.90909091 1.        ]
```

Create a constant array
```
e = np.full((2, 2), 7)
>>> [[7 7]
     [7 7]]
```

Create a 2x2 identity matrix
```
f = np.eye(2)
>>> [[1. 0.]
     [0. 1.]]
```

Create an array with random values (Return random floats in the half-open interval `[0.0, 1.0)`)
```
g = np.random.random((2, 2)) 
>>> [[0.79147008 0.658632  ]
     [0.63582353 0.14000391]]
```

## Inspecting Your Array

Array dimensions
```
array_2d = np.array([(1, 2, 3), (4, 5, 6)])
array_2d.shape
>>> (2, 3)
```

Length of array
```
len(array_2d)
>>> 2
```

Number of array dimensions
```
array_2d.ndim
>>> 2

array_3d = np.array([[[1, 2, 3], [4, 5, 6]], [[7, 8, 9], [10, 11, 12]]])
>>> [[[ 1  2  3]
      [ 4  5  6]]

     [[ 7  8  9]
      [10 11 12]]]

array_3d.ndim
>>> 3
```

Number of array elements
```
array_2d.size
>>> 6
```

Data type of array elements
```
array_2d.dtype
>>> dtype('int64')
```

Convert an array to a different type
```
array_2d.astype(int)
>>> array([[1, 2, 3],
           [4, 5, 6]])
```

## Array Mathematics

Subtraction
```
a = np.array([(2, 3, 4), (4, 6, 8)])
b = np.array([(4, 6, 8), (8, 12, 16)])
g = a - b
>>> [[-2 -3 -4]
     [-4 -6 -8]]
```

Addition
```
np.add(a, b)
>>> array([[ 6,  9, 12],
           [12, 18, 24]])
```

Division
```
np.divide(a, b)
>>> array([[0.5, 0.5, 0.5],
           [0.5, 0.5, 0.5]])
```

Multiplication
```
np.multiply(a, b)
>>> array([[  8,  18,  32],
           [ 32,  72, 128]])
```

Exponentiation
```
np.exp(b) 
>>> array([[5.45981500e+01, 4.03428793e+02, 2.98095799e+03],
           [2.98095799e+03, 1.62754791e+05, 8.88611052e+06]])
```
           
Square root
```
np.sqrt(b) 
>>> array([[2.        , 2.44948974, 2.82842712],
           [2.82842712, 3.46410162, 4.        ]])
```

Print sines of an array
```
np.sin(a)
>>> array([[ 0.90929743,  0.14112001, -0.7568025 ],
           [-0.7568025 , -0.2794155 ,  0.98935825]])
```

Element-wise cosine
```
np.cos(b)
>>> array([[-0.65364362,  0.96017029, -0.14550003],
           [-0.14550003,  0.84385396, -0.95765948]])
```

Element-wise natural logarithm
```
np.log(a)
>>> array([[0.69314718, 1.09861229, 1.38629436],
           [1.38629436, 1.79175947, 2.07944154]])
```

## Array Manipulation

Transposing array
```
a = np.array([(2, 3, 4), (4, 6, 8)])
i = a.T
>>> [[2 4]
     [3 6]
     [4 8]]
```

Changing array shape
```
a.ravel()
>>> array([2, 3, 4, 4, 6, 8])
```

Reshape, but don’t change data
```
a.reshape(3, -2)
>>>array([[2, 3],
          [4, 4],
          [6, 8]])
```

Adding/removing Elements
```
h.resize((2, 6))
>>> [[2 3 4 4 6 8]
     [0 0 0 0 0 0]]

```

Insert items in an array
```
a = np.array([(2, 3, 4), (4, 6, 8)])
b = np.array([(4, 6, 8), (8, 12, 16)])
np.append(a, b)
>>> array([ 2,  3,  4,  4,  6,  8,  4,  6,  8,  8, 12, 16])
```

Reverse an array
```
a[::-1]
>>> array([[4, 6, 8],
           [2, 3, 4]])

b = np.array([[2, 3, 4, 5, 6]])
b[::-1]
>>> array([(2, 3, 4, 5, 6)])

b = np.array([2, 3, 4, 5, 6])
b[::-1]
>>> array([6, 5, 4, 3, 2])
```

## Aggregate Functions
Array-wise sum
```
a = np.array([(2, 3, 4), (4, 6, 8)])
a.sum()
>>> 27
```

Array-wise minimum value
```
a.min()
>>> 2
```

Maximum value of an array row
```
a.max(axis=0)
>>> array([4, 6, 8])
```

Cumulative sum of the elements
```
a.cumsum(axis=1)
>>> array([[ 4, 10, 18],
           [ 8, 20, 36]])
```

Mean
```
a.mean()
>>> 4.5

```

Median
```
np.median(a)
>>> 4.0
```

Correlation coefficient
```
np.corrcoef(a)
>>> array([[1., 1.],
           [1., 1.]])

```

Standard deviation
```
np.std(a)
>>> 1.9790570145063195
```

## Copying Arrays
Create a view of the array with the same data
```
a = np.array([(2, 3, 4), (4, 6, 8)])
h = a.view()
>>> [[2 3 4]
     [4 6 8]]
```

Create a copy of the array
```
np.copy(a)
```

Create a deep copy of the array
```
h = a.copy()
```

## Subsetting, Slicing, Indexing
Select the element at the 1st index
```
a = np.array([(2, 3, 4), (4, 6, 8)])
a[1]
>>> array([4, 6, 8])
```

Select the element at row 0 column 1
```
a[0, 1]
>>> 3
```

Select items at index 0 and 1
```
a[0:2]
>>> array([[2, 3, 4],
           [4, 6, 8]])
```

Select items at rows 0 and 1 in column 1
```
a[0:2, 1]
>> array([3, 6])
```

Select all items at row 0
```
a[:1]
>>> array([[2, 3, 4]])
```

Same as [1,2,3]
```
a < 2
>>> array([[False, False, False],
           [False, False, False]])

a[a<2]
array([], dtype=int64)

a < 6
>>> array([[ True,  True,  True],
           [ True, False, False]])

a[a<6]
>>> array([2, 3, 4, 4])
```
