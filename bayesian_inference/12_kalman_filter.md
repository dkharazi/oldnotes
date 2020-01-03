## General Description
- The Kalman Filter is an iterative mathematical algorithm, not a model
- A Kalman filter is an optimal estimator that infers parameters of interest from indirect, inaccurate, and uncertain observations
- It is recursive, so new measurements can be processed as they arrive
- If all noise is Gaussian, then the Kalman filter minimizes the MSE of the estimated parameters
- The Kalman filter is a powerful algorithm to use for "nowcasting"
- Nowcasting refers to forecasting without having current predictor values on hand
- Therefore, we would need to estimate our predictor values

## Use-Cases of Kalman Filter
- Provides good results in practice due to optimality and structure
- Convenient form for online real-time processing
- Easy to formulate and implement given a basic understanding
- Measurement equations don't need to be inverted

## What is a Filter
- A filter refers to the process "filtering out" the noise when we're trying to find some best parameter estimate from noisy data
- A Kalman filter cleans up the data measurements to try to account for the noise, and also projects these measurements onto the estimated state

## The Kalman Filter Algorithm
- The Kalman filter can be defined as the following: yᵢ = Hxᵢ + 𝜀ᵢ (where xᵢ = Axᵢ₋₁ + ɸᵢ)
- We can see that there are two parts of the algorithm:
	1. The update portion of the algorithm (i.e. xᵢ = Axᵢ₋₁ + ɸᵢ)
	2. The prediction portion of the algorithm (i.e. yᵢ = Hxᵢ + 𝜀ᵢ)
- The update portion of the algorithm can be defined as the following: xᵢ = Axᵢ₋₁ + ɸᵢ
	- Where xᵢ is our hidden variable and represents our estimated predictor variable (i.e current predicted value of x)
	- Where xᵢ₋₁ represents the previous predicted value of x
	- Where A represents the state transition matrix
		- These could be made up of the beta coefficients for a linear regression model, or the autoregressive coefficients in an AR (or ARIMA) model, etc.
	- Where ɸᵢ represents the error term for xᵢ
- The prediction portion of the algorithm can be defined as the following: yᵢ = Hxᵢ + 𝜀ᵢ
	- Where yᵢ represents our estimated response variable (i.e. current predicted value of y)
	- Where xᵢ refers to our hidden variable and represents our estimated precitor variable
	- Where H represents the state transition matrix
		- These could be made up of the beta coefficients for a linear regression model, or the autoregressive coefficients in an AR (or ARIMA) model, etc.
	- Where 𝜀ᵢ represents the error term for yᵢ

## Advantages of the Kalman Filter
- The Kalman filter is predictive and adaptive, since it looks forward with an estimate of the covariance and mean of the time series of one step into the future
- The Kalman filter does not require stationary data (neural networks usually do)
- It has a smooth representation of the series, while not requiring knowledge of the future
- A potential disadvantage of the Kalman filter is that it typically assumes linearity

## References
- http://bilgin.esme.org/BitsAndBytes/KalmanFilterforDummies
- https://www.r-bloggers.com/the-kalman-filter-for-financial-time-series/
- http://www.cs.cmu.edu/~guestrin/Class/10701-S05/slides/hmms.pdf
- https://www.youtube.com/watch?v=CaCcOwJPytQ
- https://faculty.washington.edu/ezivot/econ584/notes/statespacemodels.pdf
- http://biorobotics.ri.cmu.edu/papers/sbp_papers/integrated3/kleeman_kalman_basics.pdf
