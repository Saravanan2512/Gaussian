# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
1. Accept the number of equations n.
2. Use nested loops to input the coefficients and constants for each equation into the matrix a.
3. Ensure that the pivot element is not zero to avoid division by zero.
4. Continue substituting and solving for each variable until all variables are determined.

## Program:
```
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: SARAVANAN G
RegisterNumber: 23005445
'''
import numpy as np
import sys
n=int(input())
a=np.zeros((n,n+1))
x=np.zeros(n)
for i in range(n):
    for j in range(n+1):
        a[i][j]=float(input())
        
for i in range(n):
    if a[i][i]==0.0:
        sys.exit("divide by zero detected!")
    for j in range (i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-1,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print('X%d = %0.2f' %(i,x[i]),end=' ')
```

## Output:
![image](https://github.com/Saravanan2512/Gaussian/assets/144979117/9c3754a8-318e-42e8-abdc-ac61e7e34e31)



## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

