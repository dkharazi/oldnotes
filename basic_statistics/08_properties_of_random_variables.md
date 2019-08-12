## Preface
- Given a sequence of random variable X1, X2 ...Xn that are independent and identically-distributed (IID), we know:
	- X has the finite mean µ
        - The average of the first n random variables is Sn ≡ (1/n)∑Xi

## The Law of Large Numbers
- The means of IID sequences converge to the mean of the variables: Sn → µ as n → ∞

## The Central Limit Theorem
- Assuming that X has a finite variance σ2, then as n → ∞, the Sn random variables converge to a Gaussian random variable with mean µ and variance σ2

## Assumptions
- The Law of Large Numbers and Central Limit Theorem assume:
	1. Independent observations of X
	2. Identically distributed observations of X
	3. The observations of X have a constant variance
- If any of these assumptions are broken, then these theorems will start to fall apart

## Why Things are Gaussian?
- Whenever we have additive effects of many independent causes, each of which has only a small relative effect, we are inclined to
suspect Gaussians
- In other words, when you combine many independent random variables, the result tends towards a Gaussian (normal) distribution, since the errors in measurements, or of those random variables, are normally distributed
	- Hence, the many biological examples of Gaussian distributions
		- E.g. chest widths of Scots army recruits
		- E.g. annual number of sucides in Belgium

## References
- http://bactra.org/prob-notes/srl.pdf
- https://dsp.stackexchange.com/questions/53128/why-is-random-noise-assumed-to-be-normally-distributed
