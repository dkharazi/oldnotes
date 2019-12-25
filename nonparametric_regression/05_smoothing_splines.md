## Motivation
- We create a regression splines by specifying a set of knots, producting a sequence of basis functions (constraints), and then using least squares to estimate the spline coefficients
- Smoothing splines are created using a different approach: finding a function g that minimizes the RSS (Σy-g(x))

## General Description
- A spline is a special function defined piecewise by polynomials
- Smoothing splines are created by minimizing the RSS
- If we don't put any constraints on g(x), then we will always overfit the data by interpolating all of the data, which will always make RSS zero
- Therefore, we want to find the smoothing splines that minimize the RSS with added constraints, which will make the curve smooth
- When dealing with smoothing splines, our constraint (or penalty term) is our tuning parameter multipled by the second derivative of our function g (i.e. ƛ∫g’’(t)²dt)
- A smoothing spline is a function g that minimizes the RSS and the penalty term
- This notion of minimizing the loss function + penalty term is also found in ridge regression and lasso

## Behind the Mathematics
- The first term (i.e. loss function or RSS) encourages g to fit the data well
- The second term (i.e. penalty term) penalizes the variability in g
- Roughly speaking, the second dervative of a function is a measure of its roughness
- Minimizing the error and roughness is what we want, since we want a smooth curve that fits well
- When the tuning parameter (i.e. ƛ) equals 0, then the penalty term has no effect, and so the function g will perfectly fit the data (which causes overfitting)
- When the tuning parameter (i.e. ƛ) → ∞, then g will be perfectly smooth. and so g will just be a straight line
	- Specifically, g will be the linear least squares line
- Essentially, the tuning parameter controls the bias-variance trade-off of the smoothing spline

## Finding the Best Smoothing Spline
- The function g(x) that minimizes the smoothing spline function (i.e. loss + penalty) is a natural cubic spline with knots at each data point
- Specifically, the function g(x) that minimizes the smoothing spline is a piecewise cubic polynomial with the following:
	1. Knots at the unique values of x1,...,xn
	2. Continuous first derivative
	3. Continuous second derivative
- However, it is not the same natural cubic spline that one would get if one applied the basis function approach occurring in spline regression
- Instead, it is a shrunken version of the natural cubic spline found in spline regression, where the value of the tuning parameter in the smoothing spline function controls the level of shrinkage

## Choosing the Smoothing Parameter
- We have seen that a smoothing spline is simply a natural cubic spline with knots at every unique value of x
- It might seem that a smoothing spline will have far too many degrees of freedom, since a knot at each data point allows a great deal of flexibility
- However, the tuning parameter will control the roughness of the smoothing spline, and hence the effective degrees of freedom
- Roughly speaking, as the tuning parameter increases from 0 to ∞, the effective degrees of freedom decrease from n to 2
- Therefore, we do not need to select the number or locations of the knots, since there will be a knot at each training observation when fitting a smoothing spline
- Instead, we need to choose the value of the tuning parameter that makes the cross-validated RSS as small as possible
- The LOOCV can be computed very efficiently for smoothing splines

## References
- https://www.analyticsvidhya.com/blog/2018/03/introduction-regression-splines-python-codes/
- http://faculty.marshall.usc.edu/gareth-james/ISL/ISLR%20Seventh%20Printing.pdf
