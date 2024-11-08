# Singular Value Decomposition: square & nonsquare matrices
$$A=U \Sigma V^T$$

1. left singular vectors of A($$V$$): eigenvector & value of $$A^TA$$ &rarr; desc sort and normalize
2. right singular vectors of A($$U$$): eigenvector & value of $$AA^T$$ &rarr; desc sort and normalize
3. singular values of A($$\Sigma$$)
   - take the square root of eigenvalues
   - arrange these in descending order on the diagonal of $$\Sigma$$

## example
Given matrix $$A = \begin{bmatrix} 3 & 1 & 1 \\ -1 & 3 & 1 \end{bmatrix}$$

### i) Computing $$AA^T$$

$$AA^T = \begin{bmatrix} 3 & 1 & 1 \\ -1 & 3 & 1 \end{bmatrix}\begin{bmatrix} 3 & -1 \\ 1 & 3 \\ 1 & 1 \end{bmatrix} = \begin{bmatrix} 11 & 1 \\ 1 & 11 \end{bmatrix}$$

#### Eigenvalues:
$$\det\begin{pmatrix}\begin{bmatrix} 11 & 1 \\ 1 & 11 \end{bmatrix}-\lambda\begin{bmatrix} 1 & 0 \\ 0 & 1 \end{bmatrix}\end{pmatrix}=0$$

$$(11-\lambda)^2-1=0$$
$$(11-\lambda)^2=1$$

Therefore, $$\lambda=10$$ or $$\lambda=12$$

#### Eigenvectors:
For $$\lambda=10$$:
$$\begin{bmatrix} 11-10 & 1 \\ 1 & 11-10 \end{bmatrix}\begin{bmatrix} v_1 \\ v_2 \end{bmatrix}=\begin{bmatrix} 0 \\ 0 \end{bmatrix}$$

$$\begin{cases} v_1+v_2=0 \\ v_1+v_2=0 \end{cases}$$

$$v_1=-1, v_2=1 \rightarrow \begin{bmatrix} -1 \\ 1 \end{bmatrix}$$

For $$\lambda=12$$:
$$\begin{bmatrix} -1 & 1 \\ 1 & -1 \end{bmatrix}\begin{bmatrix} v_1 \\ v_2 \end{bmatrix}=\begin{bmatrix} 0 \\ 0 \end{bmatrix}$$

$$\begin{cases} -v_1+v_2=0 \\ v_1-v_2=0 \end{cases}$$

$$v_1=1, v_2=1 \rightarrow \begin{bmatrix} 1 \\ 1 \end{bmatrix}$$

#### Sort, descending & normalize:
$$\begin{bmatrix} 1 & -1 \\ 1 & 1 \end{bmatrix} \rightarrow U= \begin{bmatrix} \frac{1}{\sqrt{2}} & -\frac{1}{\sqrt{2}} \\ \frac{1}{\sqrt{2}} & \frac{1}{\sqrt{2}} \end{bmatrix}$$

### ii) Computing $A^TA$

$$A^TA = \begin{bmatrix} 3 & -1 \\ 1 & 3 \\ 1 & 1 \end{bmatrix}\begin{bmatrix} 3 & 1 & 1 \\ -1 & 3 & 1 \end{bmatrix} = \begin{bmatrix} 10 & 0 & 2 \\ 0 & 10 & 4 \\ 2 & 4 & 2 \end{bmatrix}$$

#### Eigenvalues:
$$\det\begin{pmatrix}\begin{bmatrix} 10 & 0 & 2 \\ 0 & 10 & 4 \\ 2 & 4 & 2 \end{bmatrix}-\lambda\begin{bmatrix} 1 & 0 & 0 \\ 0 & 1 & 0 \\ 0 & 0 & 1 \end{bmatrix}\end{pmatrix}=0$$

$$(10-\lambda)(10-\lambda)(2-\lambda)-2\cdot2(10-\lambda)+4\cdot4(10-\lambda)=0$$

$$\lambda(\lambda^2-22\lambda+120)=\lambda(\lambda-10)(\lambda-12)=0$$

Therefore, $$\lambda=0$$ or $$\lambda=10$$ or $$\lambda=12$$

