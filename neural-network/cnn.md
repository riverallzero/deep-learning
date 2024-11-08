# CNN, Convolution Neural Network

![](https://github.com/user-attachments/assets/1cc80281-3770-4539-8da7-1c396b96236e)

## Convolution
moving the filter to the right by a stride interval, perform elementwise multiplication over an area equal to the filter size and sum the results

Given Input Data: $$\begin{bmatrix} 1 & 2 & 3 & 0 \\ 0 & 1 & 2 & 3 \\ 3 & 0 & 1 & 2 \\ 2 & 3 & 0 & 1\end{bmatrix}$$

Filter: $$\begin{bmatrix} 2 & 0 & 1 \\ 0 & 1 & 2 \\ 1 & 0 & 2\end{bmatrix}$$

Convolution, Feature Map(stride=1): $$\begin{bmatrix} \sum_{i,j} \left( \begin{bmatrix} 1 & 2 & 3 \\ 0 & 1 & 2 \\ 3 & 0 & 1 \end{bmatrix} \odot \begin{bmatrix} 2 & 0 & 1 \\ 0 & 1 & 2 \\ 1 & 0 & 2 \end{bmatrix} \right)_{ij} & \sum_{i,j} \left( \begin{bmatrix} 2 & 3 & 0 \\ 1 & 2 & 3 \\ 0 & 1 & 2 \end{bmatrix} \odot \begin{bmatrix} 2 & 0 & 1 \\ 0 & 1 & 2 \\ 1 & 0 & 2 \end{bmatrix} \right)_{ij} \\ \sum_{i,j} \left( \begin{bmatrix} 0 & 1 & 2 \\ 3 & 0 & 1 \\ 2 & 3 & 0 \end{bmatrix} \odot \begin{bmatrix} 2 & 0 & 1 \\ 0 & 1 & 2 \\ 1 & 0 & 2 \end{bmatrix} \right)_{ij} & \sum_{i,j} \left( \begin{bmatrix} 1 & 2 & 3 \\ 0 & 1 & 2 \\ 3 & 0 & 1 \end{bmatrix} \odot \begin{bmatrix} 2 & 0 & 1 \\ 0 & 1 & 2 \\ 1 & 0 & 2 \end{bmatrix} \right)_{ij} \end{bmatrix}$$

Therefore: $$\begin{bmatrix} 15 & 16 \\ 6 & 15 \end{bmatrix}$$

## Pooling
create a new feature map by extracting an area equal to the pooling size from the feature map

Given Feature Map: $$\begin{bmatrix} 4 & 9 & 2 & 5 \\ 5 & 6 & 2 & 4 \\ 2 & 4 & 5 & 4 \\ 5 & 6 & 8 & 4 \end{bmatrix}$$

Pool Size = 2 x 2

### average pooling
$$\begin{bmatrix} mean\left(\begin{bmatrix} 4 & 9 \\ 5 & 6 \end{bmatrix}\right) & mean\left(\begin{bmatrix} 2 & 5 \\ 2 & 4 \end{bmatrix}\right) \\ mean\left(\begin{bmatrix} 2 & 4 \\ 5 & 6 \end{bmatrix}\right) & mean\left(\begin{bmatrix} 5 & 4 \\ 8 & 4 \end{bmatrix}\right) \end{bmatrix}$$

Therefore: $$\begin{bmatrix} 6.0 & 3.3 \\ 4.3 & 5.3 \end{bmatrix}$$

### max pooling
$$\begin{bmatrix} max\left(\begin{bmatrix} 4 & 9 \\ 5 & 6 \end{bmatrix}\right) & max\left(\begin{bmatrix} 2 & 5 \\ 2 & 4 \end{bmatrix}\right) \\ max\left(\begin{bmatrix} 2 & 4 \\ 5 & 6 \end{bmatrix}\right) & max\left(\begin{bmatrix} 5 & 4 \\ 8 & 4 \end{bmatrix}\right) \end{bmatrix}$$

Therefore: $$\begin{bmatrix} 9 & 5 \\ 6 & 8 \end{bmatrix}$$

## Flatten
expanding two dimensions into one dimension

$$\begin{bmatrix} 9 & 5 \\ 6 & 8 \end{bmatrix}\rightarrow \begin{bmatrix} 9 \\ 5 \\ 6 \\ 8 \end{bmatrix}$$

## Droup Out
dropping out the nodes(input and hidden layer) in a neural network, if the hidden layers have 1000 neurons(nodes) and a dropout is applied with drop probability = 0.5, then 500 neurons would be randomly dropped in every iteration(batch)
