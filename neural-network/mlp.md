# MLP(Multi Layer Perceptrons)
**Multi Layer Perceptrons(MLP)** is an extension of the basic perceptron architecture. While a simple perceptron is limited to binary classification and can only solve linearly separable problems, MLP overcomes these limitations by:

- Adding hidden layers between input and output layers
- Using non-linear activation functions
- Enabling it to solve non-linear problems and learn complex patterns

This architecture forms the backbone of many modern neural network architectures.

## Architecture
```
  Input Layer    Hidden Layer 1     Hidden Layer 2      Output Layer
  (8 neurons)     (3 neurons)        (3 neurons)         (2 neurons)
  -----------     ----------         ----------          -----------
       ○
       ○
       ○               ○                 ○                   ○
       ○               ○                 ○
       ○               ○                 ○                   ○
       ○
       ○
       ○
  -----------     ----------         ----------          -----------
       a               b                 c                   d
```

## Layer
### Hidden Layer 1
$$b_j = \sigma(\sum_{i=0}^7 W_{ij}^{(1)} \times a_i + bias_{j}^{(1)})$$

### Hidden Layer 2
$$c_k = \sigma(\sum_{j=0}^2 W_{jk}^{(2)} \times b_j + bias_{k}^{(2)})$$

### Output Layer
$$d_m = \sigma(\sum_{k=0}^2 W_{km}^{(3)} \times c_k + bias_{m}^{(3)})$$

### Summary
- $$weights=8 \times 3+3 \times 3+3 \times 2=39$$
- $$bias=3+3+2=8$$

## Activate Function
- Sigmoid
  - $$\sigma(x)=\frac{1}{1+e^{-x}}$$
  - $$\sigma'(x)=\sigma(x)(1-\sigma(x))$$

- ReLU
  - $$f(x)=max(0,x)$$
  - $$f'(x)=0(x<0), 1(x\geq0)$$

## Back Propagation
```
Hidden Layer 2      Output Layer         Target
 (3 neurons)        (2 neurons)         (answer)
 ----------         -----------        -----------


       ○              ○ = 0.3              0.8           
       ○  
       ○              ○ = 0.7              0.2
     
     
     
 ----------         -----------        -----------
     c                    d                  t 
```

### 1. Calculate Error
For each output neuron, the error is calculated as the difference between the target value($$t$$) and the actual output value ($$d$$).

- $$E_{d_0} = t_0 - d_0 = 0.8 - 0.3 = 0.5$$
- $$E_{d_1} = t_1 - d_1 = 0.2 - 0.7 = -0.5$$

### 2. Calculate Gradient
The gradient of the error with respect to each weight is calculated. The gradient indicates how much a small change in the weight will impact the error.

- For a single weight $$W_{km}^{(3)}$$ (from Hidden Layer 2 to Output Layer), the gradient can be calculated as follows.
- Assuming we use the Mean Squared Error (MSE) and a sigmoid activation function: 
$$E = \frac{1}{2}(d - t)^2$$
- The gradient for weight $$W_{km}^{(3)}$$ is calculated as:
$$\text{Gradient} = \frac{\partial E}{\partial W_{km}^{(3)}} = (d_m - t_m) \times \sigma'(z_m) \times c_k$$
- Here, $$z_m$$ is the weighted sum $$W_{km}^{(3)} \times c_k + bias_{m}^{(3)}$$, and $$\sigma'(z_m)$$ is the derivative of the sigmoid function. The term $$c_k$$ represents the neuron value from Hidden Layer 2.

### 3. Update Weights
Using the calculated gradient, update the weights using a learning rate($$\eta$$), which controls the step size of the update. The weight update rule typically follows.
   
- $$W_{i(new)} = W_{i(old)} - \eta \times \text{Gradient}\left(\frac{\partial E}{\partial W_i}\right)$$