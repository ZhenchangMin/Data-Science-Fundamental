# Lec3: Random Variable

## Random Variable

![1757660643282](image/lec3/1757660643282.png)
On the given probability space $(\Omega, \Sigma, Pr)$, a random variable $X$ is a function from $\Omega$ to $\mathbb{R}$, satisfying:
for $x\in\mathbb{R}$, any set $\{\omega\in\Omega|X(\omega)\leq x\}$ is in $\Sigma$, i.e., $X$ is $\Sigma$-measurable.

Random variables in fact turning every sample in sample space $\Omega$ into a number in $\mathbb{R}$

*Why we need $\Sigma$-measurable?*
We want to calculate the probability of inequalities like $X\leq 2$, and the set must be in $\Sigma$, or we cannot calculate it based on our definition of probability.

For example, suppose we have $\Omega=\{a,b,c\}$, and $\Sigma=\{\emptyset, \{a\},\{b,c\},\Omega\}$.
Now we define a random variable $Y:\Omega\to\mathbb{R}$, such that $Y(a)=1, Y(b)=2, Y(c)=3$.
We consider the event $Y\leq 2$, and the set is $\{\omega\in\Omega|Y(\omega)\leq 2\}=\{a,b\}\notin\Sigma$
So we can know that Y is not $\Sigma$-measurable, and we cannot calculate $Pr(Y\leq 2)$.

Symbols:
![1758442454471](image/lec3/1758442454471.png)

For discrete random variable $X: \Omega\to\mathbb{Z}$, which means that $X$ can only be discrete numbers, like an integer.
As they're discrete, $S$ can be any subset of $\mathbb{Z}$, and $Pr(X\in S)$ is the sum of $Pr(X\in S_i)$ for every $S_i\in S$

Example: take six fair dice, and let $X$ be the sum of the numbers on the top faces.
Then $X$ is a discrete random variable, and $Pr(X=k)=1/6$ for $k=1,2,3,4,5,6$.
Let $S=\{2,4,6\}$, then $Pr(X\in S)=Pr(X=2)+Pr(X=4)+Pr(X=6)=1/3$.

### Distribution


### Discrete Random Variable

### Continuous Random Variable
