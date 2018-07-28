---
permalink: "/en/guide/"
title: "Instructors' Guide"
---

## Design {#s:guide-design}

This lesson was developed using the methods in *[Teaching Tech Together][t3]* [[Wils2018](#CITE)].

### Brainstorming

-   Audience
    -   [Research software engineers][rse]
        who are now responsible for a small to medium-sized software project (defined below)
    -   Program frequently, use version control
    -   Know what unit testing is, but may not actually have written many tests
    -   No previous exposure to project management or software project management tools
-   Projects
    -   3×6: three people working for about six months
    -   Both numbers may vary up and down, but:
        -   Group is small enough to have lunch together (i.e., a single cohesive unit)
        -   Timescale is short enough that personnel turnover isn't an issue
    -   Some or all of the team members may be multi-tasking on other projects
    -   Building digital scientific instruments rather than doing exploratory data analysis
        -   E.g., creating a library, an application, or a pipeline
        -   May be starting from scratch
        -   But more likely cleaning up, rewriting, and integrating bits and pieces
    -   The principal scientific investigator (PI) *isn't* a member of the development team
-   Constraints
    -   One full day 09:00-16:00
        -   06:30 teaching time
        -   1:00 for lunch
        -   0:30 total for two coffee breaks
    -   This means we cannot introduce complex new tools
        -   But can add extensions to tools participants are already familiar with
    -   Attendees must be familiar with:
        -   [the Unix shell][shell-lesson]
        -   [Make][make-lesson]
        -   [Git][git-lesson] (enough to follow pull/edit/commit/push/PR instructions and use GitHub)
        -   [Python][python-lesson] (because we have to use some programming language for examples)
-   Running Example
    -   Start with a badly-organized software project
    -   Improve it in pieces throughout the course
-   Resources
    -   [Noble's Rules][noble-rules]
    -   [Jenkins' Project Primer][jenkins-primer]
    -   [Taschuk's Rules][taschuk-rules]

### Learner Personas

**Standage**

Standage, 33, is doing a post-doc in genomics at a research-intensive university in western Canada.
Over the past six years, she has created a set of R packages for mapping paleogenomic data
that are now being used by a dozen of her collaborators.
Her coding style has evolved considerably over that time,
and she now has permission from her supervisor to spend the summer bringing them up to date and documenting them
so that they can write a paper about them (and possibly commercialize them).

While Standage understands what a well-formed R package looks like,
she knows less about robust development processes,
release management,
and how to convince other people to file bugs and make contributions for software they didn't write.
This training will tell her which of these things she ought to worry about right now,
how to do them,
and how to tell when she (or others) are doing them right.

### Desired Results

**Questions:** how do I...

-   ...know what state my project is in?
-   ...figure out what the team ought to work on next?
-   ...figure out when they'll be done (and what "done" means)?
-   ...adjust plans when things go wrong?
-   ...make it easy for other people to contribute?
-   ...manage contributions from other developers?
-   ...create an installable, usable version of my project?
-   ...pass these skills on to my team?

**Skills:** I can...

1.  ...report my status clearly and succinctly in a stand-up meeting.
2.  ...give others feedback on the content and presentation of their stand-up reports.
3.  ...critique and improve bug reports and status reports.
4.  ...create a development schedule for a project
    given a set of tasks with priorities and time estimates.
5.  ...(re-)organize the files in a small to medium-sized software project
    according to [Noble's Rules][noble-rules]
6.  ...implement continuous integration by connecting
    a regression test script to a GitHub repository using Travis-CI.
7.  ...apply [Taschuk's Rules][taschuk-rules] to make software more robust.
8.  ...create an installable Python package.

**Concepts:** I know...

-   ...that participating in a software project is a separate skill from programming.
-   ...what the core practices of agile and sturdy development are
    and what kinds of projects each is best suited for.
-   ...that managing a software project depends on planning and feedback at multiple timescales.
-   ...that simple off-the-shelf tools can make participation in software projects easier.

**Tools:** I can use...

-   ...[GitHub][github] for project management (issues and pull requests).
-   ...[Make][make-lesson] for task automation.
-   ...[Travis-CI][travis-ci] for continuous integration.
-   ...[Sphinx][sphinx] for documentation generation.
-   ...[Pip and Setuptools][python-packaging] to create and install packages.
-   ...[Waffle][waffle] for backlog management.

## General {#s:guide-general}

It's all right not to get through the whole lesson.
:   This lesson is designed for people who have never programmed before,
    but any given class may include people with a wide range of prior experience.
    We have therefore included enough material to fill a full day if need be,
    but expect that many offerings will only get as far as the introduction to Pandas.

Don't tell people to Google things.
:   One of the goals of this less is
    to help novices build a workable mental model of how programming works.
    Until they have that model,
    they will not know what to search for or how to recognize a helpful answer.
    Telling them to Google can also give the impression that we think their problem is trivial.
    (That said, if learners have done enough programming before to be past these issues,
    having them search for solutions online can help them solidify their understanding.)
    Also,
    if you find anything,
    other folks were confused enough to bother with a blog or Stack Overflow post,
    so it's probably not trivial.

## Setup {#s:guide-setup}

In order to do the exercises in this course,
participants will need a [GitHub][github] account,
and will need to be able to write short programs on their laptops.
(We use Python in examples, but any modern language will do.)

## Versioning {#s:guide-versioning}

- Before the workshop, make a copy of the [SNDS repository](https://github.com/standage/snds-demo)
  by cloning it to your local system and pushing it to a new empty repo on Github
  (something like https://github.com/YourUsername/snds-demo-yyyy-mm-dd).
  Make sure to collect Github usernames from all participants pre-workshop so you can give them write access to the repo.
- The first pull request will be simple to merge.
  This will give an opportunity for a brief demo of the code review functionality, comment on particular lines, comment threads, etc.
- The second pull request will likely have a merge conflict.
  This is now super simple to handle in Github's web interface, and can also be covered in a very brief demo.

## Pragmatism {#s:guide-pragmatism}

-   You may need to meet people halfway if you want your project to grow
-   In particular, your collaborators might not be using version control
    -   And they might be right
-   Dropbox for files
    -   [Integrates with Git][git-dropbox]
    -   Non-trivial setup...
-   Similarly, they may not use LaTeX or Markdown for papers, and may be right there as well
    -   Google Docs for papers

> ...try to explain the notion of compiling a document to an
> overworked physician you collaborate with. Oh, but before that, you
> have to explain the difference between plain text and word
> processing. And text editors. And markdown/LaTeX compilers. And
> BiBTeX. And Git. And GitHub. Etc. Meanwhile he/she is getting paged
> from the OR...
>
> ...as much as we want to convince ourselves otherwise, when you
> have to collaborate with those outside the scientific computing
> bubble, the barrier to collaborating on papers in this framework is
> simply too high to overcome. Good intentions aside, it always comes
> down to "just give me a Word document with tracked changes," or
> similar.
>
> - [Stephen Turner][good-enough]

> Google Docs excels at easy sharing, collaboration, simultaneous
> editing, commenting and reply-to-commenting. Sure, one can approximate
> these using text-based systems and version control. The question is
> why anyone would like to...
>
> The goal of reproducible research is to make sure one
> can...reproduce...computational analyses. The goal of version
> control is to track changes to source code. These are fundamentally
> distinct goals, and while there is some overlap, version control is
> merely a tool to help achieve that, and comes with so much overhead
> and baggage that it is often not worth the effort.
>
> [Arjun Raj][quote-raj]

> Normal humans don't work like programmers expect them to
> because programmers haven't built tools that would let them.  
>
> - [Mike Hoye][quote-hoye]


{% include links.md %}
