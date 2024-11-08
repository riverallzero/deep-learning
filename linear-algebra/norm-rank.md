# Norm and Rank

## Norm
$$||x_p||=(\sum_i |{x_i}|^p)^\frac{1}{p}$$

- norm1($$p=1$$) = manhattan distance
- norm2($$p=2$$) = euclidean distance

## Rank
Dimension of the vector space generated (or spanned) by its columns.
This corresponds to the maximal number of linearly independent columns of A.

### example
$$\begin{bmatrix}1 & 0 & 1 \\ 0 & 1 & 1 \\ 0 & 1 & 1\end{bmatrix}$$

- column1 and column2 &rarr; linearly independent
- column3 = column1 + column2 &rarr; linearly dependent

Therefore, $$rank = 2$$
