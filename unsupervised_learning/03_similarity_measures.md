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

## Example using SMC, Jaccard, and Dice Coefficients

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
- Dice = (2M₁₁)/((2M₁₁)+M₀₁+M₀₁) = (2*3)/((2*3)+1+2) = 6/9 = 0.66
	- Where M₀₁ = 1 (from Headache)
	- Where M₁₀ = 2 (from Sex and Sore Throat)
	- Where M₁₁ = 3 (from 25+, Cough, and Chills)

## Euclidean Distance
- The Euclidean distance is a measure of dissimilarity between continuous variables
- The Euclidean distance calculates the ordinary straight-line distance between two points in Euclidean space
- The Euclidean distance can also be referred to as the Pythagorean distance
- A generalized term for the Euclidean norm is the L2 norm
- Specifically, EUC = sqrt(Σ(xᵢ-yᵢ)²)

## Great-Circle Distance
- The great-circle distance (or orthodromic distance) is a measure of dissimilarity between continuous variables
- The great-circle formula calculates the shortest distance between two points on the surface of a sphere
- The Earth is nearly spherical, so the great-circle distance provides an accurate distance between two points on the surface of the Earth  within about 0.5%
- Specifically, GC = rΔσ
	- Where r is the radius of the sphere
	- Where Δσ = arccos(sin(ω₁)sin(ω₂) + cos(ω₁)cos(ω₂)cos(ƛ₂-ƛ₁))
	- Where ƛᵢ is the latitude of point i
	- Where ωᵢ is the longitude of point i

## Haversine Distance
- The haversine distance is a measure of dissimilarity between continuous variables
- The haversine formula calculates the shortest distance between two points on the surface of the Earth
- In other words, the haversine formula calculates the great-circle distance between two points with an adjustment to provide a birds-eye-view  distance between two points
- Obviously, the haversine distance ignores any hills and assumes smooths land
- Specifically, HS = d/r
	- Where r is the radius of the Earth
	- Where d = (2r)arcsin(sqrt(sin²((ƛ₂-ƛ₁)/2) + cos(ƛ₁)cos(ƛ₂)sin²((ω₂-ω₁)/2)))
	- Where ƛᵢ is the latitude (in radians) of point i
        - Where ωᵢ is the longitude (in radians) of point i

## Manhattan Distance
- The Manhattan distance is a measure of dissimilarity between continuous variables
- The Manhattan distance calculates the distance between two points measured along axes at right angles
- A generalized term for the Euclidean norm is the L1 norm
- If the data is high dimensional, the Manhattan distance is usually preferred over the Euclidean distance
- Specifically, MH = Σ(|xᵢ-yᵢ|)

## Cosine Distance
- The cosine distance is a measure of dissimilarity between binary, nominal, or continuous variables
- Specifically, the cosine distance is a measure of dissimilarity between two (and only two) vectors
- The cosine formula calculates the cosine of the angle between the two vectors
- Therefore, the cosine similarity is a measurement of orientation and not magnitude
- Note that even if we had a vector pointing far from another vector, they still could have a small angle
- Specifically, θ = arccos((Σaᵢbᵢ)/‖a‖‖b‖)
	- Where a represents vector a
	- Where b represents vector b
	- Where ‖a‖ = sqrt(Σa²)
	- Where ‖b‖ = sqrt(Σb²)
- Note that the cosine similarity is essentially the same as the euclidean distance on normalized data

## Use-Cases for Euclidean Distance, Manhattan Distance, and Cosine Distance
- The euclidean disance is represented as a distance in the physical world, which is a natural notion of distance
- The euclidean distance is frequently used for finding the nearest hospital for emergency helicopter flights
- The euclidean distance is also used in natural language processing applications
- Specifically, the euclidean distance is calculated with a bag-of-words representation, while normalizing the word count vectors by the euclidean length of words in each document
- The manhattan distance is typically preferred to the euclidean distance for the case of high dimensional data, since it can provide similar distances to the euclidean distance
- The manhattan formula is frequently used for measuring the distances in chess, compressed sensingm and frequency distributions
- The cosine similarity is represented as an angle between two vectors
- The cosine similarity is typically used in natural language processing applications
- Specifically, the cosine similarity is used to measure how similar documents are to each other (irrespective of their size)

## Example using Euclidean and Cosine Distances

| document | car | bike | tire | she | sand | bench | doctor |
|----------|-----|------|------|-----|------|-------|--------|
| 01       | 5   | 0    | 3    | 1   | 0    | 2     | 0      |
| 02       | 3   | 0    | 5    | 0   | 1    | 6     | 0      |

- For this example, we will exclude the document variable from our euclidean, haversine, and cosine calculations
- Euclidean = sqrt(Σ(xᵢ-yᵢ)²) = ((5-3)² + (0-0)² + (3-5)² + (1-0)² + (0-1)² + (2-6)² + (0-0)²) = 4 + 0 + 4 + 1 + 1 + 16 + 0 = 26
- Cosine = arccos((Σaᵢbᵢ)/‖a‖‖b‖) = arccos((15+15+1+1+12)/(sqrt(25+9+1+4)sqrt(9+25+1+36))) = arccos(44/((6.2)(8.4))) = arccos(0.84) = 0.57

## References
- http://staffwww.itn.liu.se/~aidvi/courses/06/dm/lectures/lec9.pdf
- https://www.stat.cmu.edu/~cshalizi/350/2008/lectures/01/lecture-01.pdf
- https://datascience.stackexchange.com/questions/5121/applications-and-differences-for-jaccard-similarity-and-cosine-similarity
- https://stats.stackexchange.com/questions/15287/hierarchical-clustering-with-mixed-type-data-what-distance-similarity-to-use
- https://stats.stackexchange.com/questions/55798/what-is-the-optimal-distance-function-for-individuals-when-attributes-are-nomina/55802#55802
- https://stats.stackexchange.com/questions/99171/why-is-euclidean-distance-not-a-good-metric-in-high-dimensions/99191#99191
- https://stats.stackexchange.com/questions/195006/is-the-dice-coefficient-the-same-as-accuracy
- http://blog.christianperone.com/2013/09/machine-learning-cosine-similarity-for-vector-space-models-part-iii/
- https://www.dataminingapps.com/2016/06/can-you-explain-how-the-jaccard-index-can-be-used-for-distance-calculation/
