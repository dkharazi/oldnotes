## General Description
- An observation (or data entry) can be represented as a vector
- A vector in R3 indicates there are 3 columns with data filled in for our observation
- Therefore, a vector represents a row of data, and the rows of the vector represent the columns of data
- ** come back to this and elaborate **

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
- In other words, a linear combination is a sum of scaled vectors within a vector space
- A linear combination is a mapped output of a sum of scaled vectors from vector space V to somewhere else in that same vector space V
	- A linear combination is a mapped output of a sum of scaled vectors function
	- Specifically, the sum of scaled vectors function refers to f(v)=Σ⍺ᵢvᵢ, where v are the vectors and ⍺ are the scalars
	- For example, our input vectors can be thought of as some English words and our linear combination can be thought of as a different related English word resulting from combining all of those words together
	- In our example, our English words could be "quick", "spotted", and "cat" and our new related English word (i.e. linear combination) could be "cheetah"
        - In this example, the initial English words and resultant English word mean very different things, but are at least represented in the same language so we can understand it (i.e. in the same vector space)
	- The input of the function is a set of vectors from some vector space V
	- The output of the function is the linear combination (of those input vectors) that is also from the same vector space V
	- Therefore, a linear combination just represents some new vector in the same vector space V (as the vector space V of the input vectors)
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

## Span
- The span of two vectors v and w (or spanning set) is the set of all of their linear combinations
- For example, the span (or spanning set) of the two vectors v = [1, 1] and w = [1, -2] makes up R²
- Said another way, the two vectors v = [1, 1] and w = [1, -2] span R²
- We can think of a single vector as a point, a set of vectors as a set of points, a span of a single vector as a line, and a span of a set of vectors as a plane
- Since a one dimensional plane is a line, a span of a one dimensional vector can be thought of as a line

## Basis Vectors
- A set of vectors in a vector space V is a basis if every vector from V can be written in a unique way as a linear combination of vectors of B
- For example, the sets of vectors b = [[2, 0, 0], [0, 5, 0], [0, 0, 4]] and c = [[1, 0, -1], [2, 1, -1], [-2, 1, 4]] are both a basis of R³ because they are linear combinations of [[1, 0, 0], [0, 1, 0], [0, 0, 1]]
- A unit vector is a vector of length 1
- A standard basis is a set of unit unique vectors pointing in each direction of the axes
- There is only one unique set of vectors that can represent its vector space
- For example, the standard basis of R³ is b = [[1, 0, 0], [0, 1, 0], [0, 0, 1]], and the standard basis of R² is b = [[1, 0], [0, 1]]

## Linear Transformation
- A linear transformation is a function that maps vectors from one vector space V to another vector space W while preserving the operations of vector addition and scalar multiplication
- In other words, linear transformations are a way to move around space such that the origin remains fixed and the grid lines remain parallel and evenly spaced
- Mathematically, we define a linear transformation as T:Rⁿ→R⁰
	- Where Rⁿ and R⁰ are different vector spaces
	- Where T is our linear transformation function defined as Ax = b
	- Where x represents our input vector from an initial vector space V
	- Where b represents our transformed vector from a resulting vector space W
- The following are ways we can write the same linear transformation:
	- T:[x₁, x₂]↦[x₁+x₂, 3x₁]
	- T([x₁, x₂]) = [x₁+x₂, 3x₁]
	- T(x₁, x₂) = (x₁+x₂, 3x₁)
- For example, if we have a linear transformation T:[x₁, x₂]↦[x₁+x₂, 3x₁], then:
	- The vector [2, 4] would be linearly transformed to [6, 6]
	- The vector [1, 1] would be linearly transformed to [2, 3]
	- The vector [5, -1] would be linearly transformed to [4, 15]
