## General Description
- A Hidden Markov Model (HMM) is a probabilistic model
- An HMM is a probabilistic model that allows us to predict a sequence of unknown (hidden) variables from a set of observed variables
- We use HMMs to calculate the posterior (conditional) probability of observing a sequence of hidden states (given some additional information provided by other observed states/variables)
- Since we can use HMMs to calculate the posterior (conditional) probability of observing a sequence of hidden states, we can also use HMMs to calculate the most likely hidden state given observed states
- In other words, we can use MLE to find the most probable (unknown) hidden state given an observed state
- An HMM requires two sets of observations indexed by time, where one set of observations is associated with the observed states and the other set of observations is associated with the hidden states
- A simple example of an HMM is predicting the weather (hidden variable) based on the type of clothes that someone wears (observed)

## Components of HMM
- A set of hidden states
- A set of observed states
- A state transition matrix
	- Represents the conditional probabilities of observing a hidden state given the current hidden state
- An output emission matrix
	- Represents the joint probabilities of observing an observed state and a hidden state at the same time
- A prior matrix
	- Represents the subjective, marginal probabilities of observing an observed state

## Example of HMM
- A set of hidden states: weather
- A set of observed states: clothing worn
- A state transition matrix: P(Hot|Hot yesterday), P(Cold|Cold yesterday), P(Hot|Cold yesterday), P(Cold|Hot yesterday), etc.
- An output emission matrix: P(Hot,Shorts), P(Hot,Jeans), P(Cold,Shorts), P(Cold,Jeans), etc.
- A prior matrix: P(Hot), P(Cold), etc.

## The General Algorithm
1. Calculate the joint probabilities of observing hidden states (e.g. sunny, cloudy, etc.) and observed state (e.g. jeans, shorts, etc.)
2. Calculate the conditional probabilities of observing hidden states given its previous hidden state
3. Calculate the prior probabilities of observing the hidden states
4. Calculate the posterior probability of observing a sequence of hidden states given a sequence of observed states using Bayes theorem (i.e. Bayesian statistics)
	- For example, Posterior = Prior * Likelihood, i.e. P({Hot,Hot}|{Jeans,Shorts}) = P(Hot) * (P(Jeans|Hot)*P(Shorts|Hot)*P(Hot|Hot))
4. Or we can calculate each posterior probability of observing a sequence of hidden states given a sequence of observed states, then use MLE to find the most probable hidden state given the specified observed states
	- For example, we can calculate 4 posterior probabilities, i.e. Posterior1 = P({Hot,Hot}|{Jeans,Shorts}), Posterior2 = P({Hot,Cold}|{Jeans,Shorts}), Posterior3 = P({Cold,Hot}|{Jeans,Shorts}), Posterior4 - P({Cold,Cold}|{Jeans,Shorts})
	- Then, we can guess the hidden states are {Hot,Cold} when the observed states are {Jeans,Shorts}, since Posterior2 has the highest probability out of the four posterior probabilities (i.e. Posterior1, Posterior2, Posterior3, Posterior4)

## Difference between Markov Models and HMMs
- An HMM involves the use of a markov model on its hidden states (not on the observed states)
- A HMM is essentially a markov model with some additional information provided by other observed states (or variables)
- We use HMMs over plain markov models when we possess additional observed data that seems to be associated (or correlated) with the data we are trying to classify (i.e. hidden states)

## References
- https://medium.com/@postsanjay/hidden-markov-models-simplified-c3f58728caab
- https://www.mathworks.com/matlabcentral/fileexchange/70226-bayes-estimator-best-must-have-tattoo/?s_tid=LandingPageTabfx
- https://www.reddit.com/r/explainlikeimfive/comments/1iyl5v/eli5_what_is_a_hidden_markov_model_and_how_does/
- https://stackoverflow.com/questions/10748426/what-is-the-difference-between-markov-chains-and-hidden-markov-model
- https://en.wikipedia.org/wiki/Hidden_Markov_model
- http://www.cs.cmu.edu/~tbergkir/11711fa17/recitation4_notes.pdf
