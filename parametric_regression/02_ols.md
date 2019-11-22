## General Description
- The ordinary least squares criterion is a method for estimating regression coefficients (or population parameters)
- The least squares criterion involves minimizing the sum of squares of the residuals (RSS)
- In other words, the least squares criterion chooses coefficient estimates, such as β-hats, that minimize the RSS
- Using the least squares approach to find the population parameters, we can use some calculus to find equations for the coefficient estimates that minimize the residual sum of squares
- For example, we can use calculus to find the following coefficient estimates:
	- βhat1 = (Σ(xi-xbar)(yi-ybar))/(Σxi-xbar)
	- βhat0 = ybar - βhat1*xbar

## Residual Sum of Squares
- The residual sum of squares is defined as the sum of the squared residuals
- Mathematically, we write the equation for the residual sum of squares as the following: RSS = e1²+e2²+e3²+...+en²
- Equivalently, we can write the equation as RSS = [y1-f(x1)]²+[y2-f(x2)]²+[y3-f(x3)]²+...+[yn-f(xn)]²
- Or, we can write the equation as RSS = [y1-βhat0-βhat1*x1]²+[y2-βhat0-βhat1*x2]²+[y3-βhat0-βhat1*x3]²+...+[yn-βhat0-βhat1*xn]²

## Population Regression Line
- The least squares regression line is the linear regression line represented by our coefficient estimates
	- For example, Y = βhat0 + βhat1*X
- The population regression line is the linear regression line represented by our population parameters
	- For example, Y = β0 + β1*X
- The least squares regression line is our "best guess" at representing the population regression line, assuming the true relationship is linear

## MLE versus OLS
- Minimizing the squared error is equivalent to maximizing the likelihood when the errors are normally distributed (i.e. in the case of linear regression)
	- Refer to the top response on the stackoverflow post for a proof
- We can use MLE for predicting y values in linear regression, even if the response variable has an arbitrary distribution (rather than the normal distribution)
- For example, our response variable could have a Bernoulli distribution, exponential distribution, etc.
- In this case, we would map the linear predictor to the non-normal distribution of the response variable using a link function
- Then, the likelihood function becomes the product of all the outcomes (i.e. probabilities between 0 and 1) after the transformation of the predictor variables

## References
- http://faculty.marshall.usc.edu/gareth-james/ISL/ISLR%20Seventh%20Printing.pdf
- https://stats.stackexchange.com/questions/143705/maximum-likelihood-method-vs-least-squares-method
