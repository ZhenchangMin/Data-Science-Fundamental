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
Given $(\Omega, \Sigma, Pr)$, a random vector $X=(X_1,X_2,\dots,X_n)$ is a vector composed of multiple random variables $X_i$

The **joint CDF** $F_X(x_1,x_2,\dots,x_n)$ is defined as:
$$
F_X(x_1,x_2,\dots,x_n)=Pr(X_1\leq x_1 \cap X_2\leq x_2 \cap \dots \cap X_n\leq x_n)
$$
This can be viewed as a joint probability when all sub-random variables are no more than the given values, so we use \cap to join them together.

For discrete random vector, the **joint mass function** (PMF) is defined as:
$$
p_{(X_1,X_2,\dots,X_n)}(x_1, x_2,\dots,x_n)=Pr(X_1=x_1 \cap X_2=x_2\dots X_n=x_n)
$$

The marginal distribution of $X_i$ in $X=(X_1,X_2,\dots,X_n)$ is defined as:
$$
p_{X_i}(x_i)=\sum_{x_1,\dots x_{i-1}, x_{i+1}, \dots,x_n} p_{(X_1\dots X_n)}(x_1\dots x_n)
$$

![1758505190071](image/lec3/1758505190071.png)
In this case, we wonna calculate the marginal distribution, then we just sum up one line or a column and we could get the answer.
Like in column1, we want to get $p_{X_1}(x_1)$, so we view $Y$ as another random variable and add up all pmf in column1.

## Discrete Random Vector

### Probability Mass Function (PMF)
- As histogram: $p_{X}$ can be viewed as the histogram of the probability distribution.
- As vector: $p_{X}$ can be viewed as a vector $p_{X}\in[0,1]^{R}$, where R is the set of all possible values of $X$, and the sum of $x_i$ in $p_{X}$ is 1.

If $Y=f(X)$, Y is also a random variable, and its pmf is:
$$
p_{Y}(y)=\sum_{x: f(x)=y}p_{X}(x)
$$
That is the sum of all pmf where $f(x)=y$.

## Bernoulli Trial
A bernoulli trial is an experiment with two possible outcomes: success or failure.
A **bernoulli random variable** $X$ takes in values in $\{0,1\}$, and its pmf is:
$$
p_{X}(k)=Pr(X=k)=
\begin{cases}
p,&\text{if } k=1\\
1-p,&\text{if } k=0
\end{cases}
$$
where $p$ is a parameter representing the probability of success.

Indicator: For event $A$, its indicator random variable $X$ is defined as:
$$
X=I(A)\begin{cases}
1,&\text{if } A\\
0,&\text{if } \neg A
\end{cases}
$$

### Binomial Distribution
$X$: number of successes in $n$ i.i.d. (independent and identically distributed) Bernoulli trials with parameter $p$
A binomial random variable $X$ takes value in $\{0,1,\dots n\}$, and its pmf is:
$$
p_{X}(k)=Pr(X=k)=\binom{n}{k}p^k(1-p)^{n-k},\text{if } k=0,1,2,\dots,n
$$
We say that $X$ follows the **binomial distribution** with parameters $n$ and $p$, denoted $X\sim B(n,p)$ or $B(n,p)$.

### Geometric Distribution
$X$: number of Bernoulli trials until the first success in i.i.d. Bernoulli trials with parameter $p$

Example: trials needed to get one HEADS in a sequence of coin flips

A geometric random variable $X$ takes value in $\{1,2,\dots\}$, and its pmf is:
$$
p_{X}(k)=Pr(X=k)=(1-p)^{k-1}p,\text{if } k=1,2,\dots
$$
We say that $X$ follows the **geometric distribution** with parameter $p\in[0,1]$, denoted $X\sim Geo(p)$ or $Geometric(p)$.

Geometric distribution is memoryless: for $k\geq 1$,$n\geq 0$
$$
Pr(X=k+n|X>n)=Pr(X= k)
$$
That is, if we didn't get a success in the first $n$ trials, the probability of getting a success in the next $k$ trials is the same as the probability of getting a success in the very beginning $k$ trials.
This is like having no memory cuz past trials don't affect the future trials.
![proof](image/lec3/1758535158439.png)
Geometric distribution is the only **discrete memoryless distribution** with the range of values $\{1,2,\dots\}$.

### Sum of Independent Random Variables
If random variables $X$ and $Y$ are independent, then $X+Y$ satisfies:

$p_{X+Y}(z)=Pr(X+Y=z)=\sum_x Pr(X=x\cap Y=z-x)$, using total probability and sum up all possible pairs $(x,y)$ where $x+y=z$.
Then by independence we get:
$$
p_{X+Y}(z)=Pr(X+Y=z)=\sum_x Pr(X=x\cap Y=z-x)=\sum_x p_{X}(x)p_{Y}(z-x)
$$

This defines the **convolution** of two random variables, denoted as $p_{X+Y}=p_{X}*p_{Y}$.

### Negative Binomial Distribution
Can be viewed as “**multiple successes**” generalization of geometric distribution
$X$: number of **failures** in a sequence of i.i.d. Bernoulli trials before $r$ successes
A negative binomial random variable $X$ takes value in $\{0,1,2,\dots\}$, and its pmf is:
$$
p_{X}(k)=Pr(X=k)=\binom{k+r-1}{k}p^r(1-p)^k=(-1)^k\binom{-r}{k}p^r(1-p)^k,\text{if } k=0,1,2,\dots
$$
We say that $X$ follows the **negative binomial distribution** with parameters $r$ and $p$, denoted $X\sim NegBin(r,p)$

