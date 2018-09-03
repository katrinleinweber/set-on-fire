---
permalink: "/en/hosting/"
title: "Hosting"
questions:
-   "Where should I host my version control repositories?"
objectives:
-   "Explain different options for hosting scientific work."
keypoints:
-   "Projects can be hosted on university servers, on personal domains, or on public forges."
-   "Rules regarding intellectual property and storage of sensitive data apply no matter where code and data are hosted."
---

-   Hosting considerations
    -   Privacy: what level, if any, of restricted access do you need?
    -   Ownership and branding: are `something.github.io` or `yourname.wordpress.com` good enough, or do you need an institutional domain or a personal one?
    -   Reliability: how important are continuous availability and control over when downtime occurs
        -   It's really annoying when someone you've never met takes your site down for maintenance just as you're about to do a demo...
    -   Management burden: unfortunately, increasing any of the above requires time and money
-   Option 1: lab, department, university, or company provides server, manages accounts and backups, etc.
    -   Pro: clarifies who owns what
        -   Particularly important if any of the material is sensitive
            (i.e., relates to experiments involving human subjects or may be used in a patent application)
    -   Con: cost often higher than commercial services
    -   Con: longevity
        -   Someone who has spent ten years collecting data wants it to be available 10 years from now
        -   That's well beyond the lifespan of most of the grants that fund academic infrastructure
        -   Empirically, link rot is a huge issue with research software
-   Option 2: purchase a domain and pay an Internet service provider (ISP) to host it
    -   Pro: gives the individual or group more control
    -   Pro: sidesteps problems that can arise when moving from one institution to another
    -   Con: requires more time and effort to set up than other options
    -   Con: may not be allowed
-   Option 3: public host service
    -   [GitHub][github], [GitLab][gitlab], [BitBucket][bitbucket], [SourceForge][sourceforge], etc.
    -   All provide web interface to
        -   Create, view, and edit projects
        -   Communication and project management tools
    -   Pro: economies of scale
    -   Pro: network effects (potential collaborators probably already know how to use them)
    -   Con: public (or only a limited amount of privacy)
        -   Unless you pay
        -   And even then, out-of-institution/out-of-country hosting can be problematic
    -   Con: can be shut down, purchased, etc.
-   Institutional considerations
    -   Sharing is the ideal for academic research, but:
        -   Many research software projects aren't academic
        -   Even publicly-funded academic institutions often place restrictions on sharing,
            e.g., to protect potentially patentable intellectual property
    -   *Ask someone*
        -   It's easier to get forgiveness than permission, but forgiveness isn't guaranteed
        -   If you encounter restrictions, ask about the underlying motivations
        -   Can sometimes request exceptions for specific projects
        -   And understanding reasons helps formulate a push for institutional reform
-   Sharing code vs. sharing publication
    -   Sites like GitHub are meant for sharing things while they're being developed
    -   Services like [arXiV][arxiv] and [figshare][figshare] are for archiving particular snapshots of things for future reference
    -   There's overlap
        -   Tagging a version of code in a repository
        -   Posting a pre-print and updating it later
    -   Workflow: tag on GitHub, get a DOI from [Zenodo][zenodo], post pre-print on [arXiv][arxiv], submit to open access journal for publication of record

## Exercises {#s:hosting-exercises}

### Can My Work Be Public?

Find out whether you are allowed to host your work openly on a public forge.
Can you do this unilaterally,
or do you need permission from someone in your institution?
If so, who?

### Where Can I Share My Work?

Does your institution have a repository or repositories that you can use to share your papers, data, and software?

{% include links.md %}
