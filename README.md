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

import numpy as np

# Input Matrix
A = np.array([[1, 1, 0],
              [1, 0, 1],
              [0, 1, 1]], dtype=float)

n = A.shape[1]

Q = np.zeros_like(A)
R = np.zeros((n, n))

for i in range(n):
    v = A[:, i]

    for j in range(i):
        R[j, i] = np.dot(Q[:, j], A[:, i])
        v = v - R[j, i] * Q[:, j]

    R[i, i] = np.linalg.norm(v)
    Q[:, i] = v / R[i, i]

print("Matrix Q:")
print(Q)

print("\nMatrix R:")
print(R)

```

## Output

<img width="422" height="296" alt="image" src="https://github.com/user-attachments/assets/c7b925af-be6f-4730-9061-df7b6efc0971" />


## Result
Thus the QR decomposition algorithm using the Gram-Schmidt process is written and verified the result.
