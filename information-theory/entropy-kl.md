# Entropy, Cross Entropy and KL Divergence

## Entropy
degree of uncertainty, a numerical representation of how difficult it is to predict the likelihood of an event occurring

$$H(P)=-\sum P(x)log_2P(x)$$

### proof
$$surprise = log_2\left(\frac{1}{probability}\right)$$

flip 100 times, how surprising is it?
||heads|tails|
|:--:|:--:|:--:|
|probability($$P(x)$$)|0.9|0.1|
|surprise($$log_2\left(\frac{1}{P(x)}\right)$$)|0.15|3.32|

expectation getting heads or tails in 100 flips: $$\text{total surprise}=(0.9\times 100)\times 0.15 + (0.1\times 100) \times 3.32 = 46.7$$

surprise for each time flip coin(=entropy): $$\text{entropy}=\frac{(0.9\times 100)\times 0.15 + (0.1\times 100) \times 3.32}{100} = 0.47$$

make normalized formula
1. $$\text{entropy}=\frac{(0.9\times 100)\times 0.15 + (0.1\times 100) \times 3.32}{100}$$
2. $$\frac{(0.9\times \sout{100})\times 0.15 + (0.1\times \sout{100}) \times 3.32}{\sout{100}}$$
3. $$P(x_1)\times log_2\left(\frac{1}{P(x_1)}\right)+P(x_2)\times log_2\left(\frac{1}{P(x_2)}\right)$$
4. $$\sum P(x) log_2\left(\frac{1}{P(x)}\right)$$
5. $$\sum P(x)[log_21-log_2P(x)]$$
6. $$-\sum P(x)log_2P(x)$$

Therefore, $$\text{entropy}=H(P)=-\sum P(x)log_2P(x)$$

## Cross entropy
measure of how surprised the model was by the events that actually happened, can evaluate how close model's predictions are to the true distribution

$$H(P,Q)=-\sum P(x)log_2Q(x)$$


## Kullback Leibler Divergence
measure of how one reference probability distribution $$P$$ is different from a second probability distribution $$Q$$

$$D_{KL}=\sum P(x)[log_2P(x)-log_2Q(x)]$$