#### Eigenvectors:
For $$\lambda=0$$:
$$\begin{bmatrix} 10 & 0 & 2 \\ 0 & 10 & 4 \\ 2 & 4 & 2 \end{bmatrix}\begin{bmatrix} v_1 \\ v_2 \\ v_3 \end{bmatrix}=\begin{bmatrix} 0 \\ 0 \\ 0 \end{bmatrix}$$

$$\begin{cases} 10v_1+2v_3=0 \\ 10v_2+4v_3=0 \\ 2v_1+4v_2+2v_3=0 \end{cases}$$

$$v_1=1, v_2=2, v_3=-5 \rightarrow \begin{bmatrix} 1 \\ 2 \\ -5 \end{bmatrix}$$

For $$\lambda=10$$:
$$\begin{bmatrix} 0 & 0 & 2 \\ 0 & 0 & 4 \\ 2 & 4 & -8 \end{bmatrix}\begin{bmatrix} v_1 \\ v_2 \\ v_3 \end{bmatrix}=\begin{bmatrix} 0 \\ 0 \\ 0 \end{bmatrix}$$

$$\begin{cases} 2v_3=0 \\ 4v_3=0 \\ 2v_1+4v_2-8v_3=0 \end{cases}$$

$$v_1=2, v_2=-1, v_3=0 \rightarrow \begin{bmatrix} 2 \\ -1 \\ 0 \end{bmatrix}$$

For $$\lambda=12$$:
$$\begin{cases} -2v_1+2v_3=0, v_3=v_1 \\ -2v_2+4v_3=0, 2v_1=v_2 \\ 2v_1+4v_2-10v_3=0 \end{cases}$$

$$v_1=1, v_2=2, v_3=1 \rightarrow \begin{bmatrix} 1 \\ 2 \\ 1 \end{bmatrix}$$

#### Sort, descending & normalize:
$$\begin{bmatrix} 1 & 2 & 1 \\ 2 & -1 & 2 \\ 1 & 0 & -5 \end{bmatrix} \rightarrow V=\begin{bmatrix} \frac{1}{\sqrt{6}} & \frac{2}{\sqrt{5}} & \frac{1}{\sqrt{30}} \\ \frac{2}{\sqrt{6}} & -\frac{1}{\sqrt{5}} & \frac{2}{\sqrt{30}} \\ \frac{1}{\sqrt{6}} & 0 & -\frac{5}{\sqrt{30}} \end{bmatrix}$$

$$V^T=\begin{bmatrix} \frac{1}{\sqrt{6}} & \frac{2}{\sqrt{6}} & \frac{1}{\sqrt{6}} \\ \frac{2}{\sqrt{5}} & -\frac{1}{\sqrt{5}} & 0 \\ \frac{1}{\sqrt{30}} & \frac{2}{\sqrt{30}} & -\frac{5}{\sqrt{30}} \end{bmatrix}$$

### iii) Singular Values ($\Sigma$)
$$\begin{bmatrix} \sqrt{12} & 0 & 0 \\ 0 & \sqrt{10} & 0 \\ 0& 0 & 0 \end{bmatrix} \rightarrow \Sigma = \begin{bmatrix} \sqrt{12} & 0 & 0 \\ 0 & \sqrt{10} & 0 \end{bmatrix}$$

Therefore:

$$A = \begin{bmatrix} \frac{1}{\sqrt{2}} & -\frac{1}{\sqrt{2}} \\ \frac{1}{\sqrt{2}} & \frac{1}{\sqrt{2}} \end{bmatrix}\begin{bmatrix} \sqrt{12} & 0 & 0 \\ 0 & \sqrt{10} & 0 \end{bmatrix}\begin{bmatrix} \frac{1}{\sqrt{6}} & \frac{2}{\sqrt{6}} & \frac{1}{\sqrt{6}} \\ \frac{2}{\sqrt{5}} & -\frac{1}{\sqrt{5}} & 0 \\ \frac{1}{\sqrt{30}} & \frac{2}{\sqrt{30}} & -\frac{5}{\sqrt{30}} \end{bmatrix}$$
