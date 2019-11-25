## Sample Mean
- An estimator of the population mean µ is represented as µ-hat
- Additionally, µ-hat is an unbiased estimator of the population mean µ
- The sample mean is the unbiased estimator of the population mean
- The sample mean is just what you'd expect: x-bar = (1/n)*Σxi

## Sample Variance
- The sample variance is not a good estimate of the population variance
- Specifically, it's not an unbiased estimator of the population variance
- Thus, it’s too small
- The population variance is best estimated by (n/n−1)*s²
- Hence, the notational usage of s², instead of σ-hat²
- The story here, heuristically, is that we tend to lose variation under sampling
- So, measures of variation in the sample need to be corrected upwards, so this is the right correction to use
- A sophisticated story claims that this distinction is really important in estimation, and what we really should divide through by, is not the number of data-points but the number of degrees of freedom
- And, to get the variance, we need to estimate the mean, thereby losing one degree of freedom
- Essentially, while we should use (n/n−1)*s² as our estimate of the population variance, if the difference between that and s² is big enough to matter, you probably should think about getting more data points
- The sample variance is just what you’d expect: s² = (1/n)*Σ(xi−µhat)²

## References
- http://bactra.org/prob-notes/srl.pdf
