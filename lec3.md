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
The (Cumulative) Distribution Function (CDF) of a random variable:

$$
F_X(x)=Pr(X\leq x)
$$

All probabilities about random variables are defined in terms of CDF, and the original probability space is no longer needed.

Two random variables $X$ and $Y$ are **identically distributed** if $F_X = F_Y$

CDF is:
- Monotone: $F_X(x)\leq F_X(y)$ if $x\leq y$
- Bounded: $\lim\limits_{x\to -\infty}F_X(x) = 0$ and $\lim\limits_{x\to \infty}F_X(x) = 1$

### Discrete Random Variable
A random variable $X$ is **discrete** if $X(\Omega)$ is countable.
$X(\Omega)$ is the set of all possible values of $X$.

For a discrete random variable $X$, the **probability mass function** (PMF) is defined as:

$$
p_X(x)=Pr(X=x)
$$

And the CDF satisfies:
$$
F_X(y)=\sum\limits_{x'\leq y}p_X(x')
$$

### Continuous Random Variable
A random variable $X$ is **continuous** if its CDF can be expressed as:

$$
F_X(y) = Pr(X \leq y) = \int_{-\infty}^{y} f_X(x) \, dx
$$
which $f_X$ is the **probability density function** (PDF) of $X$.

There are random variables that are neither discrete nor continuous.

### Independence
If for $X,Y$ random variables, events $X=x$ and $Y=y$ are independent events for all x and y, then $X$ and $Y$ are mutually independent.

If for $X_1,X_2,\dots,X_n$ random variables, events $X_1=x_1,X_2=x_2,\dots,X_n=x_n$ are independent events for all $x_1,x_2,\dots,x_n$, then $X_1,X_2,\dots,X_n$ are mutually independent.
And we have the equation of their pmf:
$$
p_{(X_1,X_2,\dots,X_n)}(x_1, x_2,\dots,x_n)=Pr(X_1=x_1 \cap X_2=x_2\dots X_n=x_n)=p_{X_1}(x_1)p_{X_2}(x_2)\dots p_{X_n}(x_n)
$$

For general random variables, replace $X_i=x_i$ with $X_i\leq x_i$, and we got the definition of independence.

### Random Vector
