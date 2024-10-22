## General Description
- A linear transformation is a function that maps vectors from one vector space V to another vector space W while preserving the operations of vector addition and scalar multiplication
- In general, linear transformations have the following properties:
	- The origin remains fixed once the vector space is transformed
	- The underlying grid lines remain parallel
	- The underlying grid lines remain evenly spaced
- A vector is simply a linear combination of its standard basis vectors
- If we linearly transform that vector, then that transformed vector will end up as that same linear combination of the standard basis vectors
- Therefore, the only difference between the vectors is the scale of the standard basis vectors (i.e. the standard basis vectors in the transformed space are scaled differently than the standard basis vectors in the original space)

## Defining a Linear Transformation
- Mathematically, a linear transformation is defined as Ax = b
	- Where A is our transformation matrix
		- A transformation matrix is a basis of our original vector space W
		- More specifically, a transformation matrix is a set of vectors from our original vector space that represent the unit vectors of the new vector space
	- Where x is our scaled vector from the vector space V defined by our transformation matrix
	- Where b is our vector from the original vector space
- Essentially, if we linearly scale every vector (in our original space) around the transformation matrix A, then the scaled vector x in that space will translate to vector b in our original space
- In other words, as long as we know which vectors from our original space translate to the standard basis vectors in the new space (this is what the transformation matrix does), then we are able to translate any vector from that new space back to a vector in our original space

## Abstract Analogy of Linear Transformation
- Let's assume that we only understand English
- The transformation matrix can be thought of as a translator who only knows how to translate French words into English words
- Therefore, if we give the translator any French word, they will be able to give us the English translation
- For this analogy to have any meaning, we should assume the following:
	- English words and French words have an exact translation that are identical in meaning
	- The translator has no idea how to translate English to French, Spanish to English, or any other translation besides French to English
- In this analogy, the translator represents a transformation matrix A, a French word given to the translator represents vector x, and an English word translated by the translator represents vector b

## Examples and Notation of Linear Transformations
- The following are ways we can write the same linear transformation:
        - T:[x₁, x₂]↦[x₁+x₂, 3x₁]
        - T([x₁, x₂]) = [x₁+x₂, 3x₁]
        - T(x₁, x₂) = (x₁+x₂, 3x₁)
- For example, if we have a linear transformation T:[x₁, x₂]↦[x₁+x₂, 3x₁], then:
        - The vector [2, 4] would be linearly transformed to [6, 6]
        - The vector [1, 1] would be linearly transformed to [2, 3]
        - The vector [5, -1] would be linearly transformed to [4, 15]

## Assumptions of Linear Transformations
- A linear transformation needs to ensure the same requirements as vector spaces:
        - If the zero vector is an element of V (i.e. [0, ..., 0]∈V)
        - If x∈V and y∈V, then x+y∈V
        - If c∈R and x∈V, then cx∈V

## Linear Dependence
- A set of vectors are linearly dependent when one of the vectors from the set can be defined as a linear combination of the others
- Conversely, a set of vectors are linearly independent when no other vector from the set can be defined as a linear combination of the others
- The following are some rules related to linear dependence in an Rⁿ vector space (with n number of dimensions and m number of vectors):
	- If n < m, then the set of vectors can span Rⁿ, but can't be linearly independent
        - If n = m, then the set of vectors can span Rⁿ, and can be linearly independent
        - If n > m, then the set of vectors can't span Rⁿ, but can be linearly independent
- If our transformation matrix has linear dependent columns, then one of those columns is a scaled version of the other
- In other words, if our transformation matrix has linearly dependent columns, then the linear transformation squishes all of the original vector space onto a lower dimension
- For example, If our transformation matrix is a two dimensional matrix with linearly dependent columns, then the linear transformation squishes all of the 2D space onto a line where those two vectors sit, which is also just a one dimensional span of those two linearly dependent vectors
- In data analysis, linear dependence represents multicollinearity of two data columns
- We need to ensure linear dependence for greater interpretability and data compression reasons

## Transforming Nonsquare Matrices
- If our transformation matrix is a 3-by-2 matrix, then we are mapping two dimensional vectors to three dimensional vectors
- In other words, we are mapping vectors from a two dimensional vector space to a three dimensional vector space if our transformation matrix is a 3-by-2 matrix
- Similarly, if our transformation matrix is a 2-by-3 matrix, then we are mapping three dimensional vectors to two dimensional vectors
- In a general sense, if our transformation matrix is a x-by-y matrix, then we are mapping y dimensional vectors to x dimensional vectors (and vice versa)

## References
- https://www.youtube.com/watch?v=kYB8IZa5AuE&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab&index=3
