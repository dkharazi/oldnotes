## General Description
- Local regression is a generalization of moving average and polynomial regression
- The most common method of local regression is loess (locally estimated scatterplot smoothing)
- Local regression is used for fitting non-linear functions
- Local regression involves computing a fit for each data point using only nearby training observations (i.e. performing a moving average-like computation when fitting the model)
- Specifically, we need to fit a new weighted least squares regression model in order to obtain the local regression fit at each new point

## The Algorithm
1. Gather the fraction s = k/n (i.e. span) of training points whose xi are closest to x0
	- In other words, we determine the training observations considered in our local regression fit (at each point) by choosing a reasonable fraction of data points closest to our point we're fitting on
	- The span plays a role like that of the tuning parameter λ in smoothing splines
	- Specifically, it controls the flexibility of the non-linear fit
	- More specifically, a smaller value of s will lead to a more local (or wiggly) fit to the data, and a larger value of s will lead to a global (or linear) fit to the data (i.e. using all of the training observations)
2. Assign a weight Ki0 = K(xi, x0) to each point in this neighborhood, so that the point furthest from x0 has weight zero, and the closest has the highest weight
	- In other words, we assign high weights to each training point closest to our training point we're fitting on, and we assign very small weights to each training point furthest from our training point we're fitting on
	- We only assign weights to points within our fraction of training observations we're considering
	- Any training point will be assigned a weight of zero if it is either outside of our fraction of observations or extremely far away from the point we are fitting on
3. Fit a weighted least squares regression of the yi on the xi using the aforementioned weights, by finding the beta-coefficients that minimize the following equation: ΣKi0(yi - βp*xip)²
	- In other words, estimate the beta-coefficients by minimizing the weighted least squares cost function

## Additional Notes about the Algorithm
- In order to perform local regression, the following choices need to be made: 
	1. What fraction of closest training observations should we include in our group of observations (i.e. step one)
	2. What should we choose for our weighting functions K (i.e. step 2)
	3. Do we fit a linear, constant, or quadratic regression model (i.e. step 3)
- The most important choice is the span s, defined in step 1


## References
- http://faculty.marshall.usc.edu/gareth-james/ISL/ISLR%20Seventh%20Printing.pdf
- http://www.stat.cmu.edu/~larry/=sml/nonpar.pdf
- https://www.youtube.com/watch?v=Vf7oJ6z2LCc
