## Cardinality
- Defined as the number of elements within a set
        - Referred to as the length of a set
- We can determine the length of elements within a set through the use of cartestian products
        - This is typically denoted by {some set}^#
        - For example, ℝ^2 contains all elements that are made up of two real numbers from ℝ
                - R^2 is {(1.222,4), (3,5), (7.9,9/10), ...}
                - R^2 doesn't contain elements (1) or (2,5,6)
        - For example, {0,1}^∞ contains all elements that are made up of infinitely long sequences of 0s and 1s
                - {0,1}^∞ is {(0,1,0,0,1,0,0,..),(1,1,1,1,...), ...}
                - Thus, this would be considered an infinite set
- We can determine the cardinality of a set by removing the top-level commas and counting the number of elements within that set
        - For example, |{}| = 0
        - For example, |{{1}, {1,2,3,4}}| = 2
        - For example, |{{}, {2, {1, {}}}}| = 2

## Countable sets
- A set is countable if its cardinality is no greater than the cardinality of the natural numbers
- More specifically, a set is countable if there is a bijection between the given set and the set of all natural numbers
- Examples of countable sets:
        - ℕ [The set of all natural numbers] (i.e. ...,1,2,3,4,5,6,...)
        - 𝕎 [The set of all whole numbers] (i.e. ...,0,1,2,3,4,5,...)
        - ℤ [The set of all integers] (i.e. ...,-2,-1,0,1,2,...)
        - ℚ [The set of all rational numbers] (i.e. ...,1/3,.12,7/8,...)
- Examples of uncountable sets:
        - The set of all real numbers between 0 and 1
        - The set of all irrational numbers (i.e. any number that cannot be expressed using a fraction)
        - The set of all real numbers (since this contains the set of all irrational numbers)
        - The set of all complex numbers (i.e. ...,3i+5,3i-8,...)

## Finite Sets
- Roughly speaking, a finite set is a set in which one could in principle count and finish counting
- In other words, a finite set has a specific number of elements within its set
- Examples of finite sets:
        - {1,2,3,4,...,1000}
        - {-100,-99,-98,...,1000000000000}
        - A set with a cardinality of 2,478
        - A set with a cardinality of 1,000,000,000,000,000,000,000,000,000,000,000,000,000,000,000
- Examples of infinite sets:
        - The set of all even numbers
        - The set of all odd numbers

## More on Countability
- A finite set is a subset of a countable set
- In other words, all finite sets are countable, but not all countable sets are finite
- There are countably finite and countable infinite sets, but there are no such thing as uncountable finite sets
- A countable infinite set is the smallest infinite sets

## Power Sets and Cartesian Products
- The Cartesian product consists of ordered pairs of elements where the length of each pair is determined by the power raised (or the dimension)
        - The ordered pairs in this case are technically considered sets
- The power set consists of subsets of some set S
- We can denote cartesian products as S×S or S^2 if S is some set
- For example, say S = {1,2,3}
        - S×S = {(1,1),(1,2),(1,3),(2,1),(2,2),(2,3),(3,1),(3,2),(3,3)}
        - PowerSet(S) = {{∅},{1},{2},{3},{1,2},{1,3},{2,3},{1,2,3}}

## References
- http://theanalysisofdata.com/probability/A_1.html
- https://math.stackexchange.com/questions/185234/what-do-finite-infinite-countable-not-countable-countably-infinite-mean
- https://www.slideshare.net/ravingeek/sets-and-functions-by-saleh-elshehabey
- https://terrytao.files.wordpress.com/2011/01/measure-book1.pdf
- http://web.mnstate.edu/peil/MDEV102/U2/S13/S133.html
- quora.com/What-is-the-difference-between-finite-and-countable-in-mathematics
