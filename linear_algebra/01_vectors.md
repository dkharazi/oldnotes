## Motivating Vectors using Data
- An observation (or data entry) can be represented as a vector
- The following are descriptions of example vectors:
	- A vector in R² represents an observation (or data entry) with two columns
	- A vector in R³ represents an observation (or data entry) with three columns
	- A vector in R⁵ represents an observation (or data entry) with five columns
- The following are more intuitive descriptions of the above examples:
	- Each observation in a table with two columns can be represented as a two dimensional vector (i.e. a vector in the vector space R²)
	- Each observation in a table with three columns can be represented as a three dimensional vector (i.e. a vector in the vector space R³)
	- Each observation in a table with five columns can be represented as a five dimensional vector (i.e. a vector in the vector space R⁵)
- In other words, a vector represents a row of data (not usually a column of data)

## Different Perspectives of Vectors
- There is the physics perspective of vectors
	- Vectors are arrows pointing in space
	- Vectors are defined by their length and direction
	- Position doesn't really matter
	- In other words, if two vectors with the same direction and length are positioned differently, then they are classified as the same vector
- There is the computer science perspective of vectors
	- Vectors are ordered lists of numbers
	- In other words, the first number refers to one variable, the second number refers to the second variable, etc.
	- The length of vectors are associated with its dimensionality (i.e. 2D vector has a length of 2)
- There is the mathematician perspective of vectors
	- The mathematician's perspective tries to generalize both perspectives, since there is a lot of overlap between the two (i.e. they are both essentially saying the same thing)
	- A vector can be anything where there's a sensible notion of adding two vectors and multiplying a vector by a numbers
	- Multiplying a vector by a number is the same thing as changing the magnitude and direction of a vector
	- Adding vectors together is also the same thing as changing the magnitude and direction of a vector
	- The mathematician's perspective differs from the physic's perspective of vectors, since mathematician's believe vectors can't freely sit anywhere
	- Instead, they believe vectors should be positioned at the origin
	- Mathematicians also don't really think about vectors as arrows or forces, they really just think of them as positions in relation to some origin
- We will use the mathematician's perspective of vectors

## The Essence of Vectors
- A vector is a geometric object that has a magnitude and direction
- More specifically, a vector is a point in relation to a given origin (default origin point is (0,0) in a Cartesian coordinate system)
- Said another way, a vector tells us where our data point is in relation to the origin (of our vector space)
- As stated previously, mathematicians believe that vectors can be anything as long as there us a sensible notion of adding them and multiplying them together
- Roughly speaking, a vector has the following properties:
        - Almost always sits in a coordinate system
        - Has a length and direction
        - Is rooted at the origin
- Each vector represents a movement in space
- When we add vectors together, we're adding how much they move us in the directions represented by the numbers
- This is why the resultant vector (from vector addition) can be considered as the movement between the tail of the first vector to the head of the other vector (order does not matter)
- On the other hand, multiplying by a number means that we're scaling the magnitude of a vector
- If the number is negative, we're reversing the direction of the vector

## Vector Spaces
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

## Subspaces
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

## References
- https://www.youtube.com/watch?v=fNk_zzaMoSs&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab&index=2&t=402s
- http://www.supermath.info/LinearnotestoSec5p3.pdf
- https://en.wikipedia.org/wiki/Linear_subspace
- http://www.math.niu.edu/~beachy/courses/240/06spring/vectorspace.html
- https://events.csa.iisc.ac.in/summerschool2017/wp-content/uploads/slides/7.pdf
- https://steemit.com/mathematics/@drifter1/mathematics-linear-algebra-vector-spaces
