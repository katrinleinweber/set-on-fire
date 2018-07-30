---
permalink: "/en/licensing/"
title: "Choose a License"
questions:
-   "Why do I need a license for my work?"
-   "What license should I use for my work?"
-   "How should I tell people what they can and cannot do with my work?"
objectives:
-   "Explain why adding licensing information to a repository is important."
-   "Explain differences in licensing and social expectations."
-   "Choose an appropriate license."
-   "Explain where and how to communicate licensing."
keypoints:
-   "People who are not lawyers should not try to write licenses."
-   "Every project should include an explicit license to make clear who can do what with the material."
-   "People who incorporate GPL'd software into their own software must make their software also open under the GPL license; most other open licenses do not require this."
-   "The Creative Commons family of licenses allow people to mix and match requirements and restrictions on attribution, creation of derivative works, further sharing, and commercialization."
---

-   Creative works are automatically eligible for intellectual property (and thus copyright) protection
-   Every creative work has some sort of license - the only question is whether authors and users know what it is
-   See [[Mori2012](#CITE)] and [this blog post][vanderplas-licensing] for overviews from a scientist's point of view
-   Every repository (version control or otherwise) should therefore include an explicit license
    -   Usually `LICENSE` or `LICENSE.txt` in root directory
    -   Clearly states under which license(s) the content is being made available
    -   Plural because code, data, and text may be covered by different licenses
-   Choose a license early
    -   Otherwise, each time a new collaborator starts contributing,
        they will hold copyright on their work
        and will thus need to be asked for approval when a license is chosen
-   **Don't write your own**
    -   Even if you are a lawyer
-   A few licenses are by far the most popular
    -   Choosing a common license makes project more intelligible
    -   [Open Source Inititative][osi-license-list] license list
    -   [choosealicense.com][choose-license] will help you find a license that suits your needs
-   Considerations:
    1.  Do you want to license the code at all?
    2.  Is the content you are licensing source code?
    3.  Do you require people distributing derivative works to also distribute their code?
    4.  Do you want to address patent rights?
    5.  Is your license compatible with the licenses of the software you depend on?
        -   E.g., can't use MIT on top of GPL

## Licenses for Software

-   [MIT/BSD](#g:mit-license): do whatever you want as long as you cite the original source,
    and the authors accept no responsibility if things go wrong
-   [GPL](#g:gpl): as above, but requires similar sharing

> You may copy, distribute and modify the software as long as you track changes/dates in source files.
> Any modifications to or software including (via compiler) GPL-licensed code must also be made available under the GPL
> along with build & install instructions.
>
> --- [tl;dr][tldr-gpl]

## Licenses for Data and Manuscripts

-   [CC-0](#g:cc-0): public domain
    -   Usually the best choice for data, since it simplifies aggregate analysis
-   [CC-BY](#g:cc-by): do whatever you want as long as you cite the original source
    -   Use for manuscripts, since you *want* people to share them widely
-   Other restrictions all inhibit specific use cases
    -   -ND: no derivative works (e.g., prevents translation or reformatting)
    -   -NC: no commercial use without explicit permission
        -   Some publishers try to imply that -NC means *nobody* can make money from it, which is untrue
    -   -SA: share-alike

## Exercises {#s:licensing-exercises}

### Can I Use an Open License?

Find out whether you are allowed to apply an open license to your software.
Can you do this unilaterally,
or do you need permission from someone in your institution?
If so, who?

### What Licenses Do My Dependencies Use?

Make a list of the licenses used by the projects that your project depends on.
Are there any conflicts between them and the license that you have chosen?

{% include links.md %}
