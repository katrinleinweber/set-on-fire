---
permalink: "/en/tdd/"
title: "Test Driven Development"
objectives:
-   "Define test-driven development and explain the rationale for it."
-   "Write unit tests to define what what a simple function is supposed to do."
keypoints:
-   "Test-driven development (TDD) is the practice of writing tests before writing code."
-   "Writing tests first helps clarify the intent and interface of the code to be written."
-   "Empirical evidence for TDD's benefits is unclear, but many programmers find it very useful."
---

-   [Test-driven development](#g:tdd) (TDD)
    -   Write a handful of tests that don't even run because the code they
        are supposed to test doesn't exist yet.
    -   Write just enough code to make those tests pass.
    -   Clean up what's just been written.
    -   Commit it to version control.
-   Advocates claim that writing tests first:
    -   Focuses people's minds on what code is supposed to
        so that they're not subject to confirmation bias when viewing test results
    -   Ensures that code actually *is* testable
    -   Ensures tests are actually written
-   Evidence backing these claims is contradictory
    -   Empirical studies have not found a strong positive effect
    -   But many productive programmers believe in it
    -   So maybe we're measuring the wrong things...

## Exercises {#s:tdd-exercises}

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
