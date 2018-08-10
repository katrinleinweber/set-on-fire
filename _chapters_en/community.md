---
permalink: "/en/community/"
title: "Build a Community"
questions:
-   "How can I turn a project into a community?"
objectives:
-   "Identify the two biggest barriers to contribution in open source projects."
-   "Explain how to choose the primary medium of discussion for a project."
-   "Describe common communication pitfalls in open projects."
keypoints:
-   "The two biggest factors affecting participation in open projects are ease of setup and warmth of response to first contribution."
-   "Specify a contributor code of conduct for your project."
-   "Use one primary channel for communication."
-   "Avoid common communication pitfalls."
---

-   Clearly identify members of core team
    -   Who is a primary part of the project and what rights does that give them
    -   What do *they* need to get out of the project and when (e.g., completion of thesis or contract)
    -   Review annually (at least)
-   Treat every user as a potential contributor
    -   Makes it more likely that others will use your software
    -   Increases the odds of survival for your work when funding runs out or you move on
    -   More likely to impact traditional academic metrics (i.e., citations)
-   Be clear about what peripheral participation means
    -   Make it clear that you respect research confidentiality and define what that actually means
        -   E.g., have explicit agreements about data availability, publication embargoes, etc.
        -   Even (or especially) if the project is "all open, all the time"
    -   Be explicit about when and how software changes will be integrated so that people have reasonable expectations
-   [Steinmacher][steinmacher-barriers] identified two main barriers to contribution in open projects
    1.  How easy is it to get set up?
    2.  How friendly was reception of first contribution?
-   Every project should include a contributor code of conduct
    -   And every project leader should think about [what it's like to be in a vulnerable group][ride-like-a-girl]
    -   Use [Contributor Covenant][contributor-covenant] by default
    -   Make the process for complaint, appeal, and adjudication *very* clear
        -   And make the first point of contact very clear as well
    -   Needs:
        -   Incident response plan (i.e., who does what when an incident occurs)
        -   Widespread promotion (people have to know it exists and where to find it)
-   Most important next step is to manage communication
    -   Small projects converge on one channel (i.e., issues, mailing list, Slack)
        -   "Someone mailed me your tweet about the Slack discussion so I filed a GitHub issue about updating the Google Doc. Wait, why are you crying?"
    -   Strongly prefer email for general discussion: ubiquitous, threaded, and asynchronous
        -   But only if publicly archived
        -   Point-to-point email makes key information unfindable and fosters cliques
    -   And discussion threads on issues for specific topics (to avoid overwhelming general channel)
-   Use video conferencing and in-person meetings to build community, not to share information
    -   People can read faster than you can talk
-   Avoid [common communication pitfalls][producing-oss-pitfalls]
    -   Don't post without a purpose
    -   Don't rehash previous discussion
        -   Summarize in blog posts or web pages and point people at those
    -   Avoid bikeshedding
        -   "The smaller the problem, the longer the debate"
    -   Throttle discussion
        -   One post per person per topic per day
-   [Recurse Center's social rules][recurse-social-rules]
    -   No feigning surprise
    -   No "well, actually"
    -   No back-seat driving
    -   No subtle -isms
-   Be clear when the group is deciding and when it is merely advising
    -   Distinguish between inquiry and delegation
        -   "Could you please look at X?" is ambiguous
-   Share management tasks as well as technical tasks
    -   Make it clear what has been delegated
    -   Follow up on everything you delegate
    -   Be clear about what "done" looks like

## Why a Code of Conduct? {#s:community-conduct-why}

A CoC lays out the expectations for interpersonal interaction in your project.
The CoC that we suggest using is the [Contributor Covenant][covenant],
which provides examples of acceptable and unacceptable behavior for your project,
and specifies how unacceptable behavior will be handled.
The goal of this is to explicitly communicate the standards of interaction to which this project holds its participants,
and encourage newcomers to the project to engage with the project.

This serves several purposes:

-   It reduces the uncertainty that project participants face about what is acceptable and unacceptable behavior.
    While you might think this is obvious,
    long experience suggests that articulating it clearly and concisely reduces problems caused by have different expectations.

-   It welcomes newcomers specifically, which can help grow your project and encourage user feedback.

-   It delineates responsibilities within the project and provides specific points of contact in case of misconduct or harassment,
    as well as specifying the process to be followed in these cases.

We find that most people agree with the standards laid out in the Contributor Covenant,
and believe that posting it entails no disadvantage.

## Exercises {#s:community-exercises}

### Code of Conduct

Add the Contributor Covenant or some similar code of conduct to your project.
(Do *not* create one of your own.)
What is the process for complaint, appeal, and adjudication?

### Channels

1.  What is your project's primary communication channel?
2.  Why and how was it chosen?
3.  What discussion(s) take place in other channels?
4.  Why?
5.  How easy or hard is it for a newcomer to find where things are being discussed?

{% include links.md %}
