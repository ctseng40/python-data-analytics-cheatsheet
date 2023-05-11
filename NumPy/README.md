# NumPy Cheat Sheet
[NumPy](http://www.numpy.org) is a library for the Python programming language, adding support for large, multi-dimensional arrays and matrices, along with a large collection of high-level mathematical functions to operate on these arrays.

## Table of Contents
1. [Installation](#introduction)
2. [Prerequisites](#prerequisites)
3. [Dataset](#dataset)
4. [Model Training](#modeltraining)
5. [Model Profiling and Debugging](#model-profiling-and-debugging)
6. [Model Deployment](#model-deployment)
7. [Inference](#inference)
8. [Conclusion and Future Works](#conclusion)

## Installation
Detailed installation guide can be found [here](https://numpy.org/install/).

**CONDA**
If you use conda, you can install NumPy from the defaults or conda-forge channels:
```
# Best practice, use an environment rather than install in the base env
$ conda create -n my-env
$ conda activate my-env

# If you want to install from conda-forge
$ conda config --env --add channels conda-forge

# The actual install command
$ conda install numpy
```
**PIP**
If you use pip, you can install NumPy with:
```
$ pip install numpy
```


