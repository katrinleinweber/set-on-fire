---
permalink: "/en/versioning/"
title: "Versioning"
questions:
-   "What do I need to know about version control beyond commit, push, and pull?"
objectives:
-   "Explain how to use feature branches to manage software development."
keypoints:
-   "Use version control for everything created manually, not just code."
-   "Create a new branch for each feature."
-   "Only use that branch for that feature."
-   "Merge and delete the branch when the feature is complete."
---

-   Assume that:
    1.  Your project is already under version control
        -   If not, this may not be the right course for you
    2.  You use version control for everything created by human beings
        -   Tools like LaTeX and Markdown survive in part because plain text is the only thing version control handles well
        -   It would be a *lot* easier for newcomers to adopt version control
            if it supported office document formats, PDFs, etc.,
            but that's a rant for another time
    3.  You are using Git and [GitHub][github]
        -   Git's interface is needlessly convoluted [[Pere2013](#CITE),[Pere2016](#CITE)]
        -   But it's the price you have to pay to use GitHub...
        -   ...which is what most research projects have adopted
-   Use a [feature branch workflow](#g:feature-branch-workflow)
    -   Designate one branch as the copy of reference (typically `master`)
    -   Create a new branch from `master` for each change
    -   Only use that branch for that feature
    -   Merge the branch when the feature is done
-   Common scenario: part way through change X, realize that you also want/need to do Y
    -   Commit work to date
        -   Avoid `git stash`: it's just another layer of confusion
    -   Create a new branch for Y off `master`
    -   Do the work, merge to `master`, and then merge `master` into `X` and carry on
-   But commits are supposed to be completed steps forward, not backups of incomplete work
    -   Use `git rebase` to collapse several recent commits into a single commit for archiving
    -   Rewrites history...
    -   ...but that's OK if the result is a cleaner historical record
    -   Rebasing can be tricky if there have been lots of complicated merges...
    -   ...so stick to the "branch=feature" pattern
-   Use [annotated tags](#g:annotated-tag) to mark every major event in the project's history
    -   Annotated because they allow a message, just like a commit
    -   Use semantic versioning for software releases ([s:robust](#CHAPTER))
    -   Use `manuscript-date-event` for publications
        -   E.g., `jse-2018-06-23-response`

## Exercises {#s:versioning-exercises}

### How Do You Manage Your Repository?

Describe in 3-4 bullet points how you actually manage your version control repository.
How often are you or your team working on several things simultaneously?

### Feature Branch Workflow in Action

-   Clone the example repository to your laptop
-   Create a new branch with a unique label (such as your last name) and check out that branch.
-   Add your name and email address to its `CONTRIBUTORS.md` file.
-   Commit your changes,
    push your new branch to Github,
    and open a new pull request to merge your feature branch into `master`.

### Tagging

If you are not already using annotated tags in your project,
create a tag for the last major event in its history.
What naming convention are you using for tags, and why?

{% include links.md %}
