## True Positive Rate
- Before we define the true positive rate, we should first introduce some terminology associated with the true positive rate
	- The number of true positives is defined as TP
	- The number of positives is defined as P
	- TP refers to the number of observations that are correctly predicted as positive
	- P refers to the number of observations that are positive (i.e. P = TP + FP)
- The true positive rate is defined as TP/P
- In other words, the true positive rate is defined as as number of true positives divided by the total number of positives
- The true positive rate refers to the percentage of observations that are correctly predicted as positive
- The true positive rate is also known as sensitivity, recall, or probability of detection

## False Positive Rate
- Before we define the false positive rate, we should first introduce some terminology associated with the false positive rate
        - The number of false positives is defined as FP
        - The number of positives is defined as P
        - FP refers to the number of observations that are incorrectly predicted as positive
        - P refers to the number of observations that are positive (i.e. P = TP + FP)
- The false positive rate is defined as FP/P
- In other words, the false positive rate is defined as as number of false positives divided by the total number of positives
- The false positive rate refers to the percentage of observations that are incorrectly predicted as positive
- The false positive rate is also known as type I error or false alarms

## True Negative Rate
- Before we define the true negative rate, we should first introduce some terminology associated with the true negative rate
        - The number of true negatives is defined as TN
        - The number of negatives is defined as N
        - TN refers to the number of observations that are correctly predicted as negative
        - N refers to the number of observations that are negative (i.e. N = TN + FN)
- The true negative rate is defined as TN/N
- In other words, the true negative rate is defined as as number of true negatives divided by the total number of negatives
- The true negative rate refers to the percentage of observations that are correctly predicted as negative
- The true negative rate is also known as specificity or correct rejection

## False Negative Rate
- Before we define the false negative rate, we should first introduce some terminology associated with the false negative rate
        - The number of false negatives is defined as FN
        - The number of negatives is defined as N
        - FN refers to the number of observations that are incorrectly predicted as negative
        - N refers to the number of observations that are negative (i.e. N = TN + FN)
- The false negative rate is defined as FN/N
- In other words, the false negative rate is defined as as number of false negatives divided by the total number of negatives
- The false negative rate refers to the percentage of observations that are incorrectly predicted as negative
- The false negative rate is also known as type II error or miss rate

## Standard Accuracy
- The standard accuracy is defined as (TP + TN)/(P + N), or (TP + TN)/(TP + TN + FP + FN)
- The standard accuracy refers to the percentage of observations that are correctly predicted (out of all the observations)
- A high accuracy indicates a greater predictability (given the model and threshold/parameter values)

## AUC
- Before we introduce the AUC metric, we should first talk about the ROC curve
	- The receiver operating characteristic (or ROC) curve is a curve created by plotting the true positive rate against the false positive rate (with varying parameter values)
	- The ROC curve essentially illustrates the goodness of fit of a binary classifier as its associated parameter values are varied 
- The area under the curve (or AUC) metric refers to the area under the ROC curve
- A high AUC indicates a better model fit (and not a greater predictability)

## References
- https://datascience.stackexchange.com/questions/806/advantages-of-auc-vs-standard-accuracy
- https://en.wikipedia.org/wiki/Receiver_operating_characteristic
- http://gim.unmc.edu/dxtests/roc2.htm
