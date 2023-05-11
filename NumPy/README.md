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

```
# 1D Array
a = np.array([1, 2, 3]) 
>>> [1 2 3]

# 2D Array
b = np.array([(1, 2, 3), (4, 5, 6)]) 
>>> [[1 2 3]
     [4 5 6]]
     
# Create an array of zeros
zeros = np.zeros((3, 4)) 

# Create an array of ones
ones = np.ones((3, 4)) 

# Create an array of evenly spaced values (step value)
c = np.arange(0, 30, 5) 

# Create an array of evenly spaced values (number of samples)
d = np.linspace(0, 1, 12) 

# Create a constant array
e = np.full((2, 2), 7) 

# Create a 2x2 identity matrix
f = np.eye(2) 

# Create an array with random values
g = np.random.random((2, 2)) 
```



