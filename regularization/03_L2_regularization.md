## General Description
- L2 regularization is regularization technique used for variable selection, roughly speaking
- L2 regularization achieves variable selection by slowly shrinking the OLS coefficients down to zero, but not exactly zero
- L2 regularization shrinks the OLS coefficients by applying a penalty term to the OLS objective function, and minimizing this modified cost function instead of the original OLS objective function
- The penalty term associated with L2 regularization is the square of the magnitude of OLS coefficients, which is the main difference between the L1 and L2 regularization methods
- L2 regularization is used in ridge regression

## Mathematical Properties of L2 Regularization
- L2 regularization involves a circular-shaped constraint region
- The optimal point intersecting the elliptical contour plot (representing the objective function) and the constraint region does not lie on any axis where βj=0, which provides L2 regularization with its incapability of true variable selection
- L2 regularization uses convex optimization, and causes the beta coefficients to almost converge to 0 but never to 0 exactly

## Use-cases for L2 Regularization
- Coefficient estimation
- Close to variable selection, but not quite

## References
- https://www.quora.com/What-is-the-difference-between-L1-and-L2-regularization-How-does-it-solve-the-problem-of-overfitting-Which-regularizer-to-use-and-when
- http://laid.delanover.com/difference-between-l1-and-l2-regularization-implementation-and-visualization-in-tensorflow/
- http://www.socr.umich.edu/people/dinov/courses/DSPA_notes/17_RegularizedLinModel_KnockoffFilter.html
- https://stats.stackexchange.com/questions/176599/why-will-ridge-regression-not-shrink-some-coefficients-to-zero-like-lasso
