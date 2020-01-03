## General Description
- Code coverage is a measurement used to express which lines of code were executed by a bunch of unit tests
- There are three primary terms to describe each line that was executed:
	- `Hit:` Source code was executed by a unit test
	- `Miss:` Source code was not executed by a unit test
	- `Partial:` A branching statement was executed, but one of its branches was not executed
- Coverage = hits / (hits + partials + misses)
- Code coverage provides a visual measurement of what source code is being executed by a set of unit tests
- Code coverage is used for the following:
	- To tell software developers whether new unit tests need to be created or not
	- To tell software developers whether a merge should be made or not

## Example of Coverage
```
class Struct(object):                  # hit
    def __init__(self, content=None):  # hit            
        if content is not None:        # partial hit
            self.content = content     # hit

    def print_content(self):           # hit
	print(self.content)            # hit

s = Struct('42')                       # hit
s.print_content()                      # hit
```

## Line Coverage and Branch Coverage
- Line coverage refers to the percent of lines executed by a test run
- Branch coverage refers to the percent of branches executed by a test run
- If your test only exercises a boolean cond value being true and never runs the else branch, then:
	- 4 out of 5 lines are covered
	- 1 out of 2 branches are covered
```
if(cond) {
    line1();
    line2();
    line3();
    line4();
} else {
    line5();
}
```

## References
- https://docs.codecov.io/docs/about-code-coverage
- https://stackoverflow.com/questions/36006817/what-is-a-partial-hit-in-code-coverage
- https://docs.codecov.io/docs/coverage-diff
- https://github.com/gap-system/gap/wiki/Codecov-explained
- https://stackoverflow.com/questions/8229236/differences-between-line-and-branch-coverage
- https://github.com/pandas-dev/pandas/pull/16191
