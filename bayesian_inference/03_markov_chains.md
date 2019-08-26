## Notation within Statistical Mechanics
- A state refers to a unique observation of some system
- A system refers to a collection of random variables, which includes the future state i and current state j
	- The states i and j are essentially thought of as independent and dependent random variables, respectively

## Markov Process
- A Markov process is a stochastic process that has the following properties:
	- The number of distinct possible outcomes (or states) is finite
	- Supports the Markov Property or "memorylessness"
		- The outcome of a random variable depends only on the previously observed outcome of that random variable
	- The probabilities (associated with each transition between other state) are constant over time
- Since we assume independence of any previous observations, we can consider the conditional probabilities of each state to be fixed
	- Specifically, the next state is only conditional on the present state of the system, since its past states are considered to be independent of the next state
	- Said another way, the next observation is only conditional on the current observation of a random variable, since its past observations are considered to be independent of the next observation 
- The Markov Property doesn't usually apply to systems within the real world, so we wouldn't expect our predictions to be very accurate
	- However, running the Markov chain for thousands of iterations typically provides us with a good long-run prediction

## Example of a Markov Process using Weather
- Let's assume that on a given day it is more likely to rain if it rained the day before than if it didn't, and likewise it is more likely to be sunny if it was sunny the day before
- If we can express the probability of it raining on Tuesday as a function of the weather on Monday (without taking Sunday into account), that means that even though every day might be dependant on everything that preceded it (in fact it does, since the weather on Monday doesn't actually affect the weather on Tuesday, rather they both stem from the quite complex meteorological conditions, and those don't tend to just shift in unexpected directions), in practice we can consider only a small amount of data when predicting the weather (instead of processing the whole history of the area for every day)

## Basic Theory of Markov Chains
- A Markov Chain is a probabilistic model of a stochastic process
- Every Markov Chain can be represented using a transition matrix, a state vector, and a steady-state vector
- The "Markov" part refers to the model's use of the Markov property
	- Specifically, the transition matrix is usable only because of the Markov property
- The "Chain" part refers to running many iterations of the model by re-inputting the previous model's output over and over again
	- Specifically, we input an initial state vector, receive some output from the model (by multiplying the transition matrix and the state vector together), and re-input the output over and over again until the state vector converges, which we call our steady-state vector
	- Mathematically, we keep running the model until Mx_s = x_s, or in other words until the input equals the output, i.e. the state vector equals the steady-state vector
- The goal of a Markov Chain is to keep iterating until we receive a steady-state vector that converges

## Definiton of Markov Chains
- Rows represent the "from" or "current" state
        - The rows sum up to a probability of 1
- Columns represent the "to" or "next" state
        - The columns do not sum up to 1, since they are conditional probabilities and not joint probabilities
- A transition matrix represents the conditional probabilities of some observation given the previous observation
        - This is based on a large amount of historical data
- The state vector represents the probabilities of some current observation that you want to better understand
        - This is based on the probability that the system (or random variable) is in a state "k" at a given time
        - This is used as input
- The steady-state vector represents the converged output of multiplying the transition matrix and the initial state vector over time
        - This represents the output after very many iterations, since the state vector will eventually converge after very many iterations

## Mathematical Definition of Markov Chains
- Discrete-valued, discrete-time stochastic processes
        - A discrete-valued, discrete-time is a stochastic process
        - Mathematically, a discrete-valued, discrete-time stochastic process has the Markov property when P(Sn+1 = sn+1|Sn = sn) = P(Sn+1 = sn+1|Sn = sn, Sn−1 = sn−1, ...S1 = sn) for all si and for all n
        - That is, the probability distribution for the next state depends solely on the current state
        - We then say that Sn is a Markov process.
- The analogous condition for continuous time is P(S(tn+1) = sn+1|S(tn) = sn) = P(S(tn+1) = sn+1|S(tn) = sn, S(tn−1) = sn−1, . . . S(t1) = s1) for all values si and any increasing sequence of times ti

## Example: Markov Chain in relation to Weather
- A Markov Chain with a State Space S={Sunny, Rainy} has a transition matrix:
	- P=[    S   R ]
	    [S  .9  .1 ]
	    [R  .5  .5 ]
- Say we wanted to calculate the probability of the weather in two days from today being sunny, and we know that the weather today is sunny:
	- We need to calculate P(1st day is sunny->sunny and 2nd day is sunny->sunny) = 0.9*0.9 = 0.81
	- We need to calculate P(1st day is sunny->rainy and 2nd day is rainy->sunny) = 0.1*0.5 = 0.05
	- Then P(Sunny 2 days from now) = 0.9*0.9 + 0.1*0.5 = 0.81*0.05 = 0.86
- Mathematically, we could write the above situation as:
	- Let an event A={SS,SR,RS,RR} represent a set of possible weather transitions from one day to another
		- Where SS = a day of sunny weather where the previous day was also sunny
		- Where SR = a day of rainy weather where the previous day was sunny
		- Where RS = a day of sunny weather where the previous day was rainy
		- Where RR = a day of rainy weather where the previous day was also rainy
	- Calculate the probability P(SS,SS)
	- Calculate the probability P(SR,RS)
	- Calculate the probability P(Second day is sunny) = P(SS,SS) + P(SR,RS)

## Example of a Markov Chain in relation to the Stock Market

## Example of a Markov Chain in relation to a Random Walk

## Why use a Markov Chain
- If we use a Markov Chain, we don't need to keep track of a bunch of dependent variables with respect to some independent variable
- Instead, we only need to keep track of the history of one independent variable (and the index, which is typically a date)
	- Then, we can calculate the conditional probabilities for each state (or unique observation) given its previous state (or previous observation)

## References
- http://bactra.org/prob-notes/srl.pdf
- https://medium.com/@rohitpandey576/coin-toss-markov-chains-7995cb303406
- https://people.math.osu.edu/husen.1/teaching/571/markov_1.pdf
- http://setosa.io/blog/2014/07/26/markov-chains/
- https://en.wikipedia.org/wiki/Markov_chain
- http://people.brunel.ac.uk/~mastjjb/jeb/or/moremk.html
- https://www.math.drexel.edu/~jwd25/LM_SPRING_07/lectures/Markov.html
- https://stats.stackexchange.com/questions/165/how-would-you-explain-markov-chain-monte-carlo-mcmc-to-a-layperson 
