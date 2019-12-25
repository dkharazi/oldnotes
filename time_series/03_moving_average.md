## General Description
- A moving average model is linear regression model, where the response variable represents some value indexed by the current time period and the predictor variables represent our mean of the value and some white noise error term
- Specifically, we can define a moving average model of order r as the following:
	- sᵢ =  μ + θ₁𝜀ᵢ₋₁ + θᵣ𝜀ᵢ₋ᵣ
	- Where sᵢ is the predicted value in our current time period
	- Where μ is the mean of our values (this is constant for any i)
	- Where 𝜀ᵢ₋₁ is the error of the previous value and what we observed
	- Where θ₁ represents the percentage of the error 𝜀ᵢ₋₁ we should include in our model
	- Where 𝜀ᵢ₋ᵣ is the error of the rth previous value and what we observed
	- Where θᵣ represents the percentage of the error 𝜀ᵢ₋ᵣ we should include in our model
- The moving-average model should not be confused with the simple moving average, which takes the arithmetic mean of a given set of prices over the past number of days

## Example of Moving Average Model of Order 1
- Let's say we're predicting the price of salmon each month using a moving average model of only the the previous month's data
- We can define our model as sᵢ-hat = μ + θ₁𝜀ᵢ₋₁
	- Where sᵢ-hat is our current prediction
	- Where μ is the mean of our values
	- Where 𝜀ᵢ₋₁ = sᵢ₋₁-hat - sᵢ₋₁, or the difference betweeen our previous prediction and the previous observed value
	- Where θ₁ represents the percentage of the previous error 𝜀ᵢ₋₁ we should include in our model
- The table below shows our observed data and predictions of a few iterations

| month | i | sᵢ-hat | 𝜀ᵢ | sᵢ   | μ  | θ₁  | θ₁𝜀ᵢ |
| ----- | - | ------ | -- | ---- | -- | --- | ---- |
| Jan   | 1 | 10     | -2 | 8    | 10 | 0.5 | -1   |
| Feb   | 2 | 9      | 1  | 10   | 10 | 0.5 | 0.5  |
| March | 3 | 10.5   | 0  | 10.5 | 10 | 0.5 | 0    |
| April | 4 | 10     | 2  | 12   | 10 | 0.5 | 1    |
| May   | 5 | 11     | 1  | 12   | 10 | 0.5 | 0.5  |

- We can interpret the second iteration as the following:
	- Our predicted price of salmon in February (i.e. s₂-hat) is 9
	- The error of our predicted price of salmon in January (i.e. 𝜀₁) is -2
	- The actual price of salmon in February (i.e. s₂-hat) is 10
	- The average price of salmon (i.e. μ) is 10
	- The percentage of the previous error that we wanted to include (i.e. θ₁) is 0.5

## Example of Moving Average Model of Order 2
- Now, let's say we want to use the two previous month's data to predict the price of salmon using a moving average model
- We can define our model as sᵢ-hat = μ + θ₁𝜀ᵢ₋₁ + θ₂𝜀ᵢ₋₂
- The table below shows our observed data and predictions of a few iterations

| month | i | sᵢ-hat | 𝜀ᵢ | sᵢ   | μ  | θ₁  | θ₁𝜀ᵢ |
| ----- | - | ------ | -- | ---- | -- | --- | ---- |
| Jan   | 1 | 10     | -2 | 8    | 10 | 0.5 | -1   | 
| Feb   | 2 | 9      | 1  | 10   | 10 | 0.5 | 0.5  |
| March | 3 | 9.5    | 1  | 10.5 | 10 | 0.5 | 0.5  |
| April | 4 | 11     | 1  | 12   | 10 | 0.5 | 0.5  |
| May   | 5 | 12     | 0  | 12   | 10 | 0.5 | 0    |

- We can interpret the third iteration as the following:
	- Our predicted price of salmon in March (i.e. s₃-hat) is 9.5
	- The error of our predicted price of salmon in February (i.e. 𝜀₂) is 1
	- The error of our predicted price of salmon in January (i.e. 𝜀₁) is -2
	- The actual price of salmon in March (i.e. s₃) is 10.5
	- The average price of salmon (i.e. μ) is 10
        - The percentage of the error from February's prediction that we wanted to include (i.e. θ₁) is 0.5
	- The percentage of the error from January's prediction that we wanted to include (i.e. θ₂) is 0.5

## References
- https://www.youtube.com/watch?v=voryLhxiPzE
- https://newonlinecourses.science.psu.edu/stat510/lesson/2/2.1
- https://people.duke.edu/~rnau/411arim.htm
- https://faculty.chicagobooth.edu/jeffrey.russell/teaching/finecon/handouts/notes2.pdf
