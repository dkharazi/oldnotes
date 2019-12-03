## General Description
- Suppose we want to guess the value of a random variable
- Since we don't feel comfortable with the word guess, we use the word prediction instead
- Our goal is to find the best buess for our random variable
- We need some way to measure how good a guess is
- Therefore, we use metrics to measure the accuracy of our guesses

## Preliminary Notes about Regression Metrics
- A metric is a quantitative standard of measurement
- There isn't any Holy Grail of regression metrics
- Solely using one regression metric for every case is a bad idea
- Each metric has its own use-case, and should be used carefully and accordingly

## Basics of MSE
- The mean squared error (or MSE) is defined as the following:
	- MSE(m) = E[(Y-m)²] = (E[Y-m])² + Var[Y-m]
	- Bias: (E[Y-m])²
	- Variance: Var[Y-m]
- In other words, the mean squared error represents any bias or variance associated with a prediction
- The mean squared error represents the simplest form of the bias-variance decomposition
- Our goal is to find a prediction that minimizes the MSE
	- The variance term is irrelevant when minimizing the MSE, since Var[Y-m] = Var[Y]
	- Therefore, we should really only focus on minimizing the bias
- The MSE formula can be simplified to the following:
        - MSE = mean((yᵢ-yhatᵢ)²) = mean(errorᵢ²)

## Basics of RMSE
- The root mean squared error (or RMSE) is defined as the following:
	- RMSE(m) = SQRT(MSE(m)) = SQRT(E[(Y-m)²]) = SQRT((E[Y-m])² + Var[Y-m])
	- Bias: (E[Y-m])²
        - Variance: Var[Y-m]
- In other words, the root mean squared error represents the square root of any bias or variance aggregated together, associated with a prediction
- Our goal is to find a prediction that minimizes the RMSE
	- The variance term is irrelevant when minimizing the RMSE, since Var[Y-m] = Var[Y]
	- Therefore, we should really only focus on minimizing the bias
- The RMSE formula can be simplified to the following:
        - RMSE = sqrt(mean((yᵢ-yhatᵢ)²)) = sqrt(mean(errorᵢ²))

## Basics of MAE
- The mean absolute error (or MAE) is defined as the following:
	- MAE(m) = E[|(Y-m)|] = |E[Y-m]| + Var[Y-m]
	- Bias: |E[Y-m]|
	- Variance: Var[Y-m]
- In other words, the mean absolute error represents any bias or variance associated with any prediction
- Our goal is to find a prediction that minimizes the MAE
	- The variance term is irrelevant when minimizing the MAE, since Var[Y-m] = Var[Y]
	- Therefore, we should really only focus on minimizing the bias
- The MAE formula can be simplified to the following:
	- MAE = mean(|yᵢ-yhatᵢ|) = mean(|errorᵢ|)

## Use-Cases for MAE, MSE, and RMSE
- Since we are squaring the errors in the MSE and RMSE, we should use these metrics (over MAE) if we want to penalize the predictions as they are increasingly off from our data points
- In other words, we should use the MSE or RMSE metrics if we want to penalize large errors
- For example, if our prediction being off by 10 is twice as bad as being off by 5, then we should most likely use MAE
- On the other hand, if our prediction being off by 10 is more than twice as bad as being off by 5, then we should most likely use MSE or RMSE
- From an interpretation standpoint, MAE is clearly the winner, since it's difficult to interpret the square in the MSE or RMSE
- From a mathematical standpoint, MSE is clearly the winner, since it's difficult to perform many mathematical calculations on formulas involving the absolute value

## Notation for MAPE and MASE
- Let y𝑡 denote the current observation at time 𝑡
- Let y𝑡₋₁ denote the previous observation at time 𝑡₋₁ 
- Let f𝑡 denote the forecast of y𝑡
- Let e𝑡 denote the forecast error where e𝑡=y𝑡-f𝑡
- Let oe𝑡 denote the one-step naive error where oe𝑡=y𝑡-y𝑡₋₁

## Basics of MAPE
- The mean absolute percentage error (or MAPE) is defined as the following:
	- MAPE = 100 * mean(|e𝑡|/|y𝑡|)
- The MAPE favors predictions that are smaller than its data value, which can be considered a drawback
	- On othe other hand, we may want this property depending on our problem, in which case we would want to use MAPE
