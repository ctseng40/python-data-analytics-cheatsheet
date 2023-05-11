# NumPy Cheat Sheet
[NumPy](http://www.numpy.org) is a library for the Python programming language, adding support for large, multi-dimensional arrays and matrices, along with a large collection of high-level mathematical functions to operate on these arrays.

## Table of Contents
1. [Installation](#introduction)
2. [Importing NumPy](#importing-numpy)
3. [Creating Arrays](#creating-arrays)

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
```
>>> [1 2 3]
```
# 2D Array
b = np.array([(1, 2, 3), (4, 5, 6)]) 
>>> [[1 2 3]
     [4 5 6]]
     
# Create an array of zeros
zeros = np.zeros((3, 4))
>>> [[0. 0. 0. 0.]
     [0. 0. 0. 0.]
     [0. 0. 0. 0.]]

# Create an array of ones
ones = np.ones((3, 4))
>>> [[1. 1. 1. 1.]
     [1. 1. 1. 1.]
     [1. 1. 1. 1.]]

# Create an array of evenly spaced values (step value)
c = np.arange(0, 30, 5)
>>> [ 0  5 10 15 20 25]

# Create an array of evenly spaced values (number of samples)
d = np.linspace(0, 1, 12)
>>> [0.         0.09090909 0.18181818 0.27272727 0.36363636 0.45454545
 0.54545455 0.63636364 0.72727273 0.81818182 0.90909091 1.        ]

# Create a constant array
e = np.full((2, 2), 7)
>>> [[7 7]
     [7 7]]

# Create a 2x2 identity matrix
f = np.eye(2)
>>> [[1. 0.]
     [0. 1.]]

# Create an array with random values (Return random floats in the half-open interval [0.0, 1.0))
g = np.random.random((2, 2)) 
>>> [[0.79147008 0.658632  ]
     [0.63582353 0.14000391]]
```



