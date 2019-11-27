## General Description
- In statistics, and interaction term is a variable in the model constructed of two (or more) predictors, representing the different effects of the combination of predictor variables on the response
- An interactions term allows for a different slope of the regression lines between the response variable and the different combinations of predictor variables (involved in the interaction)

## Example using Interaction Terms
- In our example:
	- The Height variable refers to the height of a shrub
	- The Bacteria variable refers to the amount of bacteria in the soil
	- The Sun variable refers to whether the shrub is located in partial sun or full sun
- We could create the initial model:
	- Height = β0 + β1*Bacteria + β2*Sun
	- After determining our coefficients: Height = 42 + 2.3*Bacteria + 11*Sun
- We may have a hypothesis that the relationship between the amount of bacteria in the soil and the height of the shrub is different in the full compared to partial sun
- Specifically, we may believe that shrubs with more bacteria in the soil tend to be taller if they have full sun exposure, whereas shrubs with more bacteria in the soil tend be be shorter if they have partial sun exposure (i.e. slope in different direction)
- Or, we may believe that shrubs with more bacteria in the soil tend to be taller if they have full sun exposure and partial sun exposure, but the relationship is much more dramatic in full sun exposure compared to partial sun exposure (i.e. slope in same direction, but steeper)
- Therefore, it would be useful to add the following interaction term to our model:
	- Height = β0 + β1*Bacteria + β2*Sun + β3*Bacteria*Sun
- Adding the interaction term changes the values of our coefficients to the following:
	- Height = 35 + 4.2*Bacteria + 9*Sun + 3.2*Bacteria*Sun

## Expanding on Example with Coefficient Interpretations
- As stated previously, our example model was defined as the following:
	- Height = β0 + β1*Bacteria + β2*Sun + β3*Bacteria*Sun
	- Or more specifically, Height = 35 + 4.2*Bacteria + 9*Sun + 3.2*Bacteria*Sun
- The effect of Bacteria on Height is now 4.2 + 3.2*Sun
- For plants with partial exposure to the sun (i.e. Sun = 0) and 1000mL of bacteria in the soil (i.e. Bacteria = 1), the effect of Bacteria is 4.2*1 + 3.2*0 = 4.2
- For plants with full exposure to the sun and 1000mL of bacteria in the soil, the effect of Bacteria is 4.2*1 + 3.2*1 = 7.4
- The interaction term states that the effect of having more bacteria in the soil is different if a plant has full or partial levels of sun exposure
- In other words, the slopes of the regression lines between height and bacteria count are different for the different categories of sun exposure
- β3 indicates how different those slopes are

## References
- http://www.stat.cmu.edu/~cshalizi/TALR/TALR.pdf
- https://www.theanalysisfactor.com/interpreting-interactions-in-regression/
- https://en.wikipedia.org/wiki/Interaction_(statistics)
- https://cran.r-project.org/web/packages/interactions/vignettes/interactions.html
- https://www.econometrics-with-r.org/8-3-interactions-between-independent-variables.html
