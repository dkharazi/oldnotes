## Linear Combination
- A linear combination (of a set of vectors) is a vector representing any combination of the set of vectors using vector addition or scalar multiplication
- In other words, a linear combination is a sum of scaled vectors within a vector space
- More specifically, a linear combination is a mapped output of a sum of scaled vectors from vector space V to somewhere else in that same vector space V
- As stated previously, a linear combination is a mapped output of a sum of scaled vectors function
- Specifically, the sum-of-scaled-vectors function refers to f(v)=Σ⍺ᵢvᵢ, where v are the vectors, ⍺ are the scalars, and f(v) is our linear combination
- The input of the function is a set of vectors from some vector space V
- The output of the function is the linear combination (of those input vectors) that is also from the same vector space V
- Therefore, a linear combination just represents some new vector in the same vector space V (as the vector space V of the input vectors)

## An Abstract Example of Linear Combinations
- Very roughly speaking, our input vectors can be thought of as some English words and our linear combination can be thought of as a different related English word resulting from combining all of those words together
- In our example, our English words could be "quick", "spotted", and "cat" and our new related English word (i.e. linear combination) could be "cheetah"
- In this example, the initial English words and resultant English word mean very different things, but are at least represented in the same language so we can understand it (i.e. in the same vector space)
- Similar to how the input of our sum-of-scaled-vectors function is a set of vectors from the vector space V, our input is a set of words from the English language (i.e. vector space represents all languages, and our specific vector space is English)
- Similar to how the output of our sum-of-scaled-vectors function is a linear combination (of those input vectors) that is also from the same vector space V, our output is also an English word
- Therefore, our linear combination in this very abstract example represents some new word that remains English

## Where does Linear Combination Get its Name
- The "linear" part of "linear combination" refers to scalar multiplication
	- Specifically, it comes from linearly scaling a vector to output another vector
	- In other words, the resultant vector represents a scaled version of a vector
	- As a reminder, linear scaling refers to multiplying constants by a vector (or variable in the general sense)
- The "combination" part of "linear combination" refers to vector addition
	- Specifically, it comes from adding vectors together to output another vector
	- In other words, the resultant vector represents a (added) combination of a set of other vectors

## Example of Linear Combinations
- Let's say we have vectors v₁ = [1, 2, 3], v₂ = [3, 5, 1], and v₃ = [0, 0, 8]
- The vector b = [3, 6, 9] is a linear combination of [v₁, v₂, v₃] because [3, 6, 9] = 3[1, 2, 3] + 0[3, 5, 1] + 0[0, 0, 8]
- The vector b = [3, 6, 17] is a linear combination of [v₁, v₂, v₃] because [3, 6, 17] = 1[1, 2, 3] + 0[3, 5, 1] + 1[0, 0, 8]
- The vector b = [9, 16, 11] is a linear combination of [v₁, v₂, v₃] because [9, 16, 11] = 3[1, 2, 3] + 2[3, 5, 1] + 0[0, 0, 8]
- The vector b = [1, 2, 3] is a linear combination of [v₁, v₂, v₃] because [1, 2, 3] = 1[1, 2, 3] + 0[3, 5, 1] + 0[0, 0, 8]

## Span
- The span of two vectors v and w (or spanning set) is the set of all of their linear combinations
- For example, the span (or spanning set) of the two vectors v = [1, 1] and w = [1, -2] makes up R²
- Said another way, the two vectors v = [1, 1] and w = [1, -2] span R²
- We can think of a single vector as a point, a set of vectors as a set of points, a span of a single vector as a line, and a span of a set of vectors as a plane
- Since a one dimensional plane is a line, a span of a one dimensional vector can be thought of as a line

## Basis Vectors
- A set of vectors in a vector space V is a basis if every vector from V can be written in a unique way as a linear combination of vectors of B
- A unit vector is a vector of length 1
- A standard basis is a set of unit unique vectors pointing in each direction of the axes
- A standard basis is one of many possible bases for some vector space V
- The following are some examples of bases:
	- A basis of R³ is b = [[1, 1, 0], [0, 2, -1], [1, 0, 3]] because it is a linear combination of [[1, 0, 0], [0, 1, 0], [0, 0, 1]]
	- A basis of R³ is b = [[2, 0, 0], [0, 5, 0], [0, 0, 4]] because it is a linear combination of [[1, 0, 0], [0, 1, 0], [0, 0, 1]]
	- A basis of R³ is b = [[1, 0, -1], [2, 1, -1], [-2, 1, 4]] because it is a linear combination of [[1, 0, 0], [0, 1, 0], [0, 0, 1]]
	- A basis of R³ is b = [[1, 0, 0], [0, 1, 0], [0, 0, 1]] because it is a linear combination of [[1, 0, 0], [0, 1, 0], [0, 0, 1]]
- The following are some examples of standard bases:
	- The standard basis of R³ is b = [[1, 0, 0], [0, 1, 0], [0, 0, 1]]
	- The standard basis of R² is b = [[1, 0], [0, 1]]

## References
- https://www.youtube.com/watch?v=k7RM-ot2NWY&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab&index=2
- https://www.mathbootcamps.com/linear-combinations-vectors/