- Again, a linear transformation is function that maps vectors from one vector space V to another vector space W
        - A linear transformation is a mapped output of a transformation function
        - Specifically, the transformation function refers to f(x)=Ax, where x is a vector and A is the transformation matrix
	- The transformation matrix A represents a translator who only knows how to translate between exactly two vector spaces
	- For example, the transformation matrix A can be thought of as a translator who only knows how to translate English words into French words
	- In this example, the English words and French words mean exactly the same thing, but are just represented differently (in other languages/vector spaces)
	- In this example, the translator has no idea how to translate Spanish (some completely new vector space) into French, and vice versa
        - The input of the function is a vector from some vector space V
        - The output of the function is a transformed vector that is on a completely different vector space W
        - Therefore, a linear transformation just represents what the input vector would look like in a completely different vector space W
- A linear transformation needs to ensure the same requirements as vector spaces:
        - If the zero vector is an element of V (i.e. [0, ..., 0]∈V)
        - If x∈V and y∈V, then x+y∈V
        - If c∈R and x∈V, then cx∈V 
- In summary, the formula for a linear transormation is defined as Ax = b
	- Where x is our vector from an initial vector space
	- Where b is our vector on a transformed vector space
	- Where A is our transormation matrix
	- And A is a matrix representing the set of basis vectors (from our initial vector space) transformed to the new vector space
	- In other words, the transformation matrix A represents our basis vectors from our inital vector space V in the different vector space W
	- Said another way, a linear transformation is completely determined by where it takes the basis vectors of the space

## Linear Dependence
- A set of vectors are linearly dependent when one of the vectors from the set can be defined as a linear combination of the others
- A set of vectors are linearly independent when no other vector from the set can be defined as a linear combination of the other
- Linear dependence represents multicollinearity of two data columns
- We need to ensure linear independence for greater interpretability and data compression purposes
- Rules of linear dependency in an Rⁿ vector space (n number of dimensions and m number of vectors)
        - If n < m, then the set of vectors can span Rⁿ, but can't be linearly independent
        - If n = m, then the set of vectors can span Rⁿ, and can be linearly independent
        - If n > m, then the set of vectors can't span Rⁿ, but can be linearly independent
- We need to check for linear dependency in our linear transformations
	- If our transformation matrix A has linear dependent columns, then one of the vectors (from the transformation matrix) is a scaled version of the other
	- In other words, if our transformation matrix A is a two dimensional matrix with linearly dependent columns, then the linear transformation squishes all of the 2D space onto the line (i.e. lower dimension) where those two vectors sit (also known as the one dimensional span of those two linearly dependent vectors)
	- In general, we can actually think of every matrix as a transformation of space (which is a core element of linear algebra)

## Determinant
- The determinant is a scaling factor by which a linear transformation changes any area
- The following are some examples of a determinant:
	- The determinant of a transformation would be 3 if that transformation increases the area of the region by a factor of 3
	- The determinant of a transformation would be 1/2 if that transformation squishes down all areas by a factor of 1/2
	- The determinant of a transformation would be 0 if that transformation squishes all of space onto a line (or even a single point)
		- This is because the area of any region in the resulting vector space would become 0
- The following are some properties of a determinant:
	- The determinant's value represents the magnitude by which areas have been scaled
	- The determinant's sign represents the orientation (or direction) by which areas have been scaled
- In 2D spaces, the determinant represents the scaling factor by which a linear transformation changes any area
- In 3D (or greater) spaces, the determinant represents the scaling factor by which a linear transformation changes any volume
- As we now know, the determinant is derived from a linear transformation
- The determinant of a matrix A is denoted det(A)
- The determinant of a 2D transformation matrix can be solved using the following equation:
	- det([a b c d]) = ad - bc
	- Where [a b c d] represents our transformation matrix
	- Where a and d represent how much the basis vectors are stretched, roughly speaking (refers to magnitude)
	- Where b and c represent how much the area (made up by the stretched basis vectors) is stretched in the diagonal direction, roughly speaking (refers to orientation)

