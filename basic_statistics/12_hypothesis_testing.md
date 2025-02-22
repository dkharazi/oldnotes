## General Description
- The basic idea of hypothesis testing is the following: does our hypothesis fit the data better than the alternative?
- Throughout any hypothesis testing, we need to ask ourselves whether the hypothesis fits so well, that it couldn't possibly be due to chance
- Therefore, we need a way to measure the fit between data and our hypothesis

## Goodness-of-Fit
- Traditionally, statistics that measure how well (or poorly) our data supports a statistical hypothesis are called goodness-of-fit measures
- The name is a little misleading, since high goodness-of-fit values indicate a very bad fit
- In other words, smaller goodness-of-fit values indicate a better fit
- The following are a few examples of common goodness-of-fit measures:
	- Mean square error (MSE)
	- Likelihood
	- Chi square statistic

## Significant Lack of Fit
- Typically, we have a statistical hypothesis about whether our data come from some distribution
- We'll test our hypothesis by testing a population parameter associated with our hypothesized distribution in some way
- Assume for simplicity, if our hypothesis matches the data exactly, our goodness-of-fit statistic G-hat will be 0, and that larger values of G-hat become less likely (i.e. P(G-hat>g) is a monotonically-decreasing function of g)
- We then take our measurements and compute the value of g-hat
- We now ask, what is the probability p that G-hat > g, assuming the hypothesis is true
- This is the p-value of the lack of fit
- An actual test of the hypothesis involves setting a threshold α, the significance level before taking the data, and rejecting the hypothesis if p ≤ α
- In other words, we reject the hypothesis if the deviation between it is highly significant (i.e. if it was very unlikely of occurring by sheer chance

## References
- http://bactra.org/prob-notes/srl.pdf
