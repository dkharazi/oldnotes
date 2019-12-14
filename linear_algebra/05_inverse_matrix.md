## General Description
- The inverse of a matrix A is a matrix which results in the identity matrix when multiplied by A
- Mathematically, the inverse matrix A⁻¹ is the matrix that satisfies the following equation:
	- AA⁻¹ = I
- In other words, an inverse matrix can be thought of the matrix that plays the transformation matrix in reverse
- An inverse matrix is a transformation matrix in itself

## Examples with Inverse Matrix
- Let our transformation matrix represent a 90° clockwise rotation of a vector space
	- Then, A = [[0, -1], [1, 0]]
	- Thus, A⁻¹ = [[0, 1], [-1, 0]]
	- Here, A⁻¹ represents a 90° counterclockwise rotation of a vector space
- Let our transformation matrix represent a rightward shear of a vector space
	- Then, A = [[1, 0], [1, 1]]
	- Thus, A⁻¹ = [[1, 0], [-1, 1]]
	- Here, A⁻¹ represents a leftward shear of a vector space

## System of Linear Equations
- A system of linear equations is a collection of one or more linear equations involving the same set of variables
- In linear algebra, we are typically representing a system of linear equations as a linear transformation Ax = b
- We can use this system of linear equations (i.e. Ax = b) for two purposes:
        1. Solving for our vector b from the original vector space
		- We typically want to solve for b if we want to see what some vector from a transformed vector space looks like in our original vector space
                - To do this, we need the following:
			- Vector x from the transformed space
			- Transformation matrix A so that we can map vectors from the transformed vector space back to our original vector space
                - Once we have these variables, we can solve for b by just plugging in our A and x into the formula (i.e. multiplying A and x together)
        2. Solving for our initial vector x
                - We typically want to solve for x if we want to see what some vector from our original vector space looks like in a transformed vector space
                - To do this, we need the following:
			- Vector b from our original vector space
			- The inverse of the transformation matrix A⁻¹ so that we can map vectors from our original vector space to the transformed vector space
		- Once we have these variables, the equation Ax = b becomes x = bA⁻¹ by multiplying each side by A⁻¹
		- Then, we can solve for x by just plugging in our A⁻¹ and b into the formula (i.e. multiplying A⁻¹ and b together)

## Solving for the Inverse Matrix
- The inverse of a square matrix A can be defined as (1/(det(A)))[[d, -c], [-b, a]]
- There won't be an inverse of a matrix if the determinant of that matrix is 0

## References
- https://www.youtube.com/watch?v=uQhTuRlWMxw&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab&index=7
