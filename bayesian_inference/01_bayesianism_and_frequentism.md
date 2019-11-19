## Bayesian Inference
- Bayesian Inference typically involves parameter and density estimation using probabalistic methods, such as Monte Carlo methods, Markov chains, or MCMC algorithms
- Uses Bayes Theorem at a very broad level when calculating posterior probabilities: P(H|D)∝P(H)P(D|H)
	- Where P(H|D) is the posterior distribution, which is a combination of the data for some parameter and our prior beliefs
	- And P(H) is the prior distribution, which represents our belief about the parameter
	- And P(D|H) is the likelihood distribution, which represents the data
- Includes an element of subjectivity, otherwise known as a prior belief, built into probabilities
- The data is fixed, and parameters are considered to be random variables
	- In other words, Bayesians think of a distribution as describing our beliefs about a parameter

## Semi-Bayesian Inference
- MAP estimation involves optimization (of parameters), whereas MCMC is a sampling method (of the posterior distribution of parameters)
	- This is because MAP estimates are point estimates, whereas Bayesian methods are characterized by the use of distributions to summarize data and draw inferences
	- Thus, Bayesian methods tend to report the posterior mean or median along with credible intervals
- MAP estimates can be computed using conjugate priors
	- However, the posterior, prior, or likelihood distributions will rarely have a closed-form (pdf) function
	- In this case, we would turn to MCMC techniques instead of MAP estimates

## Bayesian vs. Frequentist Inference
- Essentially, frequentists are concerned with uncertainty in the data, whereas Bayesians are concerned with uncertainty in the parameters
- Frequentists believe:
	1. Probability is thought of in terms of frequencies 
		- i.e. the probability of the event is the amount of times it happened over the total amount of times it could have happened
	2. Observed data is considered to be random variables, and the parameters are fixed values
		- i.e. the data is represented using distributions
- Bayesians believe:
	1. Probability is belief or certainty about an event
		- This belief exists because of the use of priors in Bayesian Inference
		- If the prior is a uniform distribution, then the bayesian probabilities be the same as frequentist probabilities for some parameter
	2. Observed data is considered fixed values, but the model parameters are random variables
		- i.e. the parameters are represented using distributions

## Advantages Bayesian Inference
1. Able to insert prior knowledge (priors) when there is a lack of data
	- These priors will typically become irrelevant when the data better reflects the population
	- This can happen when there is a small sample size or large sample size
	- However, there is typically a smaller chance of having data reflecting the population when we have a small sample size, in comparison to when we have a large sample size
2. Able to include an added level of uncertainty or randomness in estimates
	- This can arguably better reflect the randomness that occurs in real world observations

## Different Methods of Inference
- Example of Bayesian statistics: MCMC simulation
- Example of Frequentist statistics: ML estimation
- Example of Semi-Bayesian statistics: MAP estimation

## Relevance of MCMC in Dynamics 
- The likelihood distribution represents the transition matrix
	- As a reminder, the transition matrix is a frequency matrix of the distinct current states (columns) and previous states (rows)
	- As we increase the iterations of the transition matrix, the probabilities will eventually converge
- The prior distribution represents the state vector
	- We are able to insert our own weights to filter any probabilities given by the transition matrix
- The posterior distribution represents the steady-state vector
	- We are able to receive our converged distribution if we take many samples

## References
- https://www.sciencedirect.com/topics/computer-science/posterior-probability
- https://stats.stackexchange.com/questions/2272/whats-the-difference-between-a-confidence-interval-and-a-credible-interval/2287#2287
- https://stats.stackexchange.com/questions/22/bayesian-and-frequentist-reasoning-in-plain-english
- https://frnsys.com/ai_notes/foundations/bayesian_statistics.html
- https://stats.stackexchange.com/questions/200982/do-bayesian-priors-become-irrelevant-with-large-sample-size
- http://www.svcl.ucsd.edu/courses/ece271A/handouts/BayesIntro.pdf
