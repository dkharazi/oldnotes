## Definition of Probability
- A set of outcomes is known as an event
- The number of occurrences of an event is a frequency
- In English, a probability is a number that tell us how often an event happens
- Mathematically, a probability is a real number between 0 and 1
- The space of occurrences representing the real numbers between 0 and 1 is known as the probability space
- A function that maps an event to a probability is called a probability distrib
ution

## Probability Calculus
- The following conditions need to be satisfied in order for a number to be considered a probability:
1. 0≤P(A)≤1
	- Events range from never happening to always happening
2. P(Ω)=1
	- Something must happen
3. P(Ø)=0
	- Nothing never happens
4. P(A)+P(Ā)=1
	- A must either happen or not happen
	- Here, Ā represents the compliment of A
5. P(A+B)=P(A)+P(B)-P(AB)
	- Here, A+B represents the set A alone, or B alone, or both together

## Types of Probabilities
- Essentially, there are three types of probabilities:
	1. Marginal probability
	2. Conditional probability
	3. Joint probability
- Marginal probability is the probability of observing an event irrespective of the outcome of another event
- Conditional probability is the probability of observing an event with respect to the outcome of another event
- Joint probability is the probability of observing two events

## More about Conditional Probabilities
- We're interested in knowing the conditional probability if we're interested in knowing the probability of observing event A out of all of the times event B has occurred (i.e. P(A|B))
- We can also express the conditional probability of observing event A given event B by taking the probability of observing the joint probability of observing the two events together (out of observing all possible events) and dividing that by the probability of only observing event A
- In other words, we can express the conditional probability as the joint probability divided by the marginal probability (i.e. P(A|B)=P(A*B)/P(B))

## Conditional Probabilities and Independence
- If P(B|A)=P(B), then whether or not A happens makes no difference to whether B happens
- In other words, events A and B are said to be independent if P(B|A)=P(B)

## Bayes Rule
- As previously stated, the conditional probability equals the joint probability divided by the marginal probability
- We can further simplify the formula for the conditional probability by deriving the formula for the joint probability
- Since the joint probability equals the conditional probability multiplied by the marginal probability (i.e. P(A*B)=P(A|B)*P(B)), then we can also express the conditional probability as P(A|B) = (P(B|A)*P(A))/P(B)
- This derived formula is known as Bayes Rule (or Bayes Theorem)

## References
- http://bactra.org/prob-notes/srl.pdf
