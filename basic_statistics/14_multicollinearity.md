## General Description
- Collinearity is a condition in which some of the independent variables are highly correlated with the other independent variables
- Collinearity tends to be a problem because it tends to inflate the variance of at least one estimated regression coefficient (specifically, one of the coefficients associated with collinearity)
- Specifically it will look like we have p different predictor variables, but really some of them are linear combinations of the other (so they don't add any information)
- Multicollinearity is a form of collinearity involving a perfectly linear relationship between moer than two predictor variables

## Diagnosing and Dealing with Collinearity
- The most common method of diagnosing collinearity in our model involves creating pairs plots between each predictor
- The most common method of dealing with collinearity involves removing one of the variables from our model
- When removing collinear predictor variables, we need to be careful about which predictor variable we should remove
- For example, keeping a GPA predictor variable in our model may make more sense than keeping a categorical-level grade predictor variable in our model

## Diagnosing and Dealing with Multicollinearity
- Diagnosing multicollinearity can be more difficult (compared to diagnosing collinearity)
- A multicollinear relationship may involve three or more variables that could be totally invisible on a pairs plot
- Some turn to the variance inflation factors (VIF) to detect multicollinearity, but this can also be manipulated to miss multicollinearity
	- If the predictors are correlated with each other, the standard errors of the coefficient estimates will be bigger than if the predictors were uncorrelated
- Ridge regression typically works well in the presence of multicollinearity
- Also, one substantial advantage of ridge regression is that we don't have to make any decisions about which variables to remove, and can match (to extremely high accuracy) what we'd get after dropping variables

## References
- http://www.stat.cmu.edu/~cshalizi/TALR/TALR.pdf
- http://www.stat.tamu.edu/~hart/652/collinear.pdf
- https://stats.stackexchange.com/questions/104779/why-does-ridge-regression-work-well-in-the-presence-of-multicollinearity
