Probability is how likely an [[Event|event]] is to occur.

## Basic Probability
The probability of an [[Event]] $X$ is the proportion of occurences of $X$ in a large number of trials.
$$P(X)=\lim_{N\to\infty}(\frac{N(X)}{N})$$
Where:
- $P(X)$ is the probability of event $X$ occuring
- $N$ is the number of trials
- $N(X)$ is the number of occurences of event $X$ in $N$ trials

The probabilities of all possible [[Event|events]] (outcomes) must sum to unity
$$\sum^{M}_{i=1}P(E_i)=1$$
Where:
- $M$ is the number of events and $E_i$ is a particular event

## Composite Probability
The probability of one of a set of [[Mutually Exclusive Events]] occuring is given by the sum of their respective probabilities
$$P(X \text{ or } Y) = P(X) + P(Y)$$
If the events are not [[Mutually Exclusive Events|mutually exclusive]]
$$P(X \text{ or } Y = P(X) + P(Y) - P(X \text{ and } Y)$$
Where:
- $P(X \text{ and } Y)$ is the [[Joint Probability]] of $X$ and $Y$ occuring

## Joint Probability
The probability that two [[Independant Events]] $X$ and $Y$ both occur is given by the product of their respective probabilities
$$P(X\text{ and } Y) = P(X,Y) = P(X).P(Y)$$
If the events are not [[Independant Events|indepdant]]
$$P(X\text{ and } Y) = P(X).P(Y|X) = P(Y) .P(X|Y)$$
Where $P(Y|X)$ is the [[Conditional Probability]] that $Y$ will occur given that $X$ is known to have occured.


## Conditional Probability
The probability of an event $Y$ occuring given that an event $X$ is known to have occurred is given by rearranging the last expression
$$P(Y|X) = \frac{P(X\text{ and } Y)}{P(X)}=\frac{P(Y).P(X|Y)}{P(X)}$$
This relationship between the conditional probabilities $P(Y|X)$ amd $P(X|Y)$ is known as [[Bayes' Rule]].
