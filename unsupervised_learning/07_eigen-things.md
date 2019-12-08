## General Description

## Vector
- A vector is a geometric object that has a magnitude and direction
- More specifically, a vector is a point in relation to a given origin (default origin point is (0,0) in a Cartesian coordinate system)
- Said another way, a vector tells us where our data point is in relation to the origin (of our vector space)
- Mathematicians believe that vectors can be anything as long as there us a sensible notion of adding them and multiplying them together
- Roughly speaking, a vector has the following properties:
	- Almost always sits in a coordinate system
	- Has a length and direction
	- Is rooted at the origin
- Each vector represents a movement in space
- When we add vectors together, we're adding how much they move us in the directions represented by the numbers
- This is why the resultant vector (from vector addition) can be considered as the movement between the tail of the first vector to the head of the other vector (order does not matter)
- On the other hand, multiplying by a number means that we're scaling the magnitude of a vector
- If the number is negative, we're reversing the direction of the vector

## Vector Space
- A vector space is a set of vectors V that has two operations + (vector addition) and · (scalar multiplication)
- A vector space puts some contraints on its set of vectors so these two operations can be used correctly
- The + operation requires the following to be true about any vector u and any vector v in its set of vectors V:
	- If u and v are any vectors in V, then the sum u+v belongs to V
- The · operation requires the following to be true about any vector u and any vector v in its set of vectors V:
	- If v is any vector in V and c is any real number, then the product cv belongs to V
- For example, we can think of the set of real numbers (i.e. R or R¹) as a vector space over itself
	- The sum of any two real numbers is a real number (i.e. u+v=V)
	- A scalar (also a real number) multiplied by a real number is another real number (i.e. cv=V)
	- Therefore, we can think of c as a one-dimensional vector

## Subspace
- A subspace is a subset (i.e. W) of a vector space (i.e. V)
- Therefore, a subspace needs to also satisfy the above conditions for vector addition and scalar multiplication
- In other words, a set of vectors is a subset of Vⁿ if they are elements of the nth dimension of V
- Again, a set of vectors is a subspace of Vⁿ if all of the following conditions (from a vector space) are true:
        - If the zero vector is an element of W (i.e. [0, ..., 0]∈W)
	- If x∈W and y∈W, then x+y∈V
        - If c∈R and x∈W, then cx∈V 
- For example, if we let our subspace W be the real coordinate space R³ and our vector space be V:
	- Then x∈R³ and y∈R³ can be expressed as x = (0, x1, x2, ..., xn) and w = (0, y1, y2, ..., yn), and x+y = (0+0, x1+y1, x2+y2, ..., xn+yn), then x+y should be an element of the initial vector space V, as well
	- Then x∈R³ and c∈R can be expressed as x = (0, x1, x2, ..., xn) and c = c, and cx = (0, cx1, cx2, ..., cxn), then xc should be an element of the initial vector space V, as well

## Linear Combination
- A linear combination (of a set of vectors) is a vector representing any combination of the set of vectors using vector addition or scalar multiplication
- The "linear" part of "linear combination" refers to scalar multiplication
	- Specifically, it comes from linearly scaling a vector to output another vector
	- In other words, the resultant vector represents a scaled version of a vector
	- As a reminder, linear scaling refers to multiplying constants by a vector (or variable in the general sense)
- The "combination" part of "linear combination" refers to vector addition
	- Specifically, it comes from adding vectors together to output another vector
	- In other words, the resultant vector represents a (added) combination of a set of other vectors
- For example, if we have vectors v₁ = [1, 2, 3], v₂ = [3, 5, 1], and v₃ = [0, 0, 8], then:
	- The vector b = [3, 6, 9] is a linear combination of [v₁, v₂, v₃] because [3, 6, 9] = 3[1, 2, 3] + 0[3, 5, 1] + 0[0, 0, 8]
	- The vector b = [3, 6, 17] is a linear combination of [v₁, v₂, v₃] because [3, 6, 17] = 1[1, 2, 3] + 0[3, 5, 1] + 1[0, 0, 8]
	- The vector b = [9, 16, 11] is a linear combination of [v₁, v₂, v₃] because [9, 16, 11] = 3[1, 2, 3] + 2[3, 5, 1] + 0[0, 0, 8]
	- The vector b = [1, 2, 3] is a linear combination of [v₁, v₂, v₃] because [1, 2, 3] = 1[1, 2, 3] + 0[3, 5, 1] + 0[0, 0, 8]

## Basis Vectors
- A set of vectors in a vector space V is a basis if every vector from V can be written in a unique way as a linear combination of vectors of B
- For example, the sets of vectors b = [[2, 0, 0], [0, 5, 0], [0, 0, 4]] and c = [[1, 0, -1], [2, 1, -1], [-2, 1, 4]] are both a basis of R³ because they are linear combinations of [[1, 0, 0], [0, 1, 0], [0, 0, 1]]
- A unit vector is a vector of length 1
- A standard basis is a set of unit unique vectors pointing in each direction of the axes
- There is only one unique set of vectors that can represent its vector space
- For example, the standard basis of R³ is b = [[1, 0, 0], [0, 1, 0], [0, 0, 1]], and the standard basis of R² is b = [[1, 0], [0, 1]]

## Linear Dependence
- The span of two vectors v and w (or spanning set) is the set of all of their linear combinations
- For example, the span (or spanning set) of the two vectors v = [1, 1] and w = [1, -2] makes up R²
- Said another way, the two vectors v = [1, 1] and w = [1, -2] span R²
- We can think of a vector as a point, a set of vectors as a set of points, and a span of a set of vectors as a plane
	- Since a one dimensional plane is a line, a span of a one dimensional vector can be thought of as a line
- A set of vectors are linearly dependent when one of the vectors from the set can be defined as a linear combination of the others
- A set of vectors are linearly indpendent when no other vector from the set can be defined as a linear combination of the other
- Linear dependence represents multicollinearity of two data columns
- We need to ensure linear independence for greater interpretability and data compression purposes
- Rules of linear dependency in an Rⁿ vector space (n number of dimensions and m number of vectors)
	- If n < m, then the set of vectors can span Rⁿ, but can't be linearly independent
	- If n = m, then the set of vectors can span Rⁿ, and can be linearly independent
	- If n > m, then the set of vectors can't span Rⁿ, but can be linearly independent

## Eigenvectors

## Eigenvalues

## References
- https://en.wikipedia.org/wiki/Linear_subspace
- http://www.math.harvard.edu/archive/20_spring_05/handouts/ch05_notes.pdf
- http://www.math.niu.edu/~beachy/courses/240/06spring/vectorspace.html
- https://events.csa.iisc.ac.in/summerschool2017/wp-content/uploads/slides/7.pdf
- https://www.mathbootcamps.com/linear-combinations-vectors/
- https://steemit.com/mathematics/@drifter1/mathematics-linear-algebra-vector-spaces
- https://www.youtube.com/playlist?list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab
