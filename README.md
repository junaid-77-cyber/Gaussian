# Gaussian Elimination

## AIM:
To write a program to find the solution of a matrix using Gaussian Elimination.

## Equipments Required:
1. Hardware – PCs
2. Anaconda – Python 3.7 Installation / Moodle-Code Runner

## Algorithm
# Step 1: 
Start
# Step 2:
Input the number of equations n.
# Step 3: 
Initialize an augmented matrix a[n][n+1] and solution vector x[n].
# Step 4: 
Read the augmented matrix from the user.
# Step 5:
Perform Forward Elimination to convert the system
into upper triangular form:

For each row i = 0 to n-1

If pivot element a[i][i] = 0, stop the program (division by zero).

For each row j = i+1 to n-1

Compute ratio = a[j][i] / a[i][i].

For each column k = 0 to n

Update element: a[j][k] = a[j][k] - ratio * a[i][k].

# Step 6: 
Perform Back Substitution to calculate solution values:

Set x[n-1] = a[n-1][n] / a[n-1][n-1].

For i = n-2 down to 0:

Set x[i] = a[i][n].

For j = i+1 to n-1:

Update x[i] = x[i] - a[i][j] * x[j].

Divide by pivot: x[i] = x[i] / a[i][i].

# Step 7: 
Print all solutions x1, x2, …, xn.
# Step 8:
Stop.

## Program:
```
/*
'''Program to solve a matrix using Gaussian elimination without partial pivoting.
Developed by: Junaid Sardar S
RegisterNumber: 212224100028
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
    if a[i][j]==0.0:
        sys.exit("Divide by zero detected!")
    for j in range(i+1,n):
        ratio=a[j][i]/a[i][i]
        for k in range(n+1):
            a[j][k]=a[j][k]-ratio*a[i][k]
x[n-1]=a[n-1][n]/a[n-1][n-1]
for i in range(n-2,-1,-1):
    x[i]=a[i][n]
    for j in range(i+1,n):
        x[i]=x[i]-a[i][j]*x[j]
    x[i]=x[i]/a[i][i]
for i in range(n):
    print("X%d = %0.2f" %(i,x[i]),end=" ")
*/
```

## Output:
![alt text](<Screenshot 2025-09-22 093049.png>)


## Result:
Thus the program to find the solution of a matrix using Gaussian Elimination is written and verified using python programming.

