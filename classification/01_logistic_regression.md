## General Description
- Logistic regression is a learning method that uses a logistic function (or sigmoid function) to model a binary dependent variable 
- The most common form of logistic regression is binary logistic regression, which is used for establishing a relationship between one or more independent variables and a dependent categorical variable with 2 categories (i.e. binary variable)
- Essentially, logistic regression is equivalent to the linear regression model (or the linear combination of the independent variables) with the sigmoid function applied to it
- The output of a linear regression model are the conditional means (i.e. Y|X), whereas the output of a logistic regression model are the conditional probabilities (i.e. P(y=1|X))


- THe odds are just the ratio of something happening relative to something not happening (i.e. my team winning/my team not winning)
- The log odds is just the log of the odds
- The log odds makes things symmetrical, or easier to interpret due to linearity

## Logit Function
- The Logit function will always product a lienar regressioj line
- Refers to the log-odds
- The beta coefficients (given by the glm output in R) relates to the change in log odds
- For example, increasing X by one units changes the log odds b beta-1 or multiplies the odds by e^beta-1

## Odds fynction
- Refers to the odds
- For example, if an average of nine out of every ten people will default, then the odds of a persoon defaulting is 9, since p(X) = 0.9 implies an odds of 0.9/(1-0.9)=9

## Logistic function
- The logistic function will always produce an S-shaped curve
- Refers to probabilties
- For example, the amount that p(X) changes due to a one-unit change in X will depend on the current value of X

## References
- https://medium.com/datadriveninvestor/logistic-regression-18afd48779ce
- https://sebastianraschka.com/faq/docs/logistic-why-sigmoid.html
