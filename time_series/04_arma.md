## General Description
- An autoregressive moving average (ARMA) model is a model combining the autoregressive model and moving average model together
- An autoregressive model is parameterized by parameter p (i.e. AR(p)), which represents the number of lags included in the model
- A moving average model is parameterized by parameter p (i.e. MA(p)), which represents the order of lags included in the model
- Therefore, an ARMA model is parameterized by the same models taken from the autoregressive model (i.e. number or lags) and moving average model (i.e. order)
- Mathetmatically, we typically represent an ARMA function as ARMA(p, k), where p refers to the number of lags from the autoregressive model and k refers to the order from the moving average model
- Mathematically, we typically represent an ARMA model as sᵢ = β₀ + β₁sᵢ₋₁ + θ₁εᵢ₋₁ + εᵢ, and sᵢ-hat = β₀ + β₁sᵢ₋₁ + θ₁εᵢ₋₁
	- Where the AR component is represented by β₀ + β₁sᵢ₋₁
	- Where the MA component is represented by θ₁εᵢ₋₁

## Differences Between AR and MA Models
- The AR terms represent the lagged values sᵢ
- The MA terms represent the lagged errors of sᵢ (i.e. εᵢ)
- The primary difference between an AR and MA model is based on the correlation between time series objects at different time points
- Specifically, the correlation between sᵢ and sᵢ₋ᵣ for r > order of MA is always zero
- This directly flows from the fact that covariance between sᵢ and sᵢ₋ᵣ is zero for MA models
- However, the correlation of sᵢ and sᵢ₋ᵣ gradually declines with r becoming larger in the AR model
- This difference gets exploited irrespective of having the AR model or MA model
- The correlation plot can give us the order of MA model

## Examples of ARMA Model
- Let's say we build an ARMA model, such as the following: ARMA(1,1)
	- Our model would be represented as sᵢ-hat = β₀ + β₁sᵢ₋₁ + θ₁εᵢ₋₁
- Let's say we build an ARMA model, such as the following: ARMA(2,1)
	- Our model would be represented as sᵢ-hat = β₀ + β₁sᵢ₋₁ + β₂sᵢ₋₂ + θ₁εᵢ₋₁
- Let's say we build an ARMA model, such as the following: ARMA(1,2)
	- Our model would be represented as sᵢ-hat = β₀ + β₁sᵢ₋₁ + θ₁εᵢ₋₁ + θ₂εᵢ₋₂

## References
- https://www.youtube.com/watch?v=HhvTlaN06AM&t=2s
- https://www.analyticsvidhya.com/blog/2015/12/complete-tutorial-time-series-modeling/
- https://maryclare.github.io/atsa/content/notes/notes_3.pdf 
