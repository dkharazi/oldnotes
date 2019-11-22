## General Description
- Regression is a statistical technique for estimating the relationship among a continuous response variable and a set of predictor variables
- Linear regression is a type of regression that models a linear relationship among a continuous response variable and its predictor variables
- In other words, linear regression assumes a constant rate of change between a response variable and its predictor variables
- The most common approach for estimating the population parameters involved in the linear regression model is the method of least squares
	- There are other ways of estimating the population parameters, such as maximum likelihood estimation (MLE)
- Roughly speaking, residuals are the realizations (or observations) of the random variable ε (or the error term)

## Model Components
- The response variable equals the true mean plus some noise
	- Mathematically written as Y = β0 + β1X + ε
	- In a frequentist framework, the response variable, the predictor variables, and the error term are all random variables
	- In a frequentist framework, the β0 and β1 coefficients are our population parameters
		- As stated previously, we estimated the population parameters using either the least squares criterion or maximum likelihood estimation
- The response variable conditioned on the predictor variables is normally distributed
	- Mathematically written as Y|X ~ N(β0+β1x, σ²)
	- E[Y|X] = β0 + β1x
	- Var[Y|X] = σ²
- The error term conditioned on the predictor variables is normally distributed
	- Mathematically written as ε|X ~ N(0, σ²)
	- E[ε|X] = 0
        - Var[ε|X] = σ²

## Assumptions of Linear Regression
1. The distribution of any predictor variable is unspecified (possibly even deterministic)
2. The relationship between the response variable and predictor variables is linear (i.e. represented by Y|X = β0 + β1X + ε)
3. The error term is normally distributed with a mean of 0 and constant variance for all values of X (i.e. ε|X~N(0,σ²)
	- Which implies the error term is uncorrelated across observations and is uncorrelated with predictors
	- In other words, this implies ε is independent of observations, and ε is independent of the predictor variables
	- Said another way, homoscedasticity is maintained (i.e. constant variance)
	- Mathematically, E[ε|X=x]=0 and Var[ε|X=x]=σ²

## Properties of Linear Models
- The predictor variables do not need to be normally distributed
- The reponse variable does not need to be normally distributed
- The response variable conditional on the predictor variables needs to be normally distributed

## Properties of Residuals
1. The residuals should have an expected value of zero (i.e. E[e|X=x]=0)
2. The residuals should show a nearly constant variance (i.e. Var[e|X=x]=σ²)
3. The residuals can't be completely uncorrelated with each other, but the correlation should be extremely weak (and grow negligable as n→∞)
4. The residuals should be Gaussian (since the errors should be Gaussian)

## References
- https://www.stat.cmu.edu/~cshalizi/mreg/15/lectures/04/lecture-04.pdf
- http://www.stat.cmu.edu/~cshalizi/TALR/TALR.pdf
- http://faculty.marshall.usc.edu/gareth-james/ISL/ISLR%20Seventh%20Printing.pdf
- https://ocw.mit.edu/courses/mathematics/18-655-mathematical-statistics-spring-2016/lecture-notes/MIT18_655S16_LecNote19.pdf
