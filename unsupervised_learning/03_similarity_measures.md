## General Description
- Sometimes, we want to determine how similar two data entries are compared to each other
- To do this, we need to have some way of measuring similarity between those two entries
- Therefore, we use dissimilarity or distance measures
- Simple matching coefficients (SMC) and jaccard coefficients are calculated on binary data values
- Euclidean distances and cosine distances are calculated on continuous data values

## Simple Matching Coefficient
- The simple matching coefficient (or SMC) is a measure of dissimilarity between binary variables
- The SMC calculates the percentage of mutual presences and mutual absences between the variable values
- Specifically, SMC = (M₀₀+M₁₁)/(M₀₀+M₀₁+M₁₀+M₁₁)
	- Where M₀₀ is the number of matching False values between two data entries
	- Where M₁₁ is the number of matching True values between two data entries
	- Where M₁₀ is the number of differing values where the first entry's value is True and the second entry's value is False
	- Where M₀₁ is the number of differing values where the first entry's value is False and the second entry's value is True

## Jaccard Coefficient
- The Jaccard similarity coefficient is a measure of dissimilarity between binary variables
- The Jaccard coefficient calculates the percentage of mutual presences between the variable values
- Specifically, Jaccard = (M₁₁)/(M₀₁+M₁₀+M₁₁)
	- Where M₁₁ is the number of matching True values between two data entries
        - Where M₁₀ is the number of differing values where the first entry's value is True and the second entry's value is False
        - Where M₀₁ is the number of differing values where the first entry's value is False and the second entry's value is True
- The Jaccard coefficient can be thought of as a generalized case of the SMC

## Dice Coefficient
- The Dice coefficient is a measure of dissimilarity between nominal variables
- The Dice coefficient calculates the percentage of mutual presences between the variable values (with mutual absenses)
- Specifically, Dice = (2*J)/(1+J)
	- Where J is the Jaccard coefficient
- Therefore, the Dice coefficient is very similar to the Jaccard coefficient, but the Dice coefficient doesn't account for true negatives
- The Dice coefficient is used in NLP, specifically when using a bag-of-words approach

## Use-Cases for SMC and Jaccard Coefficients
- The SMC coefficient is used for symmetrical binary variables, meaning the two classes associated with the binary variables are thought to have equal importance
- On the other hand, the Jaccard coefficient is typically used for assymetrical binary variables, meaning the two classes associated with the binary variables are thought to have different importances
- However, the Jaccard coefficient can also be used for symmetrical binary variables
- It's important to note that we can transform multi-class categorical variables into many separate binary variables so that we can calculate SMC or Jaccard coefficients on the data entry
- Since the SMC is used for symmetrical binary variables, the SMC is typically used to detect cheating on two different exams
- Since the Jaccard coefficient is used for asymmetrical binary variables, the Jaccard coefficient is typically used to detect fraud between two different documents
- Therefore, the Jaccard coefficient is typically used when we have many False values (or TN) that we don't want to account for in our similarity calculation

## Example of SMC and Jaccard Calculations

| id | Sex    | 25+ | Cough | Fever | Chills | Headache | Sore Throat |
|----|--------|-----|-------|-------|--------|----------|-------------|
| 01 | Female | Yes | Yes   | No    | Yes    | No       | Yes         |
| 02 | Male   | Yes | Yes   | No    | Yes    | Yes      | No          |

- For this example, we will exclude the id variable from our SMC and Jaccard calculations
- SMC = (M₀₀+M₁₁)/(M₀₀+M₀₁+M₁₀+M₁₁) = (1+2)/(1+1+2+3) = 3/7 = 0.43
	- Where M₀₀ = 1 (from Fever)
	- Where M₀₁ = 1 (from Headache)
	- Where M₁₀ = 2 (from Sex and Sore Throat)
	- Where M₁₁ = 3 (from 25+, Cough, and Chills)
- Jaccard = (M₁₁)/(M₀₁+M₁₀+M₁₁) = (3)/(1+2+3) = 3/6 = 0.5
	- Where M₀₁ = 1 (from Headache)
	- Where M₁₀ = 2 (from Sex and Sore Throat)
	- Where M₁₁ = 3 (from 25+, Cough, and Chills)
- Dice = (2*M₁₁)/((2*M₁₁)+M₀₁+M₀₁) = (2*3)/((2*3)+1+2) = 6/9 = 0.66
	- Where M₀₁ = 1 (from Headache)
	- Where M₁₀ = 2 (from Sex and Sore Throat)
	- Where M₁₁ = 3 (from 25+, Cough, and Chills)

## Euclidean Distance

## Cosine Similarity

## References
- http://staffwww.itn.liu.se/~aidvi/courses/06/dm/lectures/lec9.pdf
- https://www.stat.cmu.edu/~cshalizi/350/2008/lectures/01/lecture-01.pdf
- https://datascience.stackexchange.com/questions/5121/applications-and-differences-for-jaccard-similarity-and-cosine-similarity
- https://stats.stackexchange.com/questions/15287/hierarchical-clustering-with-mixed-type-data-what-distance-similarity-to-use
- https://stats.stackexchange.com/questions/55798/what-is-the-optimal-distance-function-for-individuals-when-attributes-are-nomina/55802#55802
- https://stats.stackexchange.com/questions/195006/is-the-dice-coefficient-the-same-as-accuracy
- https://www.dataminingapps.com/2016/06/can-you-explain-how-the-jaccard-index-can-be-used-for-distance-calculation/
- https://dataaspirant.com/2015/04/11/five-most-popular-similarity-measures-implementation-in-python/
- https://www.datanovia.com/en/lessons/clustering-distance-measures/
