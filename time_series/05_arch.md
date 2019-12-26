## General Description
- An autoregressive conditionally heteroscedastic (ARCH) model is a time series model of variance
- In other words, an ARCH model is used to model the conditional variance when the conditional variance follows a pattern
- On the other hand, an ARMA model is used to model the conditional mean when the conditional mean follows a pattern
- Said another way, ARCH models are used to describe a changing, possibly volatile variance
- Although an ARCH model could possibly be used to describe a gradually increasing variance over time, most often it is used in situations in which there may be short periods of increased variation
- Essentially, an ARCH model could be used for any series that has periods of increased or decreased variance

## Representing the ARCH Model
- We can model any trending volatility by adjusting how we model the errors
- Specifically, the ARCH(1) model represents errors terms as the following: εᵢ = ωᵢ + sqrt(α₀ + α₁εᵢ₋₁²)
	- Where ωᵢ is a white noise term representing some random, unpredictable component
	- Where εᵢ represents the volatility in the current time period
	- Where α₀ and α₁ represent some coefficients for their respective time periods
	- Where εᵢ₋₁² represents the volatility in the previous time period
- Specifically, the ARCH(2) model represents error terms as the following: εᵢ = ωᵢ + sqrt(α₀ + α₁εᵢ₋₁² + α₂εᵢ₋₂²)
	- Where ωᵢ is a white noise term representing some random, unpredictable component
	- Where εᵢ represents the volatility in the current time period
	- Where α₀, α₁, and α₂ represent some coefficients for their respective time periods
	- Where εᵢ₋₁² represents the volatility in the previous time period
	- Where εᵢ₋₂² represents the volatility in the two previous time periods

## Testing for ARCH Models
1. Fit our best possible ARCH model
2. Consider how the model fits against the residuals graphically
3. Create a correlogram to to choose the best number of lags to include in the ARCH model
	- A correlogram is an autocorrelation plot

## References
- https://www.youtube.com/watch?v=Li95a2biFCU
- https://www.fsb.miamioh.edu/lij14/672_2014_s5.pdf
- https://newonlinecourses.science.psu.edu/stat510/lesson/11/11.1
