## Motivating Change of Bases
- If I have the vector [3, 2] sitting in a 2D space, we usually think of these coordinates as scalars
- Specifically, we think of these scalars as scaling the standard basis vectors
- In this example, we think of the first coordinate 3 as a number that scales the x-axis unit vector, while the second coordinate 2 is a number that scales the y-axis unit vector
- Therefore, we can think of these two special unit vectors as encapsulating all of the implicit assumptions of our coordinate system
- A way to translate between vectors and a set of numbers is called a coordinate system
- As stated previously, these two special unit vectors are called the (standard) basis vectors of our standard coordinate system

## More on Basis Vectors
- There are many different basis vectors in different coordinate systems, but they are all thought of the same in their own coordinate system (i.e. [1, 0], [1, 0, 0], [0, 1], etc.)
- The only difference is their transformation (or mapping) between coordinate systems
- In other words, every pair of basis vectors may look different across different coordinate systems
- However, every pair of basis vectors will look the same within a coordinate system, since basis vectors simply define the meaning of the coordinates [1,0] and [0,1] (or greater) in each world

## Example of Different Basis Vectors
- Let's say Jennifer and I define two different coordinate systems
- Therefore, Jennifer uses a different set of basis vectors compared to us
- Let's label Jennifer's basis vectors as b1 and b2 and our basis vectors as v1 and v2
- In Jennifer's coordinate system, she refers to her basis vectors as [1, 0] and [0, 1], and she refers to our basis vectors as [1/3, -1/3] and [1/3, 2/3]
- In our coordinate system, we refer to our basis vectors as [1, 0] and [0, 1], and we refer to Jennifer's basis vectors as [2, 1] and [-1, 1]
- In our coordinate system, we may observe a vector [3, 2], which Jennifer would see as [5/3, 1/3] in her coordinate system
- The origin is the same between our coordinate systems

## How Jennifer translates to our Coordinate System
- If we know Jennifer's basis vectors from our perspective and a vector in her coordinate system, then we can use matrix multiplication to translate that vector from her coordinate system to our coordinate system
- For example, suppose we know the following:
	- Jennifer's basis vectors [1, 0] and [0, 1] from her coordinate system translate to [2, 1] and [-1, 1] in our coordinate system
	- A vector [-1, 2] from Jennifer's coordinate system
- Then, we can translate that vector to our coordinate system by plugging in those values to the equation Ax=b
- As a result, [[2, 1], [-1, 1]] x [-1, 2] = [-4, 1]
	- Where [[2, 1], [-1, 1]] is our transformation matrix A
	- Where [-1, 2] is our vector from her coordinate system x
	- Where [-4, 1] is that vector in our coordinate system b
- We can see a matrix whose columns represent some set of basis vectors represents a linear transformation

## How we Translate to Jennifer's Coordinate System
- If we know our basis vectors from Jennifer's perspective and a vector in our coordinate system, then we can use matrix multiplication to translate that vector from our coordinate system to her coordinate system
- For example, we know the following:
	- Jennifer's basis vectors [1, 0] and [0, 1] from her coordinate system translate to [2, 1] and [-1, 1] in our coordinate system
	- A vector [3, 2] from our coordinate system
- Then, we can translate that vector to Jennifer's coordinate system by first finding the inverse of Jennifer's basis vectors, then plugging in thos values to the equation x=A⁻¹b
- As a result, [[1/3, -1/3], [1/3, 2/3]] x [3, 2] = [5/3, 1/3]
	- Where [[1/3, -1/3], [1/3, 2/3]] is the inverse of our transformation matrix A⁻¹
	- Where [3, 2] is a vector from our coordinate system b
	- Where [5/3, 1/3] is that vector in Jennifer's coordinate system x
- We can see the inverse of a matrix also represents a linear transformation, since it is also a matrix whose columns represent some set of basis vectors

## Translating the Effect of a Linear Transformation between Coordinate Systems
- Suppose we want to perform a 90° counterclockwise rotation in our coordinate system
- Our transformation matrix would be [[0, 1], [-1, 0]]
- If we wanted to perform a 90° counterclockwise rotation in Jennifer's coordinate system, our transformation matrix would look different
- This is because transformations depend on the coordinate system we're currently in, and we have different coordinate systems
- In other words, the columns of the transformation matrix represent where our basis vectors go, but the matrix that Jennifer wants should represent where her basis vectors land (described in her coordinate system)
- We can solve this problem using the equation A⁻¹MA
	- Where M represents the transformation matrix in our coordinate system (i.e. [[0, 1], [-1, 0]])
	- Where A represents Jennifer's basis vectors in our coordinate system (i.e. [[2, 1], [-1, 1]])
	- Where A⁻¹ represents our basis vectors in Jennifer's coordinate system (i.e. [[1/3, -1/3], [1/3, 2/3]])

## References
- https://www.youtube.com/watch?v=P2LTAUO1TdA&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab&index=13
