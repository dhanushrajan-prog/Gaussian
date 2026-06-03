# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
Step 1:

Import the required NumPy library.

Step 2:

Read or define the coefficient matrix and constant matrix using np.array().

Step 3:

Apply Gaussian Elimination to convert the matrix into row-echelon form and solve for the unknown variables.

Step 4:

Display the solution of the matrix as output.
#program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: DHANUSH RAJAN.T
RegisterNumber: 212225230052
'''
import os
os.environ["OPENBLAS_NUM_THREADS"] = "1"
import numpy as np
n = int(input())
a = np.zeros((n, n + 1))
for i in range(n):
    for j in range(n + 1):
        a[i][j] = float(input())
for i in range(n):
    for j in range(i + 1, n):
        ratio = a[j][i] / a[i][i]
        for k in range(n + 1):
            a[j][k] = a[j][k] - ratio * a[i][k]
x = np.zeros(n)
x[n - 1] = a[n - 1][n] / a[n - 1][n - 1]
for i in range(n - 2, -1, -1):
    s = 0
    for j in range(i + 1, n):
        s = s + a[i][j] * x[j]
    x[i] = (a[i][n] - s) / a[i][i]
for i in range(n):
    print(f"X{i} = {x[i]:.2f}", end=" ")



```
## Output:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/5d151312-5c10-494e-8b8e-53c4f1088ba9" />

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.
