# Objective

The projects have students implement constant propagation. To do that, constant folding is needed (first lab) along with a control flow graph representation of a method and a reaching definition data-flow analysis of a control flow graph. These three things make constant propagation possible which is the subject of the next lab.  This lab puts the other two pieces in place: control flow graphs and data-flow analysis.

The first objective of this lab is to implement a `ControlFlowGraph` class that builds the control flow graph for a method given a `MethodDeclaration` node in a `CompilationUnit`. The graph should be constructed with an `ASTVisitor` using the algorithm defined in the [lecture notes](https://bitbucket.org/byucs329/byu-cs-329-lecture-notes/src/master/cfg-rd-lecture.md). 

The second objective of this lab is to implement the reaching definitions data-flow analysis as defined in the [lecture notes](https://bitbucket.org/byucs329/byu-cs-329-lecture-notes/src/master/cfg-rd-lecture.md) on the `ControlFlowGraph`.

The third objective is to create a test framework to test the correctness of the control flow graph and the reaching definition analysis. Both implementations should be functionally tested with Black-box test techniques in isolation. What that means is that mocking is used to test reaching definitions separate from building the control flow graph so the tests for the reaching definitions do not rely on the code to build the control flow graph. 

Please keep in mind that the next lab will integrate constant folding, control flow graphs, and reaching definitions to implement constant propagation.  

# Reading

See [cfg-rd-lecture.md](https://bitbucket.org/byucs329/byu-cs-329-lecture-notes/src/master/cfg-rd-lecture.md).

# Java Subset

Use the same subset of Java as defined in **Lab0 Constant Folding**. See [README.md](https://github.com/byu-cs329/lab0-constant-folding) in the master template repository or the most updated set of language restrictions.

# Lab Requirements

  1. An implementation and black-box functional test framework for the `ControlFlowGraph` 
  2. An implementation and minimal black-box functional test framework using mocks to implement the `ControlFlowGraph` interface for the reaching definitions data-flow analysis---separate the test for reaching definitions from the control flow graph construction
  3. The use of the ```Mockito.verify``` API to verify interactions with the ```ControlFlowGraph``` mock
  4. A black-box functional test framework for the integrated system that builds the control flow graph and then does the reaching definitions analysis

## What to turn in?

Create a pull request when the lab is done. Submit to Canvas the URL of the repository.

# Rubric

| Item | Point Value |
| ------- | ----------- |
| Test framework for ```ControlFlowGraph``` with reasonable oracles | 20 |
| Tests that divide the input space in a reasoned, systematic, and somewhat complete way for ```ControlFlowGraph``| 30 |
| Test framework for ```ReachingDefinitions``` with reasonable oracles | 20 |
| Minimal number of tests using mocks for the ```ControlFlowGraph``` that cover a few interesting parts of the input space for ```ReachingDefinitions``| 30 |
| Checks in tests using the ```Mockito.verify``` API either with mock objects or spy objects during unit testing or integration testing | 20 |
| Consistent, readable, and descriptive naming of all tests | 10 |
| Appropriate use of `@Nested`, `@Tag`, and `@DisplayName` to organize and communicate the test methodology | 10 | | 
| Implementation of ```ControlFlowGraph``` | 25 |
| Implementation of ```ReachingDefinitions``` | 25 |
| Adherence to best practices (e.g., no errors, no warnings, documented code, well grouped commits, appropriate commit messages, etc.) | 10 | |