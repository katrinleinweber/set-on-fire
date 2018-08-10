---
permalink: "/en/process/"
title: "Development Process"
questions:
-   "What kind of development process should my project use?"
-   "What does a design-first development process look like?"
-   "How can I improve my project's development processes without becoming overwhelmed?"
-   "Under what circumstances can I suspend best practices?"
objectives:
-   "Explain the key features of agile development."
-   "Explain why agile development is a good fit for many new research software projects."
-   "Explain the key features of sturdy development."
-   "Explain why sturdy development is a good fit for many mature research software projects."
-   "Describe the concept of technical debt."
-   "Discuss strategies for principled compromises in software development best practices."
keypoints:
-   "Agile development is a software development process based on short iterations and rapid feedback."
-   "Key feedback loops are pair programming, test-driven development, continuous integration, and stand-up meetings."
-   "Agile works well for exploratory projects."
-   "Agile depends on high-bandwidth communication between developers and users, and on developers wanting to be empowered."
-   "Sturdy development is a software development process based on planning suitable for larger teams and more mature projects."
-   "Key features are division of labor, effort estimation, and long-term scheduling."
-   "Sturdy development is most suitable for large projects with well-defined goals."
-   "Technical debt must often be accrued to get a project off the ground, but must eventually be paid down for a project to grow."
-   "Use rapid iterative development to bring a project up to a minimally viable standard."
-   "Software engineering best practices are not a goal unto themselves, but means to an end."
-   "Ensure the scientific core of your project is sound. Otherwise, fix bugs when they come along, and then get back to science."
---

FIXME
-   software lifecycle
    -   What needs to be done?
    -   Why?
    -   Who's doing it?
    -   When is it due?
    -   What state is it in (i.e., are we done yet)?
    -   Where is everything?
    -   How do we do things?
-   Technical debt
    -   Dissonance between (constantly refining) conceptual model and the model reflected in code
    -   Informed, deliberate suspension of best practices
    -   Term popularized by tech startup culture
-   Constant tradeoff
    -   Usually necessary to get a project off the ground
    -   Complicates sustained development
        -   Maintaining and extending requires going back and cleaning up
        -   Debt must be "paid down"...usually with interest
