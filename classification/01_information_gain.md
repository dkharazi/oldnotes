## General Description
- Information gain is the amount of information gained about a random variable from observing another random variable
- Information gain is a metric that is used to evaluate the splitting criteria for a decison tree
- In other words, we evaluate the information gain of an attribute (or split) to tell us how important the attribute is
- The following are some example attributes we may evaluate using information gain:
	- Should we split on balance > 50k
	- Should we split on applicant = employed
	- Should we split on weather = sunny
- Information gain uses the entropy metric in its calculation
- Specifically, information gain can be defined as the following equation:
	- Information Gain = entropy(parent)-average_entropy(proposed children)
- Our goal is to find a split that maximizes the information gain, which will happen if we minimize the entropy for the groups created by the split

## Entropy
- Entropy measures the level of impurity in a group created by a proposed split
- We should only think about splitting if our group is very impure (i.e. Entropy = 1)
- Our goal is to find a split that minimizes the entropy for each group created by the split
- Minimizing the entropy is the same as minimizing the impurity
- In other words, the best split will be the one that makes sure each group contains data with the same value (i.e. the least impure)
- Entropy is defined by the following equation:
	- Entropy = sum(-pᵢlogpᵢ)
		- Where pᵢ is the probability of class (or group) i

## Examples of Entropy Calculation
- Let's say we are trying to evaluate the purity of a group, where we have 16 males and 14 females in our sample
	- Entropy = (-16/30)(-0.9) - (14/30)(-1.1) = 0.99
	- In this case, we should think about splitting, since the group is extremely pure
- Let's say we are trying to evalute the purity of a group, where we have only 16 males in our sample
	- Entropy = (-16/16)(0) = 0
	- In this case, we shouldn't think about splitting, since the group is extremely pure

## Example of Information Gain Calculation
- Let's say we are trying to evaluate a split of a group, where we initially have 16 males and 14 females in our sample
1. Calculate the parent entropy
	- -(14/30)(log(14/30)) - (16/30)(log(16/30)) = 0.996
	- In this case, the impurty is large, so we should split
2. Calculate one child's entropy
	- -(13/17)(log(13/17)) - (4/17)(log(4/17)) = 0.787
	- Here, there are 17 data points in this group after the split
	- Also, 13 of those data points are female, and 4 of those data points are male
	- In this case, the impurity is fairly high for this group after the split
3. Calculate the other child's entropy
	- -(1/13)(log(1/13)) - (12/13)(log(12/13)) = 0.391
	- Here, there are 13 data points in this group after the split
	- Also, 1 of those data points are female, and 12 of those data points are male
	- In this case, the impurty is fairly small for this group after the split
4. Calculate the weighted average entropy of the children
	- ((17/30)0.787) + ((13/30)0.391) = 0.615
5. Calculate the information gain
	- 0.996 - 0.615 = 0.38
	- Therefore, this split gives us 0.38 amount of additional information
	- We should evalute other splits, and choose this one if there aren't any other splits with an information gain greater than 0.38

## References
- https://homes.cs.washington.edu/~shapiro/EE596/notes/InfoGain.pdf
- https://www.stat.cmu.edu/~cshalizi/350/2008/lectures/05/lecture-05.pdf
- https://en.wikipedia.org/wiki/Information_gain_in_decision_trees
