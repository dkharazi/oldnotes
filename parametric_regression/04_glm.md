## General Description
- When we build a model using parameteric regression, we are typically predicting the values of some response variable conditional on some predictor variables
- A generalized linear model assumes the conditional distribution of the response variable conditional on predictors (i.e. Y|X) is a member of some family of distributions
- Therefore, out model's predictions of Y|X will belong to the same family of distribution
- For example:
	- Linear regression assumes the conditional distribution of Y|X is a gaussian distribution
	- Logistic regression assumes the conditional distribution of Y|X is a bernoulli distribution
	- Poisson regression assumes the conditional distribution of Y|X is a poisson distribution

## Characteristics of a GLM
- A generalized linear model is a type of model where the model's predictions are transformed to some output that is linearly related to the predictors
- A generalized linear model is able to achieve this because it assumes the distribution of a given model's predictions (and thus Y|X) is a member of some family of distributions
- The transformation is performed using a link function

## Link Function
- As mentioned previously, a link function maps a model's predictions to some transformed output that is linearly related to the predictors
- In other words, a link function transforms our model's predictions from a particular distribution to another distribution
- A link function achieves this by adjusting the magnitude of the variance of each measurement to be a function of its predicted value
- In other words, a link function will map the model's predictions to a scale where the relationship between the transformed predictions and the predictors is linear
- This scale is pre-determined according to the the assumed family of distribution for Y|X in the model

## Examples of Link Functions
- The logit function
	- The logit function is an example of a link function
	- If we input a logistic regression model's predictions into the logit function, then the function will return the log-odds
	- The log-odds are linearly related to the predictors
	- The logit link function is used to transform probabilities on the probability scale (i.e. [0,1]) to log-odds on the logit scale
	- In other words, the logit link function maps probabilities to a scale where the relationship between the transformed probabilities and the predictors is linear
- The log function
	- The log function is an example of a link function
	- If we input a poisson regression model's predictions into the log function, then the function will return some transformed output (related to the incident ratio)
	- This transformed output is linearly related to the predictors

## References
- https://en.wikipedia.org/wiki/Generalized_linear_model
- https://en.wikipedia.org/wiki/Generalized_linear_model#Link_function
- https://www.researchgate.net/post/What_is_the_difference_between_the_general_linear_model_GLMand_generalized_linear_model_GZLM
- https://stats.stackexchange.com/questions/48594/purpose-of-the-link-function-in-generalized-linear-model
- https://www.sciencedirect.com/topics/mathematics/logit-scale
- https://www.reddit.com/r/statistics/comments/cc18wr/explain_like_im_5_what_does_a_link_function_do_in/
