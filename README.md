# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by

    ![eqn1](./ex4.jpg)

    ![eqn2](./ex6.jpg)

    ![eqn3](./ex3.jpg)

3.	Obtain the Q matrix   
    ![eqn4](./ex1.jpg)
4.	Construct the upper triangular matrix R
    ![eqn5](./ex2.jpg)



## Program:
### Gram-Schmidt Method
```
''' 
Program to QR decomposition using the Gram-Schmidt method
Developed by: Sivasakthi S
RegisterNumber: 25017123
'''
import numpy as np
def QR_Decomposition(A):
    A=np.array(A,dtype=float)
    m,n=A.shape
    Q=np.zeros((m,n))
    R=np.zeros((n,n)) 
    for j in range(n):
        V=A[:,j].copy()
        for i in range(j):
            R[i,j]=np.dot(Q[:,i],A[:,j])
            V=V-R[i,j]*Q[:,i]
        R[j,j]=np.linalg.norm(V)
        Q[:,j]=V/R[j,j]
        for k in range(j+1,n):
            R[j,k]=np.dot(Q[:,j],A[:,k])
    return Q,R
a = np.array(eval(input()))
Q,R=QR_Decomposition(a)
print("The Q Matrix is")
print("",Q)
print("The R Matrix is")
print("",R)






```

## Output
```
<img width="1920" height="1200" alt="Screenshot (110)" src="https://github.com/user-attachments/assets/deca2b57-18c7-459f-82d8-3415cb290d35" />
<img width="1920" height="1200" alt="Screenshot (108)" src="https://github.com/user-attachments/assets/632c3a08-c0be-4fcc-9b47-dea83a6f8202" />
<img width="1920" height="1200" alt="Screenshot (109)" src="https://github.com/user-attachments/assets/70cc08ba-e2cd-46e3-a7fb-cddf1068cc57" />

```

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
