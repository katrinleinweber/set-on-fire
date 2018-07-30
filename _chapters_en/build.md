---
permalink: "/en/build/"
title: "Automated Builds"
questions:
-   "How should I automate tasks I do repeatedly?"
objectives:
-   "Explain what build managers were originally designed to do, and what else they are now used to do."
-   "Make a build file self-explaining."
-   "Explain when to use checklists rather than a build manager."
keypoints:
-   "Use a build manager to manage repetitive tasks."
-   "Make build files explain themselves."
-   "Use checklists for tasks that have to be done repeatedly, but can't be done by a computer."
-   "Have new contributors go through checklists to look for omissions and inaccuracies."
---

-   DRY: Don't Repeat Yourself
    -   Usually applied to nouns (code)
    -   Just as true for verbs (actions)
    -   The only thing you can accomplish by typing something repeatedly is to get it wrong
-   Use a [build manager](#g:build-manager)
    -   [GNU Make][gnu-make] defined the category
        -   Has its own (quirky) syntax
        -   Depends on native shell commands for operations
    -   [SnakeMake][snakemake] and similar tools are modern descendents
    -   [SCons][scons], [doit][pydoit], and others use the syntax of a full-blown programming language to achieve the same ends
-   Originally created to compile multi-file programs efficiently, but can all be used for arbitrary tasks
    -   Run tests
    -   Build packages for release
    -   Create reports
-   Key feature: [dependencies](#g:dependency)
    -   "A depends on B and C, both of which depend on D"
    -   If D changes, B and C are rebuilt once, and then A is built
    -   Tracking can be implemented using timestamps
        -   Fast to check
        -   But not always reliable for very short tasks on networked systems
    -   Or via [file hashes](#g:hashing)
        -   Slightly slower
        -   Requires persistent storage
        -   Reliable across machines
-   File dependencies aren't always a good base for workflow
    -   Not all actions produce files
-   General workflow tools may be a better fit for some kinds of research
    -   [Galaxy][galaxy] is a high-end tool
    -   [doit][pydoit] is a lot easier to start with
    -   Only as stable as the pieces they connect: workflows can rust if not maintained
    -   [Common Workflow Language][cwl] is an attempt to unify some of these tools
-   And debugging builds is often challenging, no matter what the tool
-   A [checklist]{#g:checklist} is a set of build instructions meant to be executed by a human being
    -   [[Gawa2007](#CITE)] describes how use of checklists cuts fatalities in surgery significantly
    -   Use them for anything that *can't* be done automatically by a machine
    -   Keep in version control
        -   Ask every new contributor/user to use *and give feedback*
        -   Include a contact email address in every checklist
-   Most issue-tracking systems ([s:issues](#CHAPTER)) allow you to specify template text for new issues
    -   These may support tick boxes
    -   Use them for checklists

## Exercises {#s:build-exercises}

### Create a Task list

1.  If your project already uses a build manager,
    what tasks are used most often?
2.  If your project *doesn't* use a build manager,
    what are the first few tasks you should automate?

### Self-Documenting Build Files

The default target in a build file (e.g., `make` with no parameters)
should print a list of available commands.
Look at the `Makefile` in this repository to see how this works,
then modify the build file for your project to do so as well.

### Create a Setup Checklist

1.  Write a short point-form checklist describing the things you do
    when setting up a new machine to do development on your project.
2.  How many of the steps in your checklist can be automated using shell scripts or other small programs?
3.  How will newcomers know if they have completed the steps in the checklist correctly?

{% include links.md %}
