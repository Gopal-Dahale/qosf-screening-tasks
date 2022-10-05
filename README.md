# QOSF screening tasks cohort 6

This repository contains the solution for QOSF screening task 2: Missing Number.

## Problem Statement

From a function that has as a parameter a vector of positive integers of size $2^n -1$, which is missing a number, this vector can be disordered, to search for the missing number from a quantum circuit.

Return the positive integer value that is missing in the input.

Example:

```
A =  missing_number([2,0,1])
print(A)
3
```

### Bonus: 

Which is the largest list that can be implemented? Identify it and describe the result.

## Solution

The idea is to use [Grover's algorithm](https://en.wikipedia.org/wiki/Grover%27s_algorithm) to find the missing number. We use [Qiskit](https://qiskit.org/) to solve this problem. Grover's algorithm has a time complexity of $O(\sqrt{N})$ where $N$ is the size of the function domain (in our case it's the size of the input vector).

## Developing on the bonus part

We try to simulate for various values of $n$. We know that at some point the system will crash due to high memory usage. We give a theoritical upper bound for it in the notebook. The largest list that worked for us is for $n=11$ i.e. the size of list is $2^{12}-1$.

## Structure of repository

### missing_number.py
This file contains the code for generating Grover's oracle, diffuser and performing Grover's search on the input vector.

The function `missing_number` takes and `input_vector` as argument and returns a `tuple` which contains the missing number, the counts of the experiment and the quantum circuit.

### Task_2_Missing_Number.ipynb
This notebook describes how to use `missing_number.py` and showcase the results. Also, it simulates the bonus part.
