## General Description
- A SARIMA model is an ARIMA model that accounts for seasonality
- Here, seasonality just refers to a repeating pattern within a year (i.e. can't be a two-year pattern)
- A SARIMA model is defined as ARIMA(p,d,q)(P,D,Q)m
	- Where p refers to the order of the autoregressive portion of the ARIMA model
	- Where d refers to the order of the integrated portion of the ARIMA model (i.e. how many times we take a difference to get our model to be stationary)
	- Where q refers to the order of the moving average portion of the ARIMA model
	- Where m refers to the seasonal factor (i.e. the number of distinct periods within a year that make up a single seasonal pattern that is repeated over time)
	- Where P refers to the order of the autoregressive portion of the ARIMA model, with an additional seasonal component
	- Where D refers to the order of the integrated porition of the ARIMA model, with an additional seasonal component
	- Where Q refers to the order of the order of the moving average porition of the ARIMA model, with an additional seasonal component
- A SARIMA model can also be written as ARIMA(p,d,q)₁(P,D,Q)m, since we're technically backshifting parameters p, d, and q by 1 (i.e. sᵢ₊₁ - sᵢ)

## Example of SARIMA Model
- Let's say we define the following SARIMA model: ARIMA(1,0,0)(0,1,1)₄
- The p parameter with a value equal to 1 can be translated to (1-ɸ₁B¹)yᵢ
	- Where B¹yᵢ is our lag operator representing yᵢ₋₁
	- Where ɸ₁ is the slope of our variable yᵢ₋₁
	- Therefore, (1-ɸ₁B¹)yᵢ is just shorthand for yᵢ-ɸ₁yᵢ₋₁
- The D parameter with a value equal to 1 can be translated to (1-B⁴)yᵢ
	- Where B⁴yᵢ is our lag operator representing yᵢ₋₄
	- Therefore, (1-B⁴)yᵢ is just shorthand for z = yᵢ-yᵢ₋₄
- The Q parameter with a value equal to 1 can be translated to (1+Θ₁B⁴)𝜀ᵢ
	- Where B⁴𝜀ᵢ is our lag operator representing 𝜀ᵢ₋₄
	- Where 𝜀ᵢ₋₄ is the error of the fourth previous predicted value and what we observed
	- Where θ₁ represents the percentage of the error 𝜀ᵢ₋₄ we should include in our model
	- Therefore, (1-Θ₁B⁴)𝜀ᵢ is just shorthand for 𝜀ᵢ+Θ₁𝜀ᵢ₋₄
- We can continue to simplify our SARIMA model to the following formulas:
	1. (1-ɸ₁B¹)(1-B⁴)yᵢ = (1+Θ₁B⁴)𝜀ᵢ
	2. (1-ɸ₁B¹-B⁴+ɸ₁B⁵)yᵢ = 𝜀ᵢ+Θ₁𝜀ᵢ₋₄
	3. yᵢ - ɸ₁yᵢ₋₁ - yᵢ₋₄ + ɸ₁yᵢ₋₅ = 𝜀ᵢ + Θ₁𝜀ᵢ₋₄
	4. yᵢ - yᵢ₋₄ = ɸ₁yᵢ₋₁ - ɸ₁yᵢ₋₅ + Θ₁𝜀ᵢ₋₄ + 𝜀ᵢ
	5. zᵢ = ɸ₁zᵢ₋₁ + Θ₁𝜀ᵢ₋₄ + 𝜀ᵢ (since z = yᵢ-yᵢ₋₄ based on parameter D)
- Now, we've transformed our ARIMA model to account for seasonality by taking differences yᵢ - yᵢ₋₄, which will lead to a more stationary model

## References
- https://www.youtube.com/watch?v=WjeGUs6mzXg
- https://www.analyticsvidhya.com/blog/2015/12/complete-tutorial-time-series-modeling/
