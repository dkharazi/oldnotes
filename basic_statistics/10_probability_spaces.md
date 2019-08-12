## The Sample Space
- A set that contains all possible outcomes of some function
	- In most cases, we think of our function as a random experiment
- A sample space can be written as Ω

## Algebra
- An algebra can be written as 𝓕
- Mathematically, an algebra is a collection of subsets from Ω where:
	1. The null set is contained within our algebra
		- Mathematically, written as ∅ ∈ 𝓕 
		- The null set is an empty set
	2. And A ∈ 𝓕, then A-compliment ∈ 𝓕
		- Where A is a subset of Ω
	3. And A ∈ 𝓕, B ∈ 𝓕, then A∪B ∈ 𝓕
- Put another way, an algebra on a set X is a collection 𝓕 of subsets of 𝑋 that satisfy:
	1. The empty subset and the set X are both in 𝓕
	2. 𝓕 is closed under complement
		- This means if A∈𝓕, then A-compliment∈𝓕 for all A∈𝓕
	3. 𝓕 is closed under finite unions
		- This means for all A1,A2,...,Ak in 𝓕, then A1∪A2∪...∪Ak are within 𝓕
		- This also means that A1∪A2∪...∪Ak is a finite collection of elements, i.e. k<∞
			- In other words, the sets within 𝓕 are finite, and the union of all of the finite sets in 𝓕 are also finite.

## σ-Algebra
- Put another way, A σ-algebra on a set 𝑋 is a collection 𝓕 of subsets of 𝑋 satisfying the following properties:
	1. The empty subset and X are both in 𝓕
	2. 𝓕 is closed under complement
	3. 𝓕 is closed under countable unions
		- This means for all A1,A2,...,Ak in 𝓕, then A1∪A2∪...∪Ak are within 𝓕
		- This also means that A1∪A2∪...∪Ak is a countable collection of elements, i.e. k={some countable n}
			- In other words, the sets within 𝓕 are countable, and the union of all of the countable sets in 𝓕 are also countable.
- Example of σ-Algebra: 𝓕 = {∅, Ω}
- Example of σ-Algebra: 𝓕 = {∅, A, A-compliment, Ω}
- Example of σ-Algebra: 𝓕 = 2^Ω (which is a collection of all of the subsets of omega)
- Not an example of σ-Algebra: 𝓕 = {∅, A, Ω} (Needs to contain the compliment)

## Further Notations
- We can write {an element} ∈ {a set}, or {a set} ∈ {a collection of sets}
	- For example, we can write a∈A, where A is an event (which is a set) and a is an outcome/realization of A
	- For example, we can also write A∈𝓕, where A is an event (which is a set) and 𝓕 is an algebra (which is a collection of sets)
- We can write {a set} ⊂ {a set}, or {a collection of sets} ⊂ {a collection of sets}
	- For example, we can write A⊂B, where A and B are both events (which are sets)
	- For example, we can also write 𝓕 0 ⊂ 𝓕 1, where 𝓕 0 is an algebra (which is a collection of sets) that is contained within an algebra 𝓕 1 (which is larger a collection of sets)

## Measurable Space

## The P-space

## The Triple Space

## References
- https://math.stackexchange.com/questions/150530/sigma-algebra-and-algebra-difference
- https://www.quora.com/Can-you-give-some-examples-where-algebra-and-sigma-algebra-are-different
- https://www.youtube.com/watch?v=-nnJQ0kJgIY&list=PLbMVogVj5nJQqGHrpAloTec_lOKsG-foc&index=4
- http://theanalysisofdata.com/probability/A_1.html
- https://en.wikipedia.org/wiki/Probability_space
- https://math.stackexchange.com/questions/1990959/probability-space-of-a-random-variable
