---
permalink: "/en/issues/"
title: "Tracking Work"
questions:
-   "How can I keep track of who's doing what?"
-   "How can I keep track of what needs to be done?"
objectives:
-   "Describe what sorts of things should be recorded in an issue-tracking system."
-   "Describe what goes into a well-written issue."
-   "Explain how issue-tracking systems can be used to implement workflows."
-   "Explain how issue-tracking systems can be used to focus attention where it's needed."
keypoints:
-   "An issue-tracking system is a shared to-do list for a project."
-   "Every issue has a few mandatory fields to help with searching, and free-form text for details."
-   "Every issue is in a particular state."
-   "A project can define a workflow by specifying who can change tickets' states when."
-   "Use tickets to prioritize work: what needs be done now, what can be deferred until later."
---

-   Version control tells you where you've been; [ticketing](#g:ticketing) tells us where you're going
    -   Ticketing tools are often called bug trackers,
        since they were created to keep track of work that nees to be done and bugs that needed fixing
    -   Or issue trackers, since that sounds more corporate
-   Every ticket has:
    -   Unique ID/link
    -   One-line summary to aid browsing and search
    -   Status (discussed below)
    -   Creator's ID
    -   Other people's IDs
    -   Full description that may include screenshots, error messages, etc.
    -   Threaded discussion
-   Use it to:
    -   Describe bugs, and solicit/collect bug reports from community
    -   Request, plan, and discuss new features
        -   "Discuss" because most allow reply-to discussion threads, and will notify people who are already on the thread of updates
    -   Ask questions
        -   Repurposes the discussion capability
        -   If search is good and someone's willing to add tags, old issues can act as a FAQ
-   Use ticketing to prioritize work
    -   Create a tag for the next work sprint (typically called `V3.1` or `2018-03`)
    -   Assign that tag to tickets that the group is going to try to close by that time
-   More sophisticated systems allow people to:
    -   Record dependencies between tickets
    -   Estimate how long work will take
    -   Record how long work actually took
    -   Don't worry about any of this until people are actually using tickets...

## Status and Lifecycle {#s:issues-status}

-   Use tags to distinguish:
    -   Bug: something should work but doesn't
    -   Enhancement: something could/should be added
    -   Task: something needs to be done, but won't show up in code (e.g., we need to get the next release out by February)
    -   Question: how is something supposed to work?
    -   Discussion: we need to make a decision about something
        -   All tickets can have discussion - this category is for ones that start that way
-   Add extra tags to distinguish:
    -   High Priority: small projects typically can't take advantage of multiple priority levels, so don't bother with them
    -   Won't Fix/Works as Designed/Duplicate: reasons for closing without acting
    -   Verified/Accepted/Decided: yes, this bug needs fixed, this feature should be added, or we've decided what to do
    -   Ready for Review/Ready to Merge: self-explanatory
    -   Accomplished: this task has been done
-   And assign people:
    -   Creator: usually added automatically by the system
    -   Owner: who's doing the work/moderating the discussion
    -   Reviewer: who's checking
-   Helpful to have one more tag: *Suitable for Newcomer* or *Beginner*
    -   If you help potential new contributors find places to start, they're more likely to do so
-   Can use ticket status to make the development lifecycle explicit
    -   I.e., only allow certain state transitions
    -   And notify interested parties of state transitions

<figure>
  <img src="../../files/issue-lifecycle.png" alt="Issue Lifecycle" />
  <figcaption id="f:issue-lifecycle">Issue Lifecycle</figcaption>
</figure>

-   Don't worry about any of this until people are actually using tickets...

## How to Write a Good Bug Report

1.  Make sure it actually *is* a bug.
2.  Try to come up with a short, repeatable way to trigger it.
    -   You'll be surprised how often you can solve the problem yourself as you do this...
3.  Write a descriptive short summary (something better than "program crashes")
4.  Describe how to reproduce
    -   Describe both what you expected and what it actually does
5.  Attach screenshots, input files, etc.
6.  Make sure to describe software version, operating system, etc.
7.  Describe each problem separately

~~~
ID: 1278
Creator: standage
Owner: malvika
Tags: Bug, Verified
Summary: wordbase.py fails on accented characters
Description:
1.  Create a text file called 'accent.txt' containing the word "Pümpernickel"
    with an umlaut over the 'u'.

2.  Run 'python wordbase.py --all --message accent.txt'

Program should print "Pümpernickel" on a line by itself, but instead
it fails with the message:

    No encoding for [] on line 1 of 'accent.txt'.

([] shows where a solid black box appears in the output instead of a
printable character.)

python wordbase.py --version reports 0.13.1; using on Windows 10.
~~~

## Exercises {#s:issues-lifecycle}

### What's On Your List?

1.  What are the top 3 items on your project's to-do list?
2.  How sure are you that your collaborators and users would agree with your selection?

### What's Your Lifecycle?

Ticket status is sometimes organized by [stages of grief][twitter-grief].

1.  What states can your project's issues be in?
2.  What state transitions are allowed?  ("Any to any" is a common and acceptable answer.)
3.  Who decides when an issue can move from one state to another?

{% include links.md %}
