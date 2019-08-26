## Example: Markov Chain in relation to Weather
- A Markov Chain with a State Space S={Sunny, Rainy} has a transition matrix:
        - P=[    S   R ]
            [S  .9  .1 ]
            [R  .5  .5 ]
- Say we wanted to calculate the probability of the weather in two days from today being sunny, and we know that the weather today is sunny:
        - We need to calculate P(1st day is sunny->sunny and 2nd day is sunny->sunny) = 0.9*0.9 = 0.81
        - We need to calculate P(1st day is sunny->rainy and 2nd day is rainy->sunny) = 0.1*0.5 = 0.05
        - Then P(Sunny 2 days from now) = 0.9*0.9 + 0.1*0.5 = 0.81*0.05 = 0.86
- Mathematically, we could write the above situation as:
        1. Let an event A={SS,SR,RS,RR} represent a set of possible weather transitions from one day to another
                - Where SS = a day of sunny weather where the previous day was also sunny
                - Where SR = a day of rainy weather where the previous day was sunny
                - Where RS = a day of sunny weather where the previous day was rainy
                - Where RR = a day of rainy weather where the previous day was also rainy
        2. Calculate the probability P(SS,SS)
        3. Calculate the probability P(SR,RS)
        4. Calculate the probability P(Second day is sunny) = P(SS,SS) + P(SR,RS)

## Example of a Markov Chain in relation to the Stock Market

## Example of a Markov Chain in relation to a Random Walk

## References
- https://stats.stackexchange.com/questions/165/how-would-you-explain-markov-chain-monte-carlo-mcmc-to-a-layperson
- https://en.wikipedia.org/wiki/Markov_chain
