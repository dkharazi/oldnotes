## General Description
- An autoregressive model is a linear regression model, where the response variable is some variable index by the current time period and the predictor variables are the same variable indexed by previous time periods
- For example, we could create an autoregressive model to predict the average price of salmon in March depending on the average price of salmon in February and the average price of salmon in January
- In this case, we could define the autoregressive model as sᵢ =  β₀ + β₁sᵢ₋₁ + β₂sᵢ₋₂ + 𝜀ᵢ
	- Where sᵢ represents the average price of salmon in the current time period (i.e. March)
	- Where sᵢ₋₁ represents the average price of salmon in the previous time period (i.e. February)
	- Where sᵢ₋₂ represents the average price of salmon in the time period before the previous time period (i.e. March)

## Including Lag Variables
- A lag variable refers to a predictor from a previous time period in an autoregressive model
- For example, the average price of salmon in February (i.e. sᵢ₋₁) would be considered a lag variable in our case
- Including every single lag variable (or a very large amount of lag variables) is a typical naive approach to fitting an autoregressive model
- However, this typically leads to overfitting
- Therefore, we are interested in only including the most significant lag variables in our model to avoid overfitting, and thus building a model that will hold up better over time
- We can determine which lags are most significant by observing the lags within a partial autocorrelated function (or pacf) chart
- Specifically, we want to know which months have prices that are directly correlated with the prices of our current month
- Essentially, we only want to include the lags in our model whose direct effects (based on pacf) are high in magnitude according to the pacf chart

## References
- youtube.com/watch?v=5-2C4eO4cPQ&t=264s
