## Model Description
- MCMC methods are used to approximate the posterior distribution of a parameter of interest by random sampling in a probabilistic space
	- The posterior distribution can be thought of as a kind of average of the prior and likelihood distributions
- We can determine a posterior distribution by:
	1. Using conjugate distributions (i.e. conjugate prior)
		- The prior and likelihood distributions rarely match up perfectly, so we usually aren't able to work with conjugate distributions
		- If we are lucky, we can use these and simply multiply the closed-form functions (prior and likelihood) by each other
	2. Using MCMC sampling
		- If the posterior, likelihood, or prior distributions become more complicated and do not follow a closed-form function, then we cannot solve for these analytically and will need use MCMC sampling

## How Monte Carlo Simulations relate to MCMC
- Monte Carlo simulations generally refer to taking samples from a population to simulate the population distribution
- In many cases, we can use Monte Carlo simulations to approximate the area under curves when integration doesn't have a closed-form solution
- Within the MCMC algorithm, random parameter values are simulated and either accepted or rejected as the new parameter value at each iteration
- In the scope of the MCMC algorithm, the process of generating new random parameter values for many iterations is known as Monte Carlo simulations

## How Markov Chains relate to MCMC
- A Markov Chain generally refers to a model that only uses the current state to predict the next event
	- Specifically, the model contains an independent variable that represents some current observation, and a dependent variable that represents the previous observation
	- This is referred to as the Markov Property, or memorylessness
- Within the MCMC algorithm, we determine how much better a randomly-generated parameter value is to the previous parameter value, and we add the randomly-generated parameter value to the chain if it is considered better
- In the scope of the MCMC algorithm, the Markov Chain refers to the following features:
	- Only referring to the previous parameter value when evaluating if the randomly-generated parameter value is better or not
	- Adding any "better" values to a chain of parameter values

## General Description of the MCMC algorithm
1. Generate a random parameter value to consider, and continue to generate random parameter values for many iterations (this is the Monte Carlo part)
2. Compute the posterior (joint) probability of observing the pair of randomly-generated parameter values by combining the prior and lilelihood distributions (this is the Bayes theorem part)
	- More specifically, the likelihood equals the joint probability of observing the parameter of interest given the data
	- And the prior equals the joint probability of observing the parameters together
	- Example: We want to estimate the conditional mean μ, which is represented by some posterior distribution μ~Posterior(mu,sd|X)
		- We know that X represents our predictor data, Y represents our response data, and mu = β0+β1*X
		- So, we can rewrite the representation of the posterior distribution as μ~Posterior(β0,β1,σ|X)
		- We know that our likelihood equals the joint probability (or likelihood) of observing the data given the parameters β0, β1, and σ
			- Therefore, P(X|β0,β1,σ) = dnorm(data=y_1,mean=β0+β1*x_1,sd=σ) * dnorm(data=y_2,mean=β0+β1*x_2,sd=σ) * ... * dnorm(data=y_n,mean=β0+β1*x_n,sd=σ)
		- We know that our prior equals the joint probability (or likelihood) of observing the parameters β0, β1, and σ
			- Therefore, P(β0,β1,σ) = dnorm(data=β0,mean=**some mean we decide**, sd=**some sd we decide**) * dnorm(data=β1,mean=**some mean we decide**, sd=**some sd we decide**) * dnorm(data=σ,mean=**some mean we decide**, sd=**some sd we decide**)
3. Determine if the randomly-generated parameter value is better than the previous better value (this is the Metropolis-Hastings part, or some other method for evaluation)
4. If the pair of randomly-generated parameter values is better than the last one, then it is added to the chain of parameter values (this is the Markov chain part)

## References
- https://towardsdatascience.com/a-zero-math-introduction-to-markov-chain-monte-carlo-methods-dcba889e0c50
- https://towardsdatascience.com/markov-chain-monte-carlo-291d8a5975ae
- https://nicercode.github.io/guides/mcmc/
- https://theoreticalecology.wordpress.com/2010/09/17/metropolis-hastings-mcmc-in-r/
- https://www.stat.cmu.edu/~cshalizi/statcomp/13/lectures/16/lecture-16.pdf
