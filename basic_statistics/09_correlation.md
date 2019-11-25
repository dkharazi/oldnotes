## General Description
- Correlation is used in a specific sense in statistics
- Correlation refers to how close two random variables share a linear relationship (plus noise) between each other
- In other words, correlation refers to whether two random variables change by a constant, proportional amount with each other
- Said another way, when one variable goes up, the other variable goes up
- Specifically, when one variable goes up, the other variable goes up by an amount proportional to the increase of the first variable (on average)
- Correlation can be represented by covariance or the correlation coefficient

## Covariance
- Covariance also refers to how close two random variables share a linear relationship (plus noise) between each other
- However, covariance is an unstandardized version of the correlation coefficient
- Therefore, covariance can be useful if we want to know the direction of how two variables vary together, or if we want to know if the two variables are independent (i.e. Cov(X,Y)=0)
- But, covariance will make it difficult to interpret the magnitude of variability between two variables
- For example, we know how to interpret a positive covariance, a negative covariance, and a covariance of 0, and we know that in theory two variables that move together more should have a high covariance -- but what even is high?
- This is where correlation comes into play, since it is essentially a normalized covariance metric
- A covariance value by itself doesn't mean much, but with it you can compare it to other covariance values
- One way of measuring correlation between two variables is their covariance:
	- Cov(X,Y) = (1/n-1)*Σ(xi-xbar)(yi-ybar)

## The Correlation Coefficient
- The (Pearson's) correlation coefficient is just a normalized covariance
- The correlation coefficient is thus constrained to lie between -1 and +1, where 0 implies the two random variables are independent
- The extreme values indicate perfect linear dependence
- One way of measuring correlation between two variables is their correlation coefficient:
	- Cor(X,Y) = Cov(X,Y)/(SD(X)*SD(Y))

## References
- http://bactra.org/prob-notes/srl.pdf