-   None of the best practices discussed in this workshop are a goal unto themselves
    -   They are means to an end
    -   What are the ends of your project?
        -   This will depend on whether the software is:
            -   One-time-use code supporting a single research project
            -   A generalized tool for analyzing particular types of data sets
            -   A software library supporting new analytical and methodological developments in a problem domain
        -   This will also depend on what part software plays in your career/research
            -   Is your job primarily to write software and/or support others in doing so?
            -   Is your job primarily to advance research in your field by producing new results, theories, models, methods, and data?
            -   Is your job primarily to teach, mentor, and/or manage others?
    -   Regardless, in science, priorities should be:
        -   Accuracy
        -   Performance
        -   ...
        -   ...
        -   ...
        -   User experience (we're not building dating apps here)
-   Rapid iterative development strategy
    -   Build a quick prototype
    -   Evaluate accuracy
    -   If performance is unsatisfactory
        -   Profile performance empirically
        -   Optimize code surgically
    -   Clean up code
-   Incremental improvement
    -   Don't try to FIX ALL TEH THINGS AT ONCE!
    -   Instead, whenever you touch a function to fix or extend it, clean it up then
        -   Check for code clarity
        -   Improve documentation and comments
        -   Write unit tests
    -   Improvements will accumulate quickly
-   Winning strategy: [stupidity-driven development][stupidity-driven]
    -   Write lots of tests for the scientific core of the code
    -   Dont fuss too much about everything else
    -   When a bug is encountered
        -   write a new regression test to reproduce the bug
        -   fix the bug
        -   get on with more important things
    -   Mantra: avoid wasting time writing tests for bugs that will never appear!

## Agile Development {#s:process-agile}

-   *Agile development* fits well with how most researchers work
-   Term coined in 2001 to describe bottom-up style of software project management
    based on short iterations and frequent feedback at many scales
    -   Practices are almost as old as programming,
        but came into their own with the rise of the web
    -   Made daily (even hourly) "releases" possible
    -   Multi-year development plans didn't make sense when everything
        they depended on would be obsolete by the time work started

<figure>
  <img src="../../files/agile-feedback.png" alt="Agile Feedback Loops" />
  <figcaption id="f:process-agile-feedback">Agile Feedback Loops</figcaption>
</figure>

-   Key feature is *short iterations*: single day to two weeks
    -   In each iteration, the team decides what to build next, designs it,
        builds it, tests it, and delivers it
    -   Users don't  know what they want until they see it,
        so short cycles avoid building things people don't actually want
    -   Most people can organize time for a few days without much effort,
        so short cycles reduce proportion of time spent on coordination
-   This exploratory approach makes agile a good fit for young research software
    -   Researchers often can't know what to write next
        until they've seen the output of the current program
-   Every day starts with a *stand-up meeting* where everyone reports:
    -   What they did the day before
    -   What they're planning to do that day
    -   What's blocking them (if anything)
    -   Called a "stand-up" meeting because it's held standing up,
        which encourages people to stay focused
    -   Encourages people to break work down into tasks that are at most one day long
    -   If someone to says "still working on X" several days in a row,
        they're not giving meaningful feedback on their progress
-   The PI is typically the *product owner* with ultimate say over what functionality the software has
    -   Not necessarily the same as what changes are made, since one feature can satisfy many needs (and one need may require many new features)
-   Agile development works best when:
    1.  Requirements are constantly changing, i.e., long-range planning
        isn't possible anyway. This is often the case for scientific
        research, particularly at the small scale.
    2.  Developers and users can communicate continuously, or at worst
        daily or weekly. Again, this is normal for small-scale research,
        where developers and users are the same people.
    3.  The team is small, so that everyone can take part in a single
        stand-up meeting. This is usually also true, though getting
        everyone to show up for a morning meeting is a challenge in many
        labs.
    4.  Team members are disciplined enough not to use "agile" as an
        excuse for cowboy coding.
    5.  They actually *like* being empowered.
-   The last two points are the most important.
    -   Most developers don't like writing plans before they code, or documentation when they're done.
        -   Coincidentally, agile doesn't require them to do much of either.
        -   It's therefore all too common for developers to say "we're agile"
            when what they mean is "we're not going to bother doing anything we don't want to".
        -   In reality, agile requires *more* discipline, not less, just as
            improvising well requires even more musical talent than playing a score
            exactly.
    -   In addition, some people don't like making decisions
        -   Many become quite defensive when told that figuring out what to do is
            now part of their job, but that's as essential to agile development as
            it is to scientific research.

## Sturdy Development {#s:process-sturdy}

-   [Sturdy development](#g:sturdy-development) is a made-up term to describe "classic" software engineering practices
    -   Didn't need a name until agile came along
-   Best suited for situations in which:
    -   Stakeholders insist that developers make commitments to long-term goals (typical of grant cycles)
    -   Work is so large that division of labor is essential
-   Key assumption: measure twice, cut once
    -   The later a problem is caught, the more expensive it is to fix
    -   So careful up-front planning can pay for itself by reducing effort downstream
    -   Truest when the problem domain, good solution strategies, and technologies are all well understood

<figure>
  <img src="../../files/sturdy.png" alt="Sturdy Lifecycle" />
  <figcaption id="f:process-sturdy">Sturdy Lifecycle</figcaption>
</figure>

-   Gather requirements to figure out what the software is supposed to do
    -   The responsibiliyt of the [product manager](#g:product-manager)
    -   While developers are working on version 4, she talks to stakeholders about what they want in version 5
    -   Never ask them what features they want in the software, but rather:
        -   What does it do now that you don't like?
        -   What can't you do that you'd like to be able to?
    -   Product manager collates these needs and figures out how the software should be changed to satisfy them
-   [Analysis and estimation](#g:analysis-and-estimation): figure out how long features will take to implement
    -   Each team member is responsible for analyzing and estimating one or more features
    -   Must come up with a plausible rough design, and estimate how long it will take to implement
    -   Where possible, come up with two such plans:
        -   One for the whole feature
        -   One for a useful subset requiring less effort
    -   A&E presupposes an overall architecture for the system has already been defined
    - Doesn't make sense to say, "We'll create a plugin to handle that" unless there's a plugin system
-   Prioritization: because there's always more to do than there is time to do it
    -   Create a 3x3 grid whose axes are "effort" and "importance"
        -   Effort should be "an hour", "a day", "a week"
        -   Anything longer than a week should be broken into sub-tasks
        -   Importance is "low", "medium", "high"
    -   Each feature goes into one square
    -   Then draw a diagonal and throw away everything below it that requires a lot of effort but isn't important

<figure>
  <img src="../../files/prioritize.png" alt="Prioritization" />
  <figcaption id="f:process-sturdy-prioritize">Prioritization</figcaption>
</figure>

-   Create a schedule
    -   Who is going to do what, when?
    -   Do *not* shave estimates to make things fit
        -   Undermines trust on both sides and leads to "science fiction scheduling"
    -   Schedule is owned by the *project manager*, whose job it is to decide when to abandon or reschedule work and what to do instead
    -   E.g., if a high priority item is taking longer than expected, should it be put on hold and work started on something with lower priority requiring less effort?
    -   The earlier you let stakeholders know that things are going to be late (or aren't going to get done at all), the less unhappy they'll be
    -   Note: estimation improves with practice
-   Do the work
    -   In practice, some work starts during A&E, since people need to prototype to see if their designs are plausible
    -   Testing and documentation start at the same time as coding
        -   Or even earlier: A&E should include estimates for time required to test and explain
    -   Also start deploying at the same time as development
        -   Needed for testing
        -   And need to test packaging and deployment along with everything else
-   Stop adding features about 2/3 of the way through the allotted time
    -   Experience shows that teams need at least 1/3 of the overall cycle to fix bugs and tidy up
-   Sturdy development relies on having good requirements
    -   As unambiguous as a legal contract or a theorem proof
    -   I.e., two well-informed practitioners should reach the same conclusions about correctness
-   "The system will reformat data files as they are submitted" isn't enough---should have:
    -   Only users who have logged in by providing a valid user name and password can upload files.
    -   The system allows users to upload files via a secure web form.
    -   The system accepts files up to 16MB long.
    -   The system accepts files in PDB and RJCS-1 format.
    -   The system converts files to RJCS-2 format before storing them.
    -   The system displays an error message page if an uploaded file cannot be parsed, but takes no other action.
    -   Etc.
-   Best to specify requirements as tests ((s:testing)[#CHAPTER]),
    but those can still require human-readable explanation

## Exercises {#s:process-exercises}

### Are You Agile?

1.  Which of the key agile practices described above are you currently using?
2.  Which do you think you and your team would actually adopt in the next 3-6 months?
3.  Which do you think are not good fits to your needs or situation?

### Prioritize

1.  Draw a 3x3 grid of the kind described above.
2.  Pick 3-4 open issues for your current project.
3.  Decide where each one belongs on the grid.
    Are any of them so large that they should be broken down into sub-tasks?

### Write Requirements

1.  Write an unambiguous specification of a feature you would like to add to your current project.
2.  Swap specifications with your partner.
3.  What is the least helpful (or most damaging) implementation of your partner's feature you can think of
    that would technically satisfy the specification they wrote?

{% include links.md %}
