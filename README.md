# Algorithm for QR Decomposition
## Aim:
To implement QR decomposition algorithm using the Gram-Schmidt method.
## Equipment’s required:
1.	Hardware – PCs
2.	Anaconda – Python 3.7 Installation / Moodle-Code Runner
## Algorithm:
1.	Intialize the matrix Q and u
2.	The vector u and e is given by
   ![image](https://github.com/Swetha733N/QRdecomposition/assets/122199934/d66bd1d4-1132-4711-a4b4-9a5eaaf97292)

3.	Obtain the Q matrix 
   ![image](https://github.com/Swetha733N/QRdecomposition/assets/122199934/94be1c0b-402e-41f0-9ff2-b45e22e5d1ef)

4.	Construct the upper triangular matrix R
   ![image](https://github.com/Swetha733N/QRdecomposition/assets/122199934/410d364c-8a4e-4625-b220-f35a6676ca58)


## Program:
### Gram-Schmidt Method
```
Program to QR decomposition using the Gram-Schmidt method
Developed by:SWETHA N
RegisterNumber: 212222110050

import numpy as np
def QR_Decomposition(A):
    n,m=A.shape
    Q=np.empty((n,n))
    u=np.empty((n,n))
    
    u[:,0]=A[:,0]
    Q[:,0]=u[:,0]/np.linalg.norm(u[:,0])
    
    for i in range(1,n):
        u[:,i]=A[:,i]
        for j in range(i):
            u[:,i]-=(A[:,i] @ Q[:,j])*Q[:,j]
        Q[:,i]=u[:,i]/np.linalg.norm(u[:,i])
    R=np.zeros((n,m))
    for i in range(n):
        for j in range(i,m):
            R[i,j]=A[:,j] @ Q[:,i]
    print(Q)
    print(R)
a =  np.array(eval(input()))
QR_Decomposition(a)        
            
```

## Output:
![image](https://github.com/Swetha733N/QRdecomposition/assets/122199934/1af7f357-d538-4574-a588-a3c01d2c6b0e)

## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
