# BELGICA-LAWRENCE-NATHAN-DC.--PA_2  

# Programming Assignment (PA#2)  

This repository contains my submission for **Programming Assignment #2** in  
**ECE 2112: Advanced Computer Programming and Algorithms**.  

The purpose of this assignment is to practice **NumPy** operations in Python, particularly focusing on data preprocessing and array manipulation. This README explains the problems solved, the step-by-step logic, and how to run the programs.  

---

## 1. Normalization Problem  
### Goal
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
```
→ imports the NumPy library, which provides tools for array operations.

```python
X = np.random.rand(5, 5)
```
→ Generates a 5×5 matrix filled with random numbers between 0 and 1.

```python
mean_X = X.mean()
std_X = X.std()
```
→ Calculates the mean and standard deviation of the matrix. These values are used for normalization.

``` python
X_normalized = (X - mean_X) / std_X
```
→ Applies the normalization formula to transform the data into a standardized scale (mean = 0, std = 1).

```python
np.save("X_normalized.npy", X_normalized)
```
→ Saves the normalized array into a `.npy` file called **X_normalized.npy** for later use.

```python
print("Original Array:\n", X)
print("\nMean of X:", mean_X)
print("Standard Deviation of X:", std_X)
print("\nNormalized Array:\n", X_normalized)
print("\nNormalized array saved as 'X_normalized.npy'")
```
→ Prints the original matrix, its mean, standard deviation, and the normalized result.

### Example Output (Sample)

```python
Original Array:
 [[0.57 0.88 0.63 0.32 0.91]
  [0.10 0.22 0.78 0.45 0.66]
  [0.89 0.12 0.47 0.33 0.55]
  [0.60 0.36 0.29 0.72 0.14]
  [0.83 0.48 0.31 0.99 0.20]]

Mean of X: 0.512
Standard Deviation of X: 0.252

Normalized Array:
 [[ 0.23  1.46  0.48 -0.76  1.58]
  [-1.64 -1.17  1.06 -0.25  0.59]
  [ 1.49 -1.56 -0.17 -0.72  0.15]
  [ 0.35 -0.61 -0.88  0.83 -1.46]
  [ 1.27 -0.13 -0.80  1.89 -1.24]]

Normalized array saved as 'X_normalized.npy'
```

## 2. Divisible by 3 Problem

### Goal
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
```
→ Import NumPy for array creation and manipulation.

```python
numbers = np.arange(1, 101)
```
→ Creates a NumPy array with integers from 1 to 100.

```python
squares = numbers ** 2
```
→ Squares each element of the array.

```python
A = squares.reshape(10, 10)
print("Matrix A (10x10 with squares):\n")
print(A)
```
→ Reshapes the squared numbers into a 10×10 matrix and prints it.

```python
div3 = A[A % 3 == 0]
print("\nNumbers divisible by 3:\n")
print(div3)
```
→ Uses Boolean indexing to extract all numbers divisible by 3.

```python
np.save("div_by_3.npy", div3)
print("\nOutput saved as 'div_by_3.npy'")
```
→ Saves the filtered result into **div_by_3.npy** for later use.


### Example Output (Sample)
```python
Matrix A (10x10 with squares):
 [[    1     4     9    16    25    36    49    64    81   100]
  [  121   144   169   196   225   256   289   324   361   400]
  ...
  [ 8281  8464  8649  8836  9025  9216  9409  9604  9801 10000]]

Numbers divisible by 3:
 [   9   36   81  144  225  324  441  576  729  900 ... 9801]

Output saved as 'div_by_3.npy'
```

## How to Run the Programs

1. Clone this repository or download the Python files.
2. Run each program in a terminal or Jupyter Notebook using:

```python
python filename.py
```
(Replace filename.py with the actual file name.)

3. After running, check your folder for the output files:
- **X_normalized.npy**
- **div_by_3.npy**
