# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Start the program and read the order of the matrix.
2. Read the elements of the augmented matrix.
3. Apply Gaussian Elimination to convert the matrix into upper triangular form.
4. Find the solution using back substitution and display the result.

## Program:
```
/*
Program to find the solution of a matrix using Gaussian Elimination.
Developed by: Kishor.M
RegisterNumber: 26018383
*/
```
import os

os.environ["OPENBLAS_NUM_THREADS"] = "1"

import sys


data=list(map(float, sys.stdin.read().split()))


n=int(data[0])

a=[]
idx=1

for i in range(n):
    row=[]
    for j in range(n + 1):
        row.append(data[idx])
        idx += 1
    a.append(row)
    
for i in range(n):
    for j in range(i + 1, n):
        factor = a[j][i] / a[i][i]
        
        for k in range(i, n + 1):
            a[j][k] -= factor * a[i][k]
            
x = [0.0] * n

for i in range(n - 1, -1, -1):
    s = 0.0
    
    for j in range(i + 1, n):
        s += a[i][j] * x[j]
        
    x[i] = (a[i][n] - s) / a[i][i]
    
for i in range(n):
    print(f"X{i} = {x[i]:.2f}", end=" ")

## Output:
<img width="1920" height="1080" alt="Screenshot (26)" src="https://github.com/user-attachments/assets/1a84a1ea-4635-46d1-9bd8-94e2ac0bb184" />
<img width="1920" height="1080" alt="Screenshot (27)" src="https://github.com/user-attachments/assets/b96fe2fe-7180-4061-a00b-f396acae6edc" />
<img width="1920" height="1080" alt="Screenshot (28)" src="https://github.com/user-attachments/assets/8f09db0b-c0be-4701-b9ac-4b900eb6f846" />



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

