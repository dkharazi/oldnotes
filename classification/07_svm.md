## General Description
- Hyperplanes represent a linear separator between two different classes
- Hyperplanes are also known as support vector classifiers in reference to support vector machines (SVM)
- An SVM is a classifier that finds the best hyperplane to separate data points into two different classes
- The best hyperplane is the hyperplane with the largest margin between the support vectors of the two classes
	- A hyperplane represents the threshold between the two classes
	- Margin is the distance between the support vectors of the two classes
	- Support vectors are the data points on the edge of each class that lie closest to the hyperplane

## Description of the Margin
- SVM chooses the hyperplane with the largest margin between the support vectors of the two classes
- When such a hyperplane exists, it is known as the maximum-margin hyperplane
- The linear classifier associated with the maximum-margin hyperplane is known as the maximum-margin classifier

## Defining the Maximum-Margin Hyperplane
- SVM chooses the hyperplane with the largest margin between the support vectors of the two classes
- SVM is sensitive to outliers within the training data for each class
- To get around this issue, SVM allows a few data points to be misclassified in an attempt to balance the trade-off between finding a line that maximizes the margin and a line that minimizes the misclassification
- This trade-off is a direct example of the bias-variance tradeoff
	- Specifically, the bias tends to increase (and the variance tends to decrease) when we start to allow for misclassifications in our training data
- Our margin is known as a soft margin when we allow for misclassifications

## Evaluating Soft Margins
- A margin is known as a soft margin when we allows for misclassifications
- We are able to determine the best soft margin by using cross validation
- Specifically, we use cross validation to determine the number of misclassifications (to allow inside of the soft margin) that produces the best test accuracy

## SVM General Algorithm
1. Start with the data in a relatively low dimension
2. Move the data into a higher dimension using kernel functions
3. Find a support vector classifier that separates the higher dimensional data into two groups

## The Kernel Trick
- A kernel function is used when data are non-linearly separable in its original space
- A kernel is a function that takes its input vectors in the original space and returns the dot product of the vectors in a feature space
- In other words, a kernel function will map data from its original space (where the classes are non-linearly separable) to another space where the classes are linearly separable
- Essentially, kernel functions are similarity functions
	- Given two objects, the kernel function outputs some similarity score
	- The objects can be anything starting from two integers, two vectors, etc.
- Examples of kernel functions:
	- Polynomial kernel
	- Gaussian kernel
	- Laplace RBF kernel
	- Hyperbolic Tangent kernel
	- Sigmoid kernel
 
## References
- https://uk.mathworks.com/help/stats/support-vector-machines-for-binary-classification.html
- https://towardsdatascience.com/kernel-function-6f1d2be6091
- https://towardsdatascience.com/the-kernel-trick-c98cdbcaeb3f
- https://stats.stackexchange.com/questions/152897/how-to-intuitively-explain-what-a-kernel-is
- https://towardsdatascience.com/support-vector-machine-simply-explained-fee28eba5496
- http://web.mit.edu/6.034/wwwbob/svm-notes-long-08.pdf
- http://www.robots.ox.ac.uk/~az/lectures/ml/lect2.pdf
- https://blog.statsbot.co/support-vector-machines-tutorial-c1618e635e93
- https://www.youtube.com/watch?v=efR1C6CvhmE
