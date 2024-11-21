# Perceptron

The **Perceptron** is a fundamental type of neural network designed for **binary classification**. It performs a simple linear mapping of input features to an output and is often used for tasks like classifying data into two categories. 

A perceptron consists of:
- **Input Layer**: Receives feature data ($$x_1, x_2, \dots, x_n$$).
- **Output Layer**: Produces a binary output (e.g., 0 or 1).

### Architecture

Below is a visual representation of the perceptron architecture:

![](https://github.com/user-attachments/assets/c32984e7-d87b-44fc-9863-9304b462ff44)

The perceptron calculates the weighted sum of inputs, adds a bias ($$b$$), and applies an activation function ($$\sigma$$) to produce the output.

### Mathematical Representation

1. **Weighted Sum**:  
   $$Z = \sum_i W_i \cdot x_i + b = W_1 \cdot x_1 + W_2 \cdot x_2 + b$$

2. **Activation Function**:  
   $$\sigma(Z): if \ Z > 0=1, else \ 0$$

---

### Example: NAND Gate Implementation

Assume the weights($$W_1 = W_2 = -1$$) and bias($$b = 2$$). The perceptron behaves as a **NAND gate**, with the following input-output table:

| $$x_1$$ | $$x_2$$ | $$Z = W_1 \cdot x_1 + W_2 \cdot x_2 + b$$ | Output ($$\sigma(Z)$$) |
|:--:|:--:|:--:|:--:|
| 0  | 0  | 2   | 1 |
| 0  | 1  | 1   | 1 |
| 1  | 0  | 1   | 1 |
| 1  | 1  | 0   | 0 |

This resembles the truth table of a NAND gate:

- Output is **1** unless both $$x_1$$ and $$x_2$$ are **1**, in which case the output is **0**.

<img src='https://github.com/user-attachments/assets/5cb14f74-df58-43a3-b14f-7bfac26d2b63' width=50%>

---

### Key Takeaways

- The perceptron can simulate logical operations like AND, OR, and NAND by adjusting weights and biases. 
- It is limited to **linearly separable problems**; non-linear problems require more advanced architectures like multi-layer perceptrons (MLPs)
