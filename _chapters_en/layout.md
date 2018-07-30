---
permalink: "/en/layout/"
title: "Project Layout"
questions:
-   "How should I organize my research software project?"
objectives:
-   "Explain Noble's rules and emphasize the principle of organizing and naming files to reflect their content or purpose."
keypoints:
-   "Name each project component (code, data, metadata, etc.) according to its content or purpose."
-   "Group similar project files into dedicated directories."
-   "Take advantage of widely used project organization conventions unless there is a compelling reason not to."
---

-   Project organization is like a diet
    -   There is no such thing as "no diet", just a good one or a bad one
    -   Similarly, there is no such thing as "no project organization"
    -   Your project is either organized *well* or organized *poorly*
-   A model of good organization: [Noble's rules][noble-rules]
    -   Source code in `src/` (short for "source")
    -   Compiled programs in `bin/` (short for "binary", meaning "not source")
    -   Raw data in `data/`
        -   If it's too large, use `data/` to store data references or proxies ([s:data](#CHAPTER))
    -   Results in `results/`
    -   Documentation and manuscripts in `doc/`

<figure>
  <img src="../../files/placeholder.png" alt="Noble's Rules" />
  <figcaption id="f:noble">Noble's Rules</figcaption>
</figure>

-   A few files Noble didn't mention that have become conventional
    -   `README`: one-paragraph description of the project
    -   `LICENSE`: the project's license ([s:licensing](#CHAPTER))
    -   `CONDUCT`: its code of conduct ([s:community](#CHAPTER))
    -   `CITATION`: how the work should be cited ([s:publishing](#CHAPTER))
        -  May have a separate `CONTRIBUTORS` file, or list contributors in `CITATION`
    -   These files may be plain text or Markdown, or have no suffix at all, but please use the principal names as given
-   Name files according to their content in ways that are easy to match with [globs](#g:glob) or [regular expressions](#g:regular-expression)
    -   Bad: `antelope field data (latest).csv`
    -   Good: `castratragus-lemuria-2018-06.csv`
    -   This "species-location-year-month" format makes it easy to select files by species, location, or date
    -   Which in turn will simplify automation ([s:build](#CHAPTER))
-   Group similar files in meaningfully-named directories
    -   Bad: putting the results your colleague just emailed you in `todo/*.csv`
    -   Good: creating `results/standage-deduplicated-2018-06/` and putting files there
    -   Don't worry about long directory names: [tab completion](#g:tab-completion) means you only have to type them once

## Exercises {#s:layout-exercises}

### Current Project Organization

Draw a diagram like [f:noble](#FIGURE) showing how your project is currently organized.

-   Are all your projects organized this way?
-   Is this structure documented anywhere?
-   Are there any changes you could make to take advantage of common conventions?

### Current File Naming Conventions

How are the files in your project named right now?
Are they all named consistently?

### Standard Files

If your project does not already have `README` and `CITATION` files,
add them to its root directory.
(We will add a license and a code of conduct after [s:license](#CHAPTER) and [s:community](#CHAPTER) respectively.)

{% include links.md %}
