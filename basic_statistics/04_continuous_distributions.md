## General Description
- For continuous random variables, the probability of observing a single event will always equal 0
- We can use a cumulative distribution function (cdf) to consider a small interval of probabilities around a certain event in order to approximately measure an event
- However, this approach will not always lead to consistent or accurate probability calculations, since our probabilities will be based on the statistician's subjective interval each time
- Roughly speaking, we want to have a pre-determined function that returns some (very small) binned interval of probabilities around the point of interest
- The probability density function is the function that achieves our goal

## Probability Density Function (pdf)
- A probability density function is a function that maps a continuous value in the sample space to a "relative likelihood" of observing that value
- Each type of random variable has its own distinct probability density function
- We can use a probability density function to calculate probabilities of observing an interval of events (using the cumulative distribution function)
- We can also use a probability density function to calculate the density (or likelihood) of observing a single event for some continuous random variable
- Roughly speaking, a density is a value that conceptually represents the binned probability of observing a single event of a continuous random variable
- Specifically, a density refers to the derivative of an extremely small interval of events around our point of interest, which tells us how much probability there is in the neighborhood of our point of interest

## Gaussian Distribution
- The guassian distribution is also known as the normal distribution
- This is the single most important distribution in probability theory, owing to the Central Limit Theorem
- If we have a normally distributed random variable, we can input observations into its probability density function and receive densities as output
- The gaussian distribution is represented by parameters µ and σ², where µ is the mean and σ² is the variance

## References
- http://bactra.org/prob-notes/srl.pdf
- https://en.wikipedia.org/wiki/Probability_distribution
