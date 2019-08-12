## Error and Bias
- Bias and variance typically refer to the errors associated with an estimator
- Irreducible error typically refers to the error provided by a (population) random variable
	- Error is a property of a random variable

## Properties of Estimators
- Biasedness
	- An estimator is unbiased if the expected value of the error term is 0
	- Relates to bias in the bias-variance tradeoff concept
	- An unbiased estimator can be a good indication that we will receive a low training error in the bias-variance tradeoff
- Consistency
	- An estimator is consistent if our parameter estimate converges to the true parameter as n → ∞
	- Relates to variance in the bias-variance tradeoff concept
	- A consistent estimator can be a good indication that we will receive a low variance in the bias-variance tradeoff

## Bias-Variance Tradeoff
1. Bias
        - Bias of an estimator is associated with training error
        - High training error/bias leads to underfitting
        - Bias is caused by systematic or statistical errors
        - Specific sources of bias include:
                - A lack of training data (sampling error of the training set)
                - Too few features in our training data
                - Flaws in the model
                        - Example: we may need to train the data on a more complicated model or an entirely different model altogether
                - Flaws in the modeling process
                        - Example: we may not be using the proper equations correctly
                        - Example: we may need to decrease regularization
                        - Example: misunderstanding of bayesian modeling algorithms and hyper-parameter fitting
                - Flaws in the measurement instrument
                - Flaws in the measurement process
                - Flaws in determing the best way to measure some variable of interest
                        - Example: we may correctly measure some imperfect proxy for what we're really interested in, but will still receive poor accuracies, since we are measuring an imperfect proxy to begin with
2. Variance
        - Variance of an estimator is associated with testing/cross-validation error
        - High testing error/variance leads to overfitting
        - Variance is caused by overall sampling error or mistaking noise for signal during the training portion of our modeling process
        - Specific sources of variance include:
                - A lack of testing/overall data (overall sampling error)
                - Too many features in our training data
                - Flaws in the model
                        - Example: we may need to train the data on a less complicated model or an entirely different model altogether
                - Flaws in the modeling process
                        - Example: we may need to increase regularization
3. Irreducible Error
	- Irreducible error is also referred to as error for short (or random error, noise, the error term, or ε)
        - Irreducible error represents inherent randomness caused by natural variability in the random variable
                - This natural variability is a result of not knowing every variable and its true relationship with every other random variables in the world
        - A certain level of irreducible error will always exist, and is even incorporated in (population) random variables
		- I.e. Y = βiXi + εi
        - Random error (or noise) is thought of as a random variable itself, with a mean of 0
        - The error term is mathematically defined as εi = Yi − (β0 + β1*xi)
        - Irreducible error represents the standard deviation of the random error term (ε)
                - It wouldn't make any sense for the irreducible error to be the error term, since the irreducible error is a fixed number representing uncertainty, rather than a random variable, which is a function

## References
- http://scott.fortmann-roe.com/docs/BiasVariance.html
- http://www.stat.cmu.edu/~cshalizi/TALR/TALR.pdf
- https://www.learnopencv.com/bias-variance-tradeoff-in-machine-learning/
