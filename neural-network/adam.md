# ADAM (Adaptive Moment Estimation)
ADAM is an optimization algorithm that combines the benefits of two popular methods: momentum and adaptive learning rates. It is particularly effective for training deep neural networks.

## Background: The Problem with Standard Gradient Descent
Standard gradient descent can face several challenges:
- Slow convergence in areas with shallow gradients
- Oscillation in areas with steep gradients
- Difficulty choosing an appropriate learning rate
- Getting stuck in saddle points

## Gradient Descent with Momentum
Momentum helps accelerate gradient descent by accumulating a moving average of past gradients, reducing oscillations.

Initialize:
$$V_{dW} = 0, V_{db} = 0$$

At each iteration t:
   - $$V_{dW} = \beta_1 V_{dW} + (1-\beta_1)dW$$
   - $$V_{db} = \beta_1 V_{db} + (1-\beta_1)db$$

Update parameters:
   - $$W := W - \alpha V_{dW}$$
   - $$b := b - \alpha V_{db}$$

where $$\beta_1$$ is the momentum coefficient.

## RMSprop (Root Mean Square Propagation)
RMSprop adapts the learning rates for each parameter by dividing them by the square root of an exponentially decaying average of squared gradients.

Initialize:
$$S_{dW} = 0, S_{db} = 0$$

At each iteration t:
   - $$S_{dW} = \beta_2 S_{dW} + (1-\beta_2)(dW)^2$$
   - $$S_{db} = \beta_2 S_{db} + (1-\beta_2)(db)^2$$

Update parameters:
   - $$W := W - \alpha \frac{dW}{\sqrt{S_{dW} + \epsilon}}$$
   - $$b := b - \alpha \frac{db}{\sqrt{S_{db} + \epsilon}}$$

where $$\beta_2$$ is the decay rate and $$\epsilon$$ is a small constant to prevent division by zero.

## ADAM Algorithm
ADAM combines momentum and RMSprop, using both first and second moments of the gradients.

1. Initialize:
   $$V_{dW} = 0, V_{db} = 0, S_{dW} = 0, S_{db} = 0$$

2. At each iteration t:
   
   Compute momentum (first moment):
      - $$V_{dW} = \beta_1 V_{dW} + (1-\beta_1)dW$$
      - $$V_{db} = \beta_1 V_{db} + (1-\beta_1)db$$

   Compute RMSprop (second moment):
      - $$S_{dW} = \beta_2 S_{dW} + (1-\beta_2)(dW)^2$$
      - $$S_{db} = \beta_2 S_{db} + (1-\beta_2)(db)^2$$

   Bias correction (not shown in original content but important):
      - $$V_{dW}^{corrected} = \frac{V_{dW}}{1-\beta_1^t}$$
      - $$S_{dW}^{corrected} = \frac{S_{dW}}{1-\beta_2^t}$$

3. Update parameters:
      - $$W := W - \alpha \frac{V_{dW}^{corrected}}{\sqrt{S_{dW}^{corrected} + \epsilon}}$$
      - $$b := b - \alpha \frac{V_{db}^{corrected}}{\sqrt{S_{db}^{corrected} + \epsilon}}$$

## Recommended Hyperparameters
From the original paper (Kingma & Ba, 2014):
- Learning rate($$\alpha$$): 0.001 (default)
- First moment decay rate($$\beta_1$$): 0.9
- Second moment decay rate($$\beta_2$$): 0.999
- Epsilon($$\epsilon$$): $$10^{-8}$$
