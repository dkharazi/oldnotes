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

## References
- https://docs.codecov.io/docs/about-code-coverage
- https://stackoverflow.com/questions/36006817/what-is-a-partial-hit-in-code-coverage
- https://docs.codecov.io/docs/coverage-diff
- https://github.com/gap-system/gap/wiki/Codecov-explained
- https://github.com/pandas-dev/pandas/pull/16191
