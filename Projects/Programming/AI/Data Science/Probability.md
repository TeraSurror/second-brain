- Way of quantifying the uncertainty associated with events chosen from some universe of events.

P(E) -> probability of an event E happening

## Dependence and Independence

- 2 events E and F are dependent if knowing something about whether E happens gives us information about whether F happens. Otherwise they are independent. 

Mathematically, 2 events are independent if the probability that they both happen is the product of the probabilities that each one happens:

P(E, F) = P(E) * P(F) [Only when they are independent]

## Conditional Probability

If E and F are not necessarily independent, we define the probability of E conditional on F as:
P(E | F) = P(E, F) / P(F)
Think of it as the probability that E happens, given that F has happened

When E and F are independent, P(E | F) = P(E)

Note: Check out the problems given in the Data Science From Scratch Book

## Bayes Theorem

P(E | F)  = (P(E, F) P(E)) / P(F)

Probability of F can be written as,
P(F) = P(F, E) + P(F | ~E)

Therefore, Bayes Theorem can be written as follows,
P(E | F) = (P(E, F) P(E)) / (P(F | E)P(E) + P(F | ~E)P(~E))

## Continuous Distribution
- Probability for continuous distributions are represented by a probability density function.
- Probability of seeing a value in a certain interval equals the integral of the density function over the interval.

Cumulative distribution function - Gives the probability that a random variable is less than or equal to a certain value

Note: A simple way of understanding this is that if a distribution has a density function f, then the probability of seeing a value between x and x+h is approximately h * f(x) if h is very small.

## Normal Distribution
- Determined by its mean and its standard deviation
- Its mean indicates where it is centered.
- Its standard deviation tells how wide it is.

```python
def normal_pdf(x, mu=0, sigma=1):
	sqrt_two_pi = math.sqrt(2 * math.pi)
	return (math.exp(-(x - mu) ** 2 / 2 / sigma ** 2) / (sqrt_two_pi * sigma))
```

If mean is 0 and standard deviation is 1, it is called a Standard Normal Distribution.
If Z is a standard normal random variable, then it turns out that:
X = standard_deviation * Z + mean is also normal


## Central Limit Theorem

Read from book
