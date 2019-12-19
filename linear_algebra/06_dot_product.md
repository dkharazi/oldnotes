## General Description
- The dot product is a single number that represents the amount of growth observed between two vectors interacting with each other
- To determine the most accurate amount of growth made up by the two vectors, we need to ensure the vectors are on the same scale
- We can achieve this by projecting one vector onto the line made up by the other vector
- Here, we can think of "projection" to mean "along the path"
- Roughly, we can think of the dot product as directional multiplication, where vectors just represent directional growth
- When dealing with vectors, there's only a few common operations we can perform:
	- Add vectors: accumulate the growth contained in several vectors
	- Multiply by a constant: make an existing vector stronger
	- Dot product: apply the directional growth of one vector to another, which results in strengthening the original vector

## Motivating Directional Multiplication
- If everything were lined up in the universe, then we'd love to just use multiplication
- However, that's usually never the case
- Therefore, we take the dot product to account for potential differences in direction
- If we think of integrals as multiplication taking changes into account, then we can think of the dot product as multiplication taking direction into account
- Specifically, multiplication goes beyond repeated counting
- It's better to think about multiplication as applying one item to another
- For example, complex multiplication is rotation (and not repeated counting)

## Basic Properties of the Dot Product
- If you have two vectors of the same dimension (i.e. two lists of numbers with the same length), then taking their dot product has the following numerical definition:
        1. First, pairing up all of their coordinates
        2. Then, multiplying those pairs together
        3. Then, adding those multiplied pairs together
- If the dot product between two vectors is:
	- Positive, then the two vectors are generally pointing in the same direction
	- Negative, then the two vectors are generally pointing in opposite directions
	- Zero, then the two vectors are perpendicular

## Examples of the Dot Product
- dotprod([1, 2], [3, 4]) = (1x3) + (2x4) = 11
- dotprod([6, 2, 8, 3], [1, 8, 5, 3]) = (6x1) + (2x8) + (8x5) + (3x3) = 71
- dotprod([3, 0], [0, 5]) = (3x0) + (0x5) = 0

## Defining Dot Products using Growth
- We can define directional growth as the amount of growth in each dimension, which will create a new vector oriented in a new direction
- Finding the dot product between any two vectors will give us their directional growth
- Let's say we wanted to take the dot products of the set of vectors (3, 0) and (4, 0) to measure their total growth across each dimension
	- Where the number 3 represents directional growth in a single dimension or direction (i.e. the x-axis)
	- Where the number 4 represents directional growth in that same dimension or direction (i.e. the x-axis)
	- Where the numbers 0 represent directional growth in a different dimension or direction (i.e. the y-axis)
	- Therefore, the total amount of growth observed (i.e. directional growth) is 12
- Let's say we wanted to take the dot products of the set of vectors (3, 0), and (0, 4) to measure their total growth across each dimension
	- Where the x-axis dimension refers to an amount of bananas and the y-axis dimension refers to an amount of oranges
	- The first vector represents tripling our bananas and destroying our oranges
	- The second vector represents destroying our bananas and quadrupling our oranges
	- Here, addition refers to quantity, whereas multiplication refers to growth of a quantity

## Dot Product as a Similarity Measure
- Previously, we referred to the dot product between two vectors as a directional growth
- We can also think of the dot product as a similarity measure
- When the vectors are:
	- Exactly in the same direction, then the dot product (or similarity) of the vectors is positive and large
	- Sort of in the same direction, then the dot product (or similarity) of the vectors is positive and small
	- Perpendicular, then the dot product (or similarity) of the vectors is zero
	- Sort of in the opposite direction, then the dot product (or similarity) of the vectors is negative and small
	- Exactly in the opposite direction, then the dot product (or similarity) of the vectors is negative and large

## Analogy involving Mario-Kart
- In Mario Kart, there are boost pads on the ground that increase a player's speed
- In the game, there is a player vector representing our player's speed and a boost pad vector representing the orientation of a boost pad
- Each of these vectors can be represented as a two dimensional vector (i.e. x and y direction)
- If a player vector is large, then the player is moving at a very fast speed
- If a boost pad vector is large, then the boost pad itself is long
- If we want to determine how much boost a player receives when they drive over a boost pad, then we need to assume the following:
	- If a player is dropped over a boost pad with zero speed, then the boost pad will not provide the player with any boost
	- If a players crosses the pad perpendicularly, then the boost pad will not provide the player with any boost
- For all other cases, our x-speed will get an x-boost and our y-speed gets a y-boost if we have some overlap
- Specifically, Total Speed = speedx·boostx + speedy·boosty

## References
- https://www.youtube.com/watch?v=LyGKycYT2v0&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab&index=9
- https://betterexplained.com/articles/vector-calculus-understanding-the-dot-product/
- https://math.stackexchange.com/questions/805954/what-does-the-dot-product-of-two-vectors-represent
- http://spiff.rit.edu/classes/phys311.old/lectures/dot/dot.html
