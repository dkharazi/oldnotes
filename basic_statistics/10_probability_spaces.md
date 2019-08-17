## The Sample Space
- A set that contains all possible outcomes of some function
- The sample space can be written as Ω
- Examples:
	- The sample space of a coin toss: Ω={H,T}
	- The sample space of a two coins tossed: Ω={(H,T),(H,H),(T,H),(T,T)}

## Algebra
- An algebra can be written as 𝓕
- Essentially, an algebra is a collection of subsets from Ω where:
	1. The null set is contained within our algebra
		- Mathematically, written as ∅ ∈ 𝓕 
		- The null set is an empty set
	2. And A ∈ 𝓕, then A-compliment ∈ 𝓕
		- Where A is a subset of Ω
	3. And A ∈ 𝓕, B ∈ 𝓕, then A∪B ∈ 𝓕
- Mathematically, an algebra on a set X is a collection 𝓕 of subsets of 𝑋 that satisfy:
	1. The empty subset and the set X are both in 𝓕
	2. 𝓕 is closed under complement
		- This means if A∈𝓕, then A-compliment∈𝓕 for all A∈𝓕
	3. 𝓕 is closed under finite unions
		- This means for all A1,A2,...,Ak in 𝓕, then A1∪A2∪...∪Ak are within 𝓕
		- This also means that A1∪A2∪...∪Ak is a finite collection of elements, i.e. k<∞ (k equals some known number)
			- In other words, the number of sets within 𝓕 is finite, and the union of all of the finite sets in 𝓕 are also finite.

## σ-Algebra
- Essentially, a σ-algebra is a collection of subsets from Ω where:
	1. 𝓕 is an algebra 
	2. A1, A2, ... ∈ 𝓕 implies A1 ∪ A2 ∪ .... ∈ 𝓕
- Mathematically, a σ-algebra on a set 𝑋 is a collection 𝓕 of subsets of 𝑋 satisfying the following properties:
	1. The empty subset and X are both in 𝓕
	2. 𝓕 is closed under complement
	3. 𝓕 is closed under countable unions
		- This means for all A1,A2,...,Ak in 𝓕, then A1∪A2∪...∪Ak are within 𝓕
		- This also means that A1∪A2∪...∪Ak is a countable collection of elements, i.e. k={some countable theoretical number}
			- In other words, the sets within 𝓕 are countable, and the union of all of the countable sets in 𝓕 are also countable.

## Examples
- Algebra
	- Let 𝑋 be an infinite set, and A be the collection of all subsets of 𝑋 which are finite or have finite complement. Then A is an algebra of sets which is not a 𝜎-algebra.
- σ-Algebra
	- 𝓕 = {∅, Ω}
	- 𝓕 = {∅, A, A-compliment, Ω}
	- 𝓕 = 2^Ω (which is a collection of all of the subsets of omega)
- Neither
	- 𝓕 = {∅, A, Ω} (Needs to contain the compliment)

## The Probability Measure Function
- A probability measure function is a function that maps events to its corresponding probabilities
- Denoted as P

## Probability Space (Ω, 𝓕, P)
- A probability space is constructed with a specific kind of situation or experiment in mind
- One proposes that each time a situation of that kind arises, the set of possible outcomes is the same and the probabilities are also the same
- Consists of the following:
	1. A sample space Ω that is a set of all possible outcomes
	2. A set of events 𝓕 that is a set of events, where each event is a set of any possible outcome
	3. A function P that maps the events to probabilities
- Once the probability space is established, it is assumed that “nature” makes its move and selects a single outcome, ω, from the sample space Ω
- All the events in 𝓕 that contain the selected outcome ω (recall that each event is a subset of Ω) are said to "have occurred" 
- The selection performed by nature is done in such a way that if the experiment were to be repeated an infinite number of times, the relative frequencies of occurrence of each of the events would coincide with the probabilities prescribed by the function P

## References
- http://www.its.caltech.edu/~mshum/stats/lect1.pdf
- https://math.stackexchange.com/questions/150530/sigma-algebra-and-algebra-difference
- https://www.quora.com/Can-you-give-some-examples-where-algebra-and-sigma-algebra-are-different
- https://www.youtube.com/watch?v=-nnJQ0kJgIY&list=PLbMVogVj5nJQqGHrpAloTec_lOKsG-foc&index=4
- http://theanalysisofdata.com/probability/A_1.html
- https://en.wikipedia.org/wiki/Probability_space
- https://math.stackexchange.com/questions/1990959/probability-space-of-a-random-variable
- https://sites.math.washington.edu/~hoffman/521/week1notes.pdf
