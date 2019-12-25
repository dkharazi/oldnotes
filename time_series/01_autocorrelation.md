## Motivating Time Series Models
- Let's say we want to predict the average price of salmon in our city this month
- Let's say we believe knowing the average price of salmon in our city last month and each month prior will help us predict the average monthly price of salmon in our city this month
- In other words, we believe the average price of salmon at each time period is dependent on the average price of salmon from the previous time periods
- Mathematically, we would write the average price of salmon in our city this month as the following: sᵢ
- Mathematically, we would write the average price of salmon in our city last month as the following: sᵢ₋₁
- Mathematically, we would write the average price of salmon in our city two months ago as the following: sᵢ₋₂

## Motivating Time Series Dependencies
- Building off of our previous example, let's say our current month is March
- Most likely, the price of salmon in January is going to have some kind of effect on the price of salmon in February
- Similarly, the price of salmon in February is going to have some kind of effect on the price of salmon in March
- However, we should also expect the price of salmon in January to have some kind of effect on the price of salmon in March as well
- In other words, we know the price of salmon at a given time period is dependent on the price of salmon from its previous time period, but sometimes the price of salmon at a given time period can also be dependent on the price of salmon from time periods before its previous time period as well
- The following is a concrete example of the above concept:
	- Let's say there's a big food festival that happens in our city every two months
	- Specifically, the food festival happens in January, March, and May
	- Let's also say the salmon shops want to make more money off of the food festivals, so they raise the price of salmon during the months of the food festival
	- Therefore, every other time period has a direct effect on the price of salmon

## Motivating Aurocorrelation
- From the previous example, we are still trying to determine the average price of salmon in March
- There are two types of effects on our price, which are the following:
	- Direct effects
		1. The direct effect of the price of salmon in January on the price of salmon in March (i.e. sᵢ₋₂ -> sᵢ)
		2. The direct effect of the price of salmon in February on the price of salmon in March (i.e. sᵢ₋₁ -> sᵢ)
	- Indirect effects
		1. The indirect effect of the price of salmon in January on the price of salmon in March (i.e. sᵢ₋₂ -> sᵢ₋₁ -> sᵢ)
- Let's say we want to determine if the price of salmon in January is correlated with the price of salmon in March, then we would typically account for the direct and indirect effects of the price of salmon in other time periods
- This is known as the autocorrelation function, which is just a simple Pearson's correlation between the two predictors
- In our case, we could write the autocorrelation function between two time periods as acf(sᵢ₋₂, sᵢ) or acf(january_price, march_price), which is the same thing as finding the correlation between two predictors from our high school math class (i.e. using Pearson's correlation)
- The following are some examples of the autocorrelation function in action:
	- acf(january_price, march_price) is large and postive, because the food festival causes them to vary together in harmony
	- acf(february_price, march_price) is large and negative, because the food festival causes them to vary together in an opposite manner
	- acf(january_1800_price, march_2019_price) is most likely small, because the food festival wasn't around and had no effect on the prices, and thus the prices were most likely unrelated so they do not vary together
- In other words, the correlation between the price of one time period and another time period accounts for both the direct and indirect effects

## Motivating Partial Autocorrelation
- The partial autocorrelation function tries to account for the direct effects only
- The partial autocorrelation function does this by excluding the indirect effects from our function
- From our previous example, we can represent our system of equation as the following:
	- sᵢ = β₀ + β₁sᵢ₋₁ + β₂sᵢ₋₂ + 𝜀ᵢ
	- Where sᵢ is the price of salmon in March (i.e. the current month)
	- Where sᵢ₋₁ is the price of salmon in February (i.e. the previous month)
	- Where sᵢ₋₂ is the price of salmon in March (i.e. two months ago)
	- Where β₁ represents the following:
		- The indirect effect of the price of salmon in January on the price of salmon in March
		- The direct effect of the price of salmon in February on the price of salmon in March
	- Where β₂ represents the direct effect of the price of salmon in January on the price of salmon in March
		- Therefore, β₂ is partial autocorrelation function coefficient, which represents the coefficient returned by the partial autocorrelation function (i.e. pacf(sᵢ₋₂, sᵢ))
		- In other words, β₂ represents the correlation of the price of salmon in January (i.e. sᵢ₋₂) and the price of salmon in March (i.e. sᵢ), only including the direct effects between the two time periods
- In the example given above, we would say our lag is 2, since the number of time periods we're looking at from our current time period (i.e. March) is 2
- Mathematically, the partial autocorrelation function does this by solving its system of equations (similar to solving for the beta coefficients) using Durbin-Levinson recursion (i.e. linear algebra methods)
- We can visualize the coefficients returned by partial autocorrelation function using an partial autocorrelation plot

## Visualizing the PACF
- Time series are serially dependent, meaning sᵢ is generally dependent on all earlier values in time
- Typically, there is a decay of dependence as the points in time grow farther and farther apart form each other
- Therefore, when we observe the lag values in a partial autocorrelation plot, we can see their respective correlations decrease as the lag values increase
- Typically, we only keep the partial autocorrelation coefficients that are very large (and outside of our interval hovering around zero) 

## References
- https://www.youtube.com/watch?v=DeORzP0go5I
- https://www.stat.cmu.edu/~cshalizi/uADA/12/lectures/ch26.pdf
- https://machinelearningmastery.com/gentle-introduction-autocorrelation-partial-autocorrelation/
- https://stats.stackexchange.com/questions/77248/what-is-autocorrelation-function
- http://www.wiwi.uni-muenster.de/05/download/studium/timeseries/WS1415/chapter_5.pdf
