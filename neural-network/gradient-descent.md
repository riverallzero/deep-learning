# Gradient Descent
**Gradient descent** is an iterative optimization algorithm that finds the minimum of a function by following the direction of steepest descent, given by the negative gradient.

For a function f(x) with a single variable, the update rule is:

$$x_{t+1} = x_t - \alpha \frac{df}{dx}(x_t)$$

where:
- $x_t$ is the current position
- $\alpha$ is the learning rate (step size)
- $\frac{df}{dx}(x_t)$ is the derivative at the current position

For multivariate functions, the formula becomes:

$$x_{t+1} = x_t - \alpha \nabla f(x_t)$$

where $\nabla f(x_t)$ is the gradient vector containing partial derivatives with respect to each variable.

The learning rate $\alpha$ controls the algorithm's behavior:
- Large $\alpha$: Faster convergence but risk of overshooting the minimum
- Small $\alpha$: More stable but slower convergence
- Too large $\alpha$: May cause divergence
- Too small $\alpha$: May get stuck due to very slow progress

## Local / Global Minimum
![](https://github.com/user-attachments/assets/7b3c9b2a-337b-474f-b677-0d912cc84c72)

A key challenge is that gradient descent may converge to a local minimum(yellow) rather than the global minimum(red), depending on the initialization point. Techniques like random restarts or momentum can help avoid this issue.
