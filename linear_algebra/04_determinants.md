## General Description
- The determinant of a linear transformation is a scaling factor by which a linear transformation changes any area
- Said another way, the determinant is a measure of how much a space is stretched or squished together
- This implies that the determinant only changes when the area changes in size after a transformation
- In 2D spaces, the determinant represents the scaling factor by which a linear transformation changes any area
- In 3D (or greater) spaces, the determinant represents the scaling factor by which a linear transformation changes any volume

## Rules of Determinants
- If an area is squeezed to a lower dimension after a transformation (i.e. linear dependence), then the determinant of the linear transformation is 0
- If an area is flipped over after a transformation, then the determinant of the linear transformation is negative
- In other words, the determinant's value represents the magnitude by which areas have been scaled
- And, the determinant's sign represents the orientation (or direction) by which areas have been scaled 

## Example of a Determinant
- Let's say our transformation matrix is [[3, 0], [0, 2]]
	- The area represented by the standard basis vectors in the original vector space equals 1 (i.e. 1x1=1)
	- The area represented by the standard basis vectors in the transformed vector space equals 6 (i.e. 3x2=6)
	- Since the area started out as 1 and ended up as 6, then we can say the linear transformation has scaled its area by a factor of 6
- Let's say our transformation matrix is [[1, 0], [1, 1]]
	- The area represented by the standard basis vectors in the original vector space equals 1 (i.e. 1x1=1)
	- The area represented by the standard basis vectors in the transformed vector space equals 1 (i.e. 1x1=1)
	- Since the area started out as 1 and ended up as 1, then we can say the linear transformation hasn't scaled up or down
	- This is because the size of the unit square hasn't changed, but only been rotated

## Calculating the Determinant
- Let's say we have a 2D transformation matrix represented as [[a, c], [b, d]]
- Then, det([[a, c], [b, d]]) = ad - bc
- Where, a and d represent how much the basis vectors are stretched, roughly speaking
- Where, b and c represent how much the area (made up by the stretched basis vectors) is stretched in the diagonal direction, roughly speaking

## References
- https://www.youtube.com/watch?v=Ip3X9LOh2dk&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab&index=6
