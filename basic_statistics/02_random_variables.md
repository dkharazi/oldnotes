## Definition
- Represents a function that maps a single value from the sample space to a realization that is any single real number
        - Mathematically, defined as X: Ω → ℝ such that ω ↦ X(ω)
                - Where ω∈Ω and X(ω)∈ℝ
                - Ω is a set that represents the domain of the random variable function
                - ℝ is a set that represents the range of the random variable function
                - ω represents an element, or a single value, from the set Ω
                - X(ω) represents an element, or a single value, from the set ℝ
                        - Also referred to as a realization (of the random variable function)

## Notations
- It’s conventional to write random variables with upper-case italic letters
	- i.e. A, B, C, X, Y, Z, etc.
		- Random variables should not be confused with events, which are also written using upper-case letters
	- Their realizations are denoted as lower-case italics
		- i.e. a, b, c, x, y, z, etc
- It’s also common to write the successive random variables that all belong to the same functions as S0, S1, ...St, ...Sn
        - Therefore, the space of each of these random variables is the same
                - That sample space is referred to as S
                - Its realizations would be referred to as s0, s1, ...st, ...sn

## Example Notations
- Y is our normally-distributed random variable
- y1, y2, ...yn is our sample, which is just a sequence of realizations (or Y(ω))
- 𝜃 is a sequence of parameters associated with our random variable Y
	- In this case 𝜃 = (μ,σ)
- The expected value of Y is written as E[Y], which is equal to μ
- μ-hat is the best estimator for our population parameter μ
- μ-hat equals y-bar when our random variable Y is normally distributed
	- Since Y is normally distributed in our case, μ-hat equals y-bar
	- y-bar equals (1/n)*Σyi
- μ-hat → E[Y] (otherwise known as µ) due to the law of large numbers (as n→∞)

## Example Use-Case
- Let X be a random variable that represents the process of flipping a coin
- We could mathematically define this as X: Ω → A
	- Where X is our random variable
	- Where our domain, or sample space Ω, is defined as Ω ≡ {Heads, Tails}
	- Where ω is a realization of our sample space Ω
	- Where our range, X(ω) or more specifically A in this case, is defined as A ≡ {0, 1} (or A ≡ {x∈𝕎: 0≤x≤1})
		- Where x is a realization of A (or more generally speaking X(ω))
- In our example, our coin toss came up as five, so x = 5

## References
- https://www.stat.cmu.edu/~cshalizi/ADAfaEPoV/ADAfaEPoV.pdf
- https://math.stackexchange.com/questions/240673/what-exactly-is-a-random-variable
- http://www.columbia.edu/~ww2040/4106S11/lec0125.pdf
- http://bactra.org/prob-notes/srl.pdf
- https://stats.stackexchange.com/questions/246047/independent-variable-random-variable
- http://www.phdeconomics.sssup.it/documents/Lesson3.pdf
