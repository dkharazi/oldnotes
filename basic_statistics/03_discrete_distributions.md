## General Description
- A discrete distribution is a statistical distribution that shows the probabilities of outcomes with finite values
- A discrete distribution is a function that maps some finite value from the sample space to the probability space
- In other words, a discrete distribution represents the probabilities of discrete events across some pre-determined space

## Bernoulli Distribution
- The range of a bernoulli distribution is {0,1}
- A bernoulli distribution represents the probability of observing a success
- In other words, a bernoulli distribution is represented by any two-element space
- The probability of getting a one is the parameter of the distribution, which is written as either p or µ
- In other words, P(X=1)=p (or P(X=1)=µ)
- The following are examples of random variables that are represented by a bernoulli distribution:
	- A random variable that maps values to either heads or tails
	- A random variable that maps values to either rain or shine	
	- A random variable that maps values to either democrat or republican
- Bernoulli distributions are especially interesting because logistic regression assumes the observations of the response variable is a benoulli random variable

## Binomial Distribution
- A binomial distribution represents a sequence of bernoulli trials (or a bernoulli process)
- The range of a binomial distribution is [0,1]
- A binomial distribution models ths number of successes in a sample size (drawn with replacement from a population)
- Therefore, a binomial distribution is made up of parameters n and p, where n is the size of the sample and p is the probability of observing a success in the sample
- Binomial distributions are especially interesting because logistic regression assumes the response variable represents a binomial random variable

## Poisson Distribution
- A poisson distribution expresses the probability of a given number of events occurring in a fixed interval of time or space if these events occur with a known constant rate (and independently of the time since the last event)
- Poisson distributions are made up by a single parameter ƛ, which represents the expected number of occurrences (doesn't need to be an integer)
- Poisson distributions are especially interesting because they are used in GLMs to model rates
- Essentially, the poisson distribution is popular for modelling the number of times an event occurs in an interval of time or space
- The following are examples of random variables that are represented by a poisson distribution:
	- The number of meteorites greater than 1 meter diameter that strike Earth in a year
	- The number of patients arriving in an emergency room between 10 and 11 pm
	- The number of photons hitting a detector in a particular time interval

## References
- http://bactra.org/prob-notes/srl.pdf
- https://en.wikipedia.org/wiki/Poisson_distribution
