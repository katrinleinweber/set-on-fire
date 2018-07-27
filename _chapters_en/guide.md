---
permalink: "/en/guide/"
title: "Instructors' Guide"
---

See [[Wils2018](#CITE)] for general notes on lesson design.

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
