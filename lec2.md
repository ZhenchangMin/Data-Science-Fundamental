# Lec2: Probability Space
## Probability Space(review)
For `discrete probability space`, $\Omega$ is finite or countably infinite.

## Probability Space and Measure(review)
A probability measure, aka probability law, is a function $Pr: \Sigma \to [0, 1]$ such that:
- $Pr(\Omega) = 1$
- $Pr(A1 \cup A2 \cup ... \cup An) = Pr(A1) + Pr(A2) + ... + Pr(An)$

## Classical Probability
For every event $A \in \Omega$, $Pr(A) = \frac{|A|}{|\Omega|}$

## Geometric Probability
For every event $A \in \Omega$, $Pr(A) = \frac{Vol(A)}{Vol(\Omega)}$

## Ramsey Theory
In any party of six people, there are either three people mutually strangers or at least three of them are mutual acquaintances.
Any 2-coloring of $K_{6}$ has a monochromatic triangle $K_{3}$.

Any 2-coloring of $K_{n}$ has a monochromatic triangle $K_{k}$.
Ramsey number $R(k, k)$ is the smallest number $n$ that satisfy.
In this case, we see R(3, 3) = 6

## Probabilistic Method
If $C^{n}_{k}2^{1-(C^{k}_{2})} < 1$, then $\exists$ 2-coloring of $K_{n}$ with no monochromatic $K_{k}$ subgraph.
Proof:
- For each subset $S \subseteq k$, define $A_{S} = {K_{S} monochromatic}$, then $Pr(A_S)$ is $2^{1-(C^{k}_{2})}$.
- By Union Bond: $Pr(\bigcup_{S \subseteq k} A_S) \leq C^{n}_{k}2^{1-(C^{k}_{2})}$
- By assumption, $Pr(\bigcup_{S \subseteq k} A_S) < 1$
- By Chebyshev's Inequality: $Pr(\bigcup_{S \subseteq k} A_S) \geq 1 - (1 - Pr(\bigcup_{S \subseteq k} A_S))^{n}$
- Hence, $\exists$ 2-coloring of $K_{n}$ with no monochromatic $K_{k}$ subgraph.

## Conditional Probability
The probability of an event $A$ given that $B$ has occurred is defined as $Pr(A|B) = \frac{Pr(A \cap B)}{Pr(B)}$.
$Pr(B)$ must be greater than 0.

## Chain Rule
$Pr(\cap_{i=1}^{n} A_{i}) = \prod_{i=1}^{n} Pr(A_{i}|\cap_{j<i}A_j)$

## Law of Total Probability
$Pr(A) = \sum_{B \in \Sigma} Pr(A|B)Pr(B)$

## Bayes' Law
$Pr(A|B) = \frac{Pr(B|A)Pr(A)}{Pr(B)}$

## Independence
The occurrence of event B changes the probability of event A, from Pr(A) to Pr(A | B)
When A and B are independent, $Pr(A|B) = Pr(A)$
And $Pr(A \cap B) = Pr(A)Pr(B)$

### Conditional Independence
$Pr(A \cap B | C) = Pr(A | C)Pr(B | C)$

### Independence of Several Events
$Pr(A \cap B \cap C) = Pr(A)Pr(B)Pr(C)$
$Pr(\cap_{i=1}^{n} A_{i}) = \prod_{i=1}^{n} Pr(A_{i})$