- In other words, the MAPE puts a heavier penalty on forecasts that exceed the actual values than those that are less than the actual values
- Said another way, the MAPE puts a heavier penalty on negative errors than positive errors
- Naturally, we would like to avoid this asymmetry of the MAPE
- The MASE can be used if we want a more symmetrical measure of the percentage error

## Basics of MASE
- The mean absolute scaled error (or MASE) is arguably considered the best available measure of forecast accuracy
- Before we define the MASE formula, we should define a one-step naive error:
	- The one-step naive error (denoted here as oe𝑡) refers to the error associated with guessing the previous data value as our current prediction
- The MASE is defined as the following:
	- MASE = mean(|e𝑡|/((1/(n-1))*Σ|y𝑡−y𝑡₋₁|))
	- Where the scaled error term refers to |e𝑡|/((1/(n-1))*Σ|y𝑡−y𝑡₋₁|)
	- Therefore, MASE = mean(scaled-error𝑡)
- The MASE can be roughly simplified to the following:
	- MASE = mean(|e𝑡|/mean(|oe𝑡|))
	- Where the scaled error term roughly refers to |e𝑡|/mean(|oe𝑡|)
- Essentially, the MASE is an average of our scaled errors
- The MASE has the following benefits:
	- Working with scaled errors, since the scaled errors are independent of the scale of the data
	- Symmetrical measure
	- Less sensitive to outliers compared to other metrics
	- Easily interpreted metric using scaled errors (compared to other metrics like RMSSE)
	- Less variable on small samples
- We can interpret scaled errors based on the following criteria:
	- A scaled error is less than one if our forecast is better than the average one-step naive forecast (i.e. using the previous data point)
	- A scaled error is greater than one if our forecast is worse than the average one-step naive forecast (i.e. using the previous data point)

## Perils of F-tests
1. F test does not measure goodness of fit (linear fit, non-linear fit, etc.)
	- Suppose that we reject the null, intercept-only hypothesis
	- This does not mean that the simple linear model is right
	- It means that the latter model predicts better than the intercept-only model — too much better to be due to chance
	- The simple linear regression model can be absolute garbage, with every single one of its assumptions flagrantly violated, and yet better than the model which makes all those assumptions and thinks the optimal slope is zero
2. F test is a pretty useless measure of predictability
	-  Not finding any significant share of variance associated with the regression could be because there is no such variance (and the intercept-only model is correct), there is some variance (but we were unlucky), or the test doesn’t have enough power to detect departures from the null
	- To expand on that last point, the power to detect a non-zero slope is going to increase with the sample size n, decrease with the noise level σ², and increase with the magnitude of the slope |β|

## Perils of R²
1. R² does not measure goodness of fit (linear fit, non-linear fit, etc.)
	- R² can be low when the model follows a completely correct form (by making the variance of our random variable large)
	- R² can be close to 1 when the model follows a completely incorrect form (by making the variance of our random variable small)
	- More specifically, R² can be very high when the true model fit is linear, but our model fit is non-linear (since all that matters is for the slope of the best linear approximation to be non-zero)
2. R² is a pretty useless measure of predictability
	- R² says nothing about prediction error (R² can be anywhere between 0 and 1 just by changing the range of our random variable)
	- R² says nothing about interval forecasts (particularly it doesn't give us any notion of how large our confidence interval is)
	- Specifically, MSE is a much better measure of prediction error
3. R² cannot be compared across data sets
	- Specifically, the same model can have radically different R² values on different data
4. R² cannot be compared between a model with an untransformed response variable and one with a transformed response variable (or between different transformations of response variables)
	- Specifically, the R² can be different by changing the range of our response variable
- The one situation where R² can be compared is when different models are fit to the same data set with the same, untransformed response variable
- However, you might as well just compare the MSE measures in this situation
- Note that the adjusted R² does absolutely nothing to fix any of these issues

## References
- https://robjhyndman.com/papers/mase.pdf
- http://www.stat.cmu.edu/~cshalizi/TALR/TALR.pdf
- https://robjhyndman.com/hyndsight/smape/
- https://stats.stackexchange.com/questions/11636/the-difference-between-mse-and-mape
- https://en.wikipedia.org/wiki/Mean_squared_error
- https://medium.com/human-in-a-machine-world/mae-and-rmse-which-metric-is-better-e60ac3bde13d
- https://www.reddit.com/r/datascience/comments/9nk0n5/assessing_regression_accuracy_interpretable/
