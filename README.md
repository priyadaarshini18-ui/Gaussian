# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Import the required libraries such as NumPy.
2. Create the coefficient matrix and constant matrix using NumPy arrays.
3. Apply Gaussian Elimination to convert the matrix into row echelon form and solve the equations.
4. Display the solution of the system of equations.

## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by:v.priyadaarshin 
RegisterNumber: 212225040317
'''
import os
os.environ["OPENBLAS_NUM_THREADS"]="1"
import numpy as np
n=int(input())
a=[]
for i in range(n):
    row=[]
    for j in range(n+1):
        row.append(float(input()))
    a.append(row)
for i in range(n):
    for k in range(i+1,n):
        factor=a[k][i]/a[i][i]
        for j in range(i,n+1):
            a[k][j]-=factor*a[i][j]
x=[0]*n
for i in range(n-1,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]-=a[i][j]*x[j]
    x[i]/=a[i][i]
for i in range(n):
    print(f"X{i} = {x[i]:.2f}",end = " ")
```

## Output:
![gaussian elimination]()
![alt text](<Screenshot 2026-05-24 193620.png>)

## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

