## Set Notation
- A set is a unique sequence of observable outcomes (e.g. {1,2,3,4,5,6} for a roll of a single die)
- An event is a set of outcomes that is written as a capital letter (e.g. A)
- A random variable is a function that is written as a capital, italicized letter 
- A realization is an observed outcome that is written as a lower-case, italicized letter

## Random Variable
- Represents a function that maps a single value from the sample space to a realization that is any single real number
	- Mathematically, defined as X: Ω → ℝ such that ω ↦ X(ω)
		- Where ω∈Ω and X(ω)∈ℝ
		- Ω is a set that represents the domain of the random variable function
		- ℝ is a set that represents the range of the random variable function
		- ω represents an element, or a single value, from the set Ω
		- X(ω) represents an element, or a single value, from the set ℝ
			- Also referred to as a realization (of the random variable function)

## Probability
- Represent a function that maps a single value from the sample space to a realization that is in the interval of 0 and 1
	- Typically, the output of the random variable function becomes the input of the probability function
		- Therefore, the sample space will represent the range of the random variable
	- Mathematically, defined as P: Ω → [0,1] such that ω ↦ P(ω)

## Events
- Sometimes, we don't want our function to map a single value from Ω or to ℝ. In this situation, we would create an event.
- For example, we could let Ω denote the sample space, let A be an event that is a subset of ℝ, and let X be our random variable
	- Mathematically, defined as X: Ω → A such that ω ↦ X(ω)
		- Where A⊂ℝ, ω∈Ω, and X(ω)∈A 
		- Ω is a set that represents the domain of the random variable function
		- A is a set that represents the range of the random variable function
		- A is an event that is a subset of all real numbers
		- ω represents an element, or a single value, from the set Ω
		- X(ω) represents an element, or a single value, from the event A
- Another example: we could let A be an event that is a subset of Ω, let ℝ be a set of all real numbers, and let X be our random variable
	- Mathematically, defined as X: A → ℝ such that ω ↦ X(ω)
		- Where A⊂Ω, ω∈A, and X(ω)∈ℝ
		- A is a set that represents the domain of the random variable function
		- ℝ is a set that represents the range of the random variable function
		- A is an event that is a subset of the sample space
		- ω represents an element, or a single value, from the set A
		- X(ω) represents an element, or a single value, from the set ℝ
- One last example: we could let A be an event that represents the set {red, white, blue}, let B be an event that represents the set {cat, dog}, and let X be our random variable
	- Mathematically, defined as X: A → B such that ω ↦ X(ω)
		- Where A={red, white, blue}, B={cat,dog}, ω∈A, and X(ω)∈B
		- A is a set that represents the domain of the random variable function
		- B is a set that represents the range of the random variable function
		- A is an event that is a subset of the sample space (i.e. colors)
		- B is an event that is a subset of animals
		- ω represents an element, or a single value, from the event A
		- X(ω) represents an element, or a single value, from the event B

## Remarks on Mathematical Notation
- A random variable X is a function X: Ω → ℝ, but we often use the shorthand X to refer to X(ω) for ω∈Ω
- Probability functions can be written in many ways
	- pX(r) ≡ P(X = r) ≡ P({s ∈ S : X(s) = r})
- Sets can be written as the following:
	- S ≡ {i ∈ ℝ : 1 ≤ i ≤ 6, x is odd}
	- S ≡ {(i, j) : 1 ≤ i ≤ 6, 1 ≤ j ≤ 6}
	- S ≡ {type of each element in list : range of each element}
- Example of alternative definition of realization
	- X(s) ≡ X((i, j)) = i + j

## Reference
- https://en.wikipedia.org/wiki/List_of_mathematical_symbols
- https://math.stackexchange.com/questions/240673/what-exactly-is-a-random-variable
- http://www.columbia.edu/~ww2040/4106S11/lec0125.pdf
- http://bactra.org/prob-notes/srl.pdf
- https://stats.stackexchange.com/questions/246047/independent-variable-random-variable
