## General Description
- L1 regularization is regularization technique used for variable selection 
- L1 regularization achieves variable selection by shrinking the OLS coefficients down to zero
- L1 regularization quickly shrinks the OLS coefficients by applying a penalty term to the OLS objective function, and minimizing this modified cost function instead of the original OLS objective function
- The penalty term associated with L1 regularization is the absolute value of the magnitude of OLS coefficients, which is the main difference between the L1 and L2 regularization methods
- L1 regularization is used in lasso regression 

## Mathematical Properties of L1 Regularization
- L1 regularization involves a diamond-shaped constraint region
- The optimal point intersecting the elliptical contour plot (representing the objective function) and the constraint region lies on an axis where βj=0, which provides L1 regularization with the function of variable selection
- L1 regularization uses convex optimization, and causes the beta coefficients to converge to 0 quickly

## Use-cases for L1 Regularization
- Coefficient estimation that is robust to outliers
- Variable selection

## References
- https://www.quora.com/What-is-the-difference-between-L1-and-L2-regularization-How-does-it-solve-the-problem-of-overfitting-Which-regularizer-to-use-and-when
- http://laid.delanover.com/difference-between-l1-and-l2-regularization-implementation-and-visualization-in-tensorflow/
- http://www.socr.umich.edu/people/dinov/courses/DSPA_notes/17_RegularizedLinModel_KnockoffFilter.html