As the last trial must be a success, so total is $r-1$ successes and $k$ failures, so choose $k$ from $r-1+k$ trials.

Negative Binomial Distribution can be generated from Geometric Distribution:
$$
X=(X_1-1)+(X_2-1)+\dots+(X_r-1), \text{for i.i.d. } X_i\sim Geo(p)
$$
As we only need the number of failures, we need to subtract 1 from each $X_i$ to subtract the success numbers.

### Hypergeometric Distribution
$X$: number of successes in $n$ draws, **without replacement**, from a **finite population** of $N$ objects, including exactly $M$ ones counted as successes.

Like in a jar we have $N$ balls in total, and $M$ of them are red, we draw $n$ balls **witout replacement** and count the number of red balls as successes.

A hypergeometric random variable $X$ takes value in $\{0, 1\dots n\}$ and
$$
p_X(k)=Pr(X=k)=\frac{\binom{M}{k}\binom{N-M}{n-k}}{\binom{N}{n}},k=0,1\dots n
$$
We say that $X$ follows the **hypergeometric distribution** with parameters $N$, $M$, $n$,
where N ≥ 0, 0 ≤ M ≤ N, and 0 ≤ n ≤ N are integers.

### Multinomial Distribution
“multi-dimensional” generalization of binomial distribution

**Trials with multiple outcomes**: There are i.i.d. trials, each having $m$ possible outcomes, where the probability of the $i$th outcome is $p_i$. Let $X_i$ be the total number of $i$th kind of outcome

Modelize: **Balls-into-bin model**: Throw $n$ balls into $m$ bins, where each bin has probability $p_i$ of receiving the ball.
Let $X_i$ be the number of balls in the $i$th bin.

Easily we know $p_1+p_2+\dots+p_m=1$.

Now we create a random vector $X=(X_1,X_2,\dots,X_m)$ where $X_i$ is the number of balls in the $i$th bin.
Easily we know $X=(X_1,X_2,\dots,X_m)$ takes value $(k_1\dots k_m)\in\{0,1,\dots n\}^m$ satisfying $\sum k_i=n$
And we have:
$$
p_{(X_1,X_2,\dots,X_m)}(k_1,k_2,\dots,k_m)=Pr(\bigcap_{i=1}^m(X_i=k_i))=\frac{n!}{k_1!k_2!\dots k_m!}p_1^{k_1}p_2^{k_2}\dots p_m^{k_m}
$$
How we get this equation?
Firstly suppose we get the result in a certain order, i.e. $X=(X_1,X_2,\dots,X_m)$, so we get $p_1^{k_1}p_2^{k_2}\dots p_m^{k_m}$
And then we need to calculate how many orders to get the final answer.
This can be viewed as we distribute $n$ places for $m$, in which $k_1$ for $X_1$, $k_2$ for $X_2$, $\dots$, $k_m$ for $X_m$.
So $n!$ would be all possible orders, and we divide $k_i!$ because we change the location of inline places does not create new order, so we divide them.
![1758728421077](image/lec3/1758728421077.png)
We say that $(X_1,X_2,\dots,X_m)$ follows the **multinomial distribution** with parameters $m$, $n$ and $p=(p_1,p_2,\dots,p_m)\in[0,1]^m$ such that $p_1+p_2+\dots p_m=1$
For each individual $1\leq i\leq m$, $X_i$ follows the **binomial distribution** with parameters $n$ and $p_i$.
$$
X_i\sim Bin(n,p_i)
$$
The marginal distribution of $X_i$ is $Bin(n,p_i)$.

### Poisson Distribution
Take a look at Binomial Distribution, we know that it is the distribution of number of successes in $n$ trials with probability of success $p$.
In real life usually $n$ is very large, and it is unknown, but we know the **expectation** $np=\lambda$, so we have:
$$
p_{Bin(n,\lambda/n)}(k)=\binom{n}{k}(\frac{\lambda}{k})^k(1-\frac{\lambda}{k})^{n-k}
$$
When n is extremely large, $\binom{n}{k}$ can be viewed as 1, and $(1-\frac{\lambda}{k})^{n-k}=(1-\frac{\lambda}{k})^{n}(1-\frac{\lambda}{k})^{-k}$.
$(1-\frac{\lambda}{k})^{-k}$ can be viewed as 1 when $n\to\infty$, so we focus on $(1-\frac{\lambda}{k})^{n}$.
$\lim\limits_{n\to\infty}(1-\frac{\lambda}{k})^{n}=e^{-\lambda}$
And in conclusion, we have:
$$
p_{Bin(n,\lambda/n)}(k)=\frac{\lambda^k}{k!}e^{-\lambda}
$$

A Poisson random variable $X$ takes value in $\{0,1,2,\dots\}$, and its pmf is:
$$
p_{X}(k)=Pr(X=k)=\frac{\lambda^k}{k!}e^{-\lambda}
$$
We say that $X$ follows the **Poisson distribution** with parameter $\lambda>0$, denoted $X\sim Pois(\lambda)$.

#### Sum of Poisson Random Variables
Given that if $X\sim Bin(n_1,p)$, $Y\sim Bin(n_2,p)$, $X+Y\sim Bin(n_1+n_2,p)$
Does Poisson distribution hold for $X\sim Pois(\lambda_1)$ and $Y\sim Pois(\lambda_2)$, then $X+Y\sim Pois(\lambda_1+\lambda_2)$?
![1758782385675](image/lec3/1758782385675.png)

#### Poisson Approximation