## Inverse Matrix
- An inverse matrix A⁻¹
- In English, an inverse matrix (with respect to linear transformations) can be thought of as playing the transformation matrix in reverse
- An inverse matrix represents its own linear transformation (that only reverses the linear transformation made by A)
- This is why A multipled by A⁻¹ equals the identity matrix
- For example, if A transforms a vector from vector space V to a vector space W, where vector space W is 90° clockwise rotation of vector space V:
	- A = [0, -1, 1, 0]
	- Then, A⁻¹ = [0, 1, -1, 0]
	- Meaning, A⁻¹ maps vectors from vector space V to a vector space W, where vector space W is a 90° counterclockwise rotation of vector space V
- In general, A⁻¹ is the unique transformation where multiplying a vector by A⁻¹ and A will get you back to the same vector
- As long as the determinant of a transformation matrix is non-zero, then there will always be an inverse matrix A⁻¹

## System of Linear Equations
- A system of linear equations is a collection of one or more linear equations involving the same set of variables
- In linear algebra, we are typically representing a system of linear equations as a linear transformation Ax = b
- As stated previously, a linear transformation is defined as Ax = b
	- Where A represents our transformation matrix
	- Where x represents our input vector from an initial vector space V
	- Where b represents our transformed vector from a resultant vector space W
- We can use this system of linear equations (i.e. Ax = b) for two purposes:
	1. Solving for our transformed vector b
		- We typically want to solve for a transformed vector b if we want to see what some vector from our current vector space looks like on a different vector space
		- To do this, we need to have a vector x from some initial vector space V, and we need to know our transformation matrix A so that we can map vectors from the initial vector space V to a different vector space W
		- Once we have these variables, we can solve for b by just plugging in our A and x into the formula (i.e. multiplying A and x together)
	2. Solving for our initial vector x
		- We typically want to solve for a vector x if we want to see what some transformed vector looks like on our initial vector space
		- To do this, we need to have a transformed vector b from our new vector space W, we need to know our transformation matrix A so that we know how initial vectors were mapped to a different vector space in the first place, and we need to know the inverse of our transformation matrix A⁻¹ so that we know how transformed vectors are mapped back to its initial vector space
		- Once we have these variables, we can solve for x by just plugging in our A and b into the formula, then multiplying each side by the invese matrix A⁻¹ (to isolate x on its own side)
		- Multiplying each side by the inverse matrix is almost like the matrix form of dividing each side by a constant (i.e. 2) in the following formula: y = 2x, if we want to solve for x

## Nonsquare Matrices as Transformations between Dimensions
- If our transformation matrix is a 3-by-2 matrix, then we are mapping two dimensional vectors to three dimensional vectors
- In other words, we are mapping vectors from a two dimensional vector space to a three dimensional vector space if our transformation matrix is a 3-by-2 matrix
- Similarly, if our transformation matrix is a 2-by-3 matrix, then we are mapping three dimensional vectors to two dimensional vectors
- In other words, we are mapping vectors from a three dimensional vector space to a two dimensional vector space if our transformation matrix is a 2-by-3 matrix
- Obviously, this concept doesn't only apply to 3-by-2 and 2-by-3 matrics, but any other nonsquare matrices as well

## Dot Products and Duality
- If you have two vectors of the same dimension (i.e. two lists of numbers with the same length), then taking their dot product has the following numerical definition:
	1. First, pairing up all of their coordinates
	2. Then, multiplying those pairs together
	3. Then, adding those multiplied pairs together
- Here are some examples of calculating the vector dot products:
	- dotprod([1, 2], [3, 4]) = (1x3) + (2x4) = 11
	- dotprod([6, 2, 8, 3], [1, 8, 5, 3]) = (6x1) + (2x8) + (8x5) + (3x3) = 71
- We can take the numerical definition of a dot product from above, and translate it to a more intuitive geometric interpretation:
	1. Pairing up all of their coordinates looks like ...

## Matrix Multiplication, Dot Products, Linear Combinations, and Linear Transformations

## Change of Basis

## Eigenvectors
- 

## Eigenvalues

## References
- http://www.math.harvard.edu/archive/20_spring_05/handouts/ch05_notes.pdf
- https://math.stackexchange.com/questions/668/whats-an-intuitive-way-to-think-about-the-determinant
- https://en.wikipedia.org/wiki/Determinant
