---
permalink: "/en/testing/"
title: "Test All The Things"
objectives:
-   "Explain why scientists should think about testing in terms of tolerances."
-   "Write unit tests to define what what a simple function is supposed to do."
keypoints:
-   "Write tests to define explicit tolerances."
-   "Use a unit testing framework to write and run tests."
-   "Isolate tests."
---

-   You're already evaluating whether your software does what you think it should do.
    The question is whether the evaluation process is:
    -   Automated
    -   Comprehensive
    -   Well documented
-   "Physicists worry about decimal places. Astronomers worry about exponents. Economists are happy if they've got the sign right."
    -   I.e., every field of science and engineering has community norms for tolerances
    -   But those community norms don't exist (yet) for software
-   When writing tests, think in terms of tolerances
    -   "What range of outputs will I accept as correct for input X in situation Y?"
-   Integer and text operations: usually require exact answer
-   Anything involving floating point: allow error bars (just as in physical experiments)
    -   But still produce identical answers for identical inputs
-   Examples
    -   When refactoring image processing routine to improve performance:
    if more than 1% of pixels change value by more than the low bit, assume a bug
    -   N-body simulation:
    if system's energy or momentum changes by more than one part in 1.0e6 over lifetime of simulation
    -   Why one in a million?  Because we have to choose something...
-   Types of tests
    -   [Smoke tests](#g:smoke-test) (does this blow up when I try to use it?)
    -   [Unit tests](#g:unit-test) (developers can safely rely on this function to do what it advertises)
    -   [Functional tests](#g:functional-test) (users can safely rely on this program to do what it advertises)
    -   [Regression tests](#g:regression-test) (make sure this bug never crops up again)
-   Use a [test runner](#g:test-runner) to manage tests
    -   Each test is a function (or method)
    -   Test results are pass, fail, or error
    -   Optionally run setup before each test and teardown afterward
    -   Test runner finds and runs tests and reports aggregate results
-   Tests should be isolated
    -   Actions of one test should not affect actions of other tests
    -   I.e., should be able to run in arbitrary order with identical results

## Exercises {#s:testing-exercises}

### What Are Your Tolerances?

1.  What will you measure to determine whether your software is correct enough?
2.  What tolerances will you accept on answers?
3.  Why?

### Pick a Unit Testing Framework

1.  If your project already uses a unit testing framework,
    explain which one and why you chose it.
2.  If your project does not already use a unit testing framework,
    find one and create one test using it.

### First, the Tests

1.  Using `assert` statements,
    write half a dozen tests for each of the following functions.
2.  Compare your tests to those written by your neighbors.
    What errors did they test for that you didn't?
    What would your tests catch that they missed?
3.  Where did you interpret requirements differently?
    I.e., where would a function pass one of your neighbors' tests but fail one of yours
    or vice versa?

{% include problems.md %}

{% include links.md %}
