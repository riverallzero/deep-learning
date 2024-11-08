# Probability Distribution

## Bernoulli 
takes the value 1 with probability $$p$$ and the value 0 with probability $$q=1-p$$, e.g. yes-no question

$$X \sim B(1,p) \ or \ B(p)$$

$$f(x) = \begin{cases} p^xq^{1-x} & x = 0,1 \\ 0 & otherwise \end{cases}$$

## Multinomial
takes the value $$i$$ with probability $$p_i$$ for $$i=1,2,\cdots,k$$, e.g., multi-choice question with $$k$$ possible outcomes

$$(X_1,X_2,X_3) \sim Multi(n,p_1,p_2,p_3)\\ x_1+x_2+x_3=n$$

$$f(x_1,x_2,\cdots,x_k)=\frac{n!}{x_1!x_2! \cdots x_k!}p_1^{x_1}p_2^{x_2}\cdots p_k^{x_k} \ \ \ \begin{cases}0 \leq x_i \geq n, i=1,2,\cdots,k\\p_1+p_2+\cdots+p_k=1\\x_1+x_2+\cdots+x_k=n\end{cases}$$

## Normal(Gaussian)
takes a continuous value with highest probability at the mean $$\mu$$, with probabilities decreasing symmetrically as values move away from $$\mu$$ according to the standard deviation $$\sigma$$, e.g. heights of people or measurement errors

$$X \sim N(\mu,\sigma^2)$$

$$f(x)=\frac{1}{\sqrt{2\pi}\sigma}exp\left(\frac{-{(x-\mu)}^2}{2\sigma^2}\right), \ -\inf<x, \mu < \inf, \sigma > 0$$

## Poisson
takes the integer value $$k$$ with probability of occurrence proportional, where $$m$$ is the average rate of occurrence($$\mu$$), e.g. number of emails received in an hour

$$X \sim P(m)$$

$$f(x)=\frac{m^x}{x!}e^{-m}$$
