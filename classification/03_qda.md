## General Description
- Quadratic Discriminant Analysis (QDA) is a supervised classification technique that is typically solved using bayes theorem (i.e. Bayesian techniques)
- QDA uses quadratic decision boundaries to determine the class of an observation, whereas LDA uses linear decision boundaries

## Assumptions
- Observations within each class are drawn from a multivariate Gaussian distribution
- Each class has its own unique mean vector, and each class can have differing variance/covariance
	- This is the primary difference between LDA and QDA
	- This makes QDA more flexible than LDA, which can cause it to perform better generally, but worse if there is a small sample size (typical issues with overfitting)

## Approach
- Make predictions using Bayes theorem (Bayesian techniques)

## QDA Compared to LDA
- QDA holds the same assumptions as LDA except that the covariance matrix is not common for each classification
- QDA tends to be more flexible and accurate compared to LDA, since QDA captures non-linear relationshipsto between predictors in the data
- QDA tends to be more computationally expensive compared to LDA
- QDA tends to fall victim to overfitting, due to its added flexibility

## References
- https://onlinecourses.science.psu.edu/stat508/book/export/html/696
- https://mdav.ece.gatech.edu/ece-6254-spring2017/notes/04-plugin-rules.pdf
