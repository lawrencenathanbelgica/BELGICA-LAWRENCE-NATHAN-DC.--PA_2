# BELGICA-LAWRENCE-NATHAN-DC.--PA_2  

# Programming Assignment (PA#2)  

This repository contains my submission for **Programming Assignment #2** in  
**ECE 2112: Advanced Computer Programming and Algorithms**.  

The purpose of this assignment is to practice **NumPy** operations in Python, particularly focusing on data preprocessing and array manipulation. This README explains the problems solved, the step-by-step logic, and how to run the programs.  

---

## 1. Normalization Problem  

Perform normalization on a randomly generated 5x5 matrix by centering and scaling the data.  

**Process:**  
1. Generate a 5x5 matrix `X` of random values between 0 and 1 using `np.random.rand()`.  
2. Compute the mean (`mean_X`) and standard deviation (`std_X`) of the matrix.  
3. Normalize the array using the formula:  

Z = (X - mean(X)) / std(X)

4. Save the normalized array into a `.npy` file for later use.  

**Code Snippet:**  
```python
import numpy as np

X = np.random.rand(5, 5)
mean_X = X.mean()
std_X = X.std()

X_normalized = (X - mean_X) / std_X
np.save("X_normalized.npy", X_normalized)

print("Original Array:\n", X)
print("\nMean of X:", mean_X)
print("Standard Deviation of X:", std_X)
print("\nNormalized Array:\n", X_normalized)
print("\nNormalized array saved as 'X_normalized.npy'")

```

## 2. Divisible by 3 Problem
 
Generate the squares of the first 100 integers in a 10×10 matrix, then extract all elements divisible by 3.

**Process:**
1. Generate numbers from `1` to `100` using `np.arange(1, 101)`.
2. Compute their squares using `numbers ** 2`.
3. Reshape into a 10×10 matrix with `.reshape(10, 10)`.
4. Filter elements divisible by `3` using `A[A % 3 == 0]`.
5. Save the result into `div_by_3.npy` using `np.save()`.

**Code Snippet:**
```python
import numpy as np

numbers = np.arange(1, 101)
squares = numbers ** 2
A = squares.reshape(10, 10)
print("Matrix A (10x10 with squares):\n")
print(A)

div3 = A[A % 3 == 0]
print("\nNumbers divisible by 3:\n")
print(div3)

np.save("div_by_3.npy", div3)
print("\nOutput saved as 'div_by_3.npy'")

```

Last step is to check the **.npy** output files (`X_normalized.npy`, `div_by_3.npy`) in the project folder.
