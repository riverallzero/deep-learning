# Eigen Decomposition: square matrices
$A=V \Lambda V^{-1}$

1. eigenvalue diagonal matrix($\Lambda$): $det(A-I\Lambda)=0$
2. eigenvector matrix($V$): $(A-I\Lambda)v=0$

## example
Given matrix A = $\begin{bmatrix} 1 & 2 \\ 5 & 4 \end{bmatrix}$

### i) Finding Eigenvalues: $\det(A-\lambda I) = 0$

$A-\lambda I = \begin{bmatrix} 1 & 2 \\ 5 & 4 \end{bmatrix} - \lambda\begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix} = \begin{bmatrix} 1-\lambda & 2 \\ 5 & 4-\lambda \end{bmatrix}$

$(1-\lambda)(4-\lambda) - 2 \cdot 5 = 0$

$\lambda^2 - 5\lambda - 6 = 0$

$(\lambda-6)(\lambda+1) = 0$

Therefore, $\lambda = -1$ or $\lambda = 6$

### ii) Eigenvector for $\lambda = -1$

$(A+I)v = 0$

$\begin{bmatrix} 2 & 2 \\ 5 & 5 \end{bmatrix}\begin{bmatrix} v_1 \\ v_2 \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \end{bmatrix}$

System of equations:
* $2v_1 + 2v_2 = 0$
* $5v_1 + 5v_2 = 0$

Solution: $v_1 = -1$, $v_2 = 1$

Eigenvector = $\begin{bmatrix} -1 \\ 1 \end{bmatrix}$

### iii) Eigenvector for $\lambda = 6$

$(A-6I)v = 0$

$\begin{bmatrix} -5 & 2 \\ 5 & -2 \end{bmatrix}\begin{bmatrix} v_1 \\ v_2 \end{bmatrix} = \begin{bmatrix} 0 \\ 0 \end{bmatrix}$

System of equations:
* $-5v_1 + 2v_2 = 0$
* $5v_1 - 2v_2 = 0$

Solution: $v_1 = \frac{2}{5}$, $v_2 = 1$

Eigenvector = $\begin{bmatrix} \frac{2}{5} \\ 1 \end{bmatrix}$

### iv) Diagonalization: $A = V\Lambda V^{-1}$

$V = \begin{bmatrix} -1 & \frac{2}{5} \\ 1 & 1 \end{bmatrix}$

$\Lambda = \begin{bmatrix} -1 & 0 \\ 0 & 6 \end{bmatrix}$

$V^{-1} = \frac{1}{(-1)(1)-(\frac{2}{5})(1)}\begin{bmatrix} 1 & -\frac{2}{5} \\ -1 & -1 \end{bmatrix} = \begin{bmatrix} -\frac{5}{7} & \frac{2}{7} \\ \frac{5}{7} & \frac{5}{7} \end{bmatrix}$

Therefore:
$A = \begin{bmatrix} -1 & \frac{2}{5} \\ 1 & 1 \end{bmatrix}\begin{bmatrix} -1 & 0 \\ 0 & 6 \end{bmatrix}\begin{bmatrix} -\frac{5}{7} & \frac{2}{7} \\ \frac{5}{7} & \frac{5}{7} \end{bmatrix}$
