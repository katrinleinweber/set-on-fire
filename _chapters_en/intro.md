---
permalink: "/en/intro/"
title: "Introduction"
questions:
-   "What are the key differences between research software and other projects?"
-   "What does 'done' look like for a research software project?"
-   "What are the goals of this training?"
objectives:
-   "Compare and contrast research software projects and other software projects."
-   "Name and explain key features of a mature research software project."
keypoints:
-   "Requirements for research software projects are typically emergent."
-   "Research software is 'done' when it can be used with confidence by people other than its authors and extended with reasonable effort."
---

-   Research is becoming more compute intensive
    -   Modeling, simulation, data analysis, data management, ...
-   Research *doesn't* mean "academic"
    -   Most data scientists are doing research
    -   Applying results instead of acting on them
-   Most researchers don't have any training in software development or community leadership
-   There is much more to a research software project than just code
    -   *Data* must be stored, cleaned, and tracked
    -   Code and data must be *structured* so that they are findable
    -   There must be a *development process* governing who does what, in what order, and how
    -   Developers, users, funders, and consumers of research results must be *communicate*...
    -   ...and be *mentored*
-   This training will discuss:
    -   What a research software project needs to achieve its goals
    -   How to transform *ad hoc* solo projects into sustainable, reliable small-team projects

## Philosophy of This Material (#s:intro-philosophy)

-   A [commons](#g:commons) is something managed jointly by a community
    according to rules they themselves have evolved and adopted
-   A research software project should aim to become a commons
    -   Its community consists of authors, users of the software, consumers of the research, and funders
    -   This material is a starting point for rules, but only a starting point:
        every community should customize them according to local needs

## Key Differences Between Research Software and Other Projects {#s:intro-characteristics}

-   Goals of research software projects
    -   Help authors answer research questions correctly
    -   Help other people answer research questions
        -   Essential for [reproducible research](#g:reproducible-research):
            if other people can't use the software, how can they review or evaluate the work?
    -   Earn credit for authors directly
        -   I.e., for having built the software rather than for the answers the software produces
-   Requirements may be either:
    -   Discovered as we go along (exploring)
    -   Relatively stable (engineering)
-   Research software tends to be *subtle* as well as *complicated*
    -   Control flow may be very simple compared to (for example) a computer game or e-commerce application...
    -   ...but figuring out exactly what coefficients and indexes to use is often hard...
    -   ...and determining whether the software is working correctly can be even harder
        -   "If we knew what answer to expect, we'd have published already"
-   Staff are usually [end-user programmers](#g:end-user-programmer) primarily interested in *using* software rather than *building* it
    -   Graduate students, post-docs, or (occasionally) faculty
    -   Experts in the problem domain (or becoming such)
    -   Mostly self-taught or peer-taught programmers
-   Some staff may be [research software engineers](#g:rse) (RSEs)
    -   Discussed in detail in [s:rse](#CHAPTER)

## What Does 'Done' Look Like? {#s:intro-done}

1.  Authors are reasonably confident that results are correct
    -   Not the same as "absolutely sure"
    -   As trustworthy as physical experiments or manual data analysis
2.  Has a citable publication described in an easy-to-find way so that users can credit the project in an academically-digestible form
3.  Software can be used by people other than original authors without heroic effort
    -   "Without heroic effort": it must be possible for people other than the authors to figure it out and use it in less time than it would take to write their own
    -   As noted above, reproducible research is impossible without this
    -   Those other people must also be reasonably confident that results are correct
4.  Fast enough to be worth using
    -   "Fast enough" includes time to find, time to install, time to figure out, and *then* time to run
5.  Small changes and extensions are easy
    -   E.g., researchers can extend the software to read data in a slightly different format, introduce a new sorting method or scaling factor, etc., without doing a wholesale rewrite
    -   Nobody has solved the "large changes are easy" problem yet...
6.  Follows community norms so that people can (and hopefully will) adopt it and maintain it
    -   I.e., it is [sustainable software](g:#sustainable-software)

## Scope of This Material {#s:intro-scope}

-   From single author-user to 3x6 (three people for six months)
-   Contributors are usually time-slicing other 
-   Contributors are primarily rewarded for their results, not the software itself
-   "Everybody makes coffee", i.e., little or no specialization of roles
-   See [s:guide-design](#SECTION) for full descriptions of learner personas

## Setup {#s:intro-setup}

-   Programming experience
    -   Be able to write functions in [Python][python], [R][r], or [MATLAB][matlab]
-   Prior exposure to the [Unix shell][bash]
    -   E.g., the [Software Carpentry introduction to the Unix Shell][swc-shell]
-   Some previous experience using [Git][git] and a [GitHub][github] account
    -   E.g., the [Software Carpentry introduction to Git][swc-git] or [[Blis2016](#CITE)]

## Exercises {#s:intro-exercises}

### Create a Value Proposition for Your Project

Fill in the template below for your current project.

1.  For **description of target users**
2.  who want to **statement of their need(s)**,
3.  **project name**
4.  provides **statement of key benefits**.
5.  Unlike **name of alternative solutions(s)**,
6.  our project enables users to **key differentiator**.

## Describe How Your Project is Managed

Write a short point-form description of your current project:

1.  Who uses the software?
2.  How?
3.  How do they find the software?
4.  How do they set it up?
5.  Who decides what to change and when?
6.  How are decisions and changes circulated?

{% include links.md %}
