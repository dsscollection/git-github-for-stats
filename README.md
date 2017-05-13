Excuse me, do you have a moment to talk about version control?
================
Jenny Bryan
2017-05-12

Why Git?
--------

Why would a practicing statistician use version control, such as Git? And what is the point of hosting your work online, e.g., on GitHub? Could the gains possibly justify the inevitable pain?

I say yes, with the zeal of the converted.

Benefits of using hosted version control in your statistical practice:

-   Doing your work becomes tightly integrated with organizing, recording, and disseminating it. It's not a separate, burdensome task you are tempted to neglect.
-   The marginal effort required to create a web presence for a project is negligible. It's not a separate, burdensome task you are tempted to neglect.
-   GitHub makes a fantastic course management system for courses that use R. You and your students can exchange actual working code and explore the associated results.
-   By using common mechanics across work modes (research, teaching, analysis), you achieve basic competence quickly and avoid the demoralizing forget-relearn cycle.

What is Git?
------------

[Git](http://git-scm.com) is a **version control system**. Its original purpose was to help groups of developers work collaboratively on big software projects. Git manages the evolution of a set of files -- called a **repository** -- in a sane, highly structured way. It is a bit like the "Track Changes" feature from Microsoft Word, but more rigorous, powerful, and scaled up to multiple files.

Git has been re-purposed by the data science community. In addition to using it for source code, we use it to manage the motley collection of files that make up typical data analytical projects, which often consist of data, figures, reports, and, yes, source code. Even those who identify more as statistician than data scientist generally have a similar mix of files that are the artifacts of a project.

A lone ranger, working on a single computer, can benefit from adopting version control. But not nearly enough to justify the pain of installation and workflow upheaval. There are much easier ways to get versioned back ups of files, if that's all you're worried about.

In my opinion, **for new users**, the pros of Git only outweigh the cons when you factor in the overhead of communicating and collaborating with other people, including your future self. And who among us does not need to do that? Your life is much easier if this is baked into your workflow, as opposed to being a separate process that you dread and avoid. Communication and collaboration are the killer apps of version control. Git enforces a rigorous model of file management, but it is critical for the distribution of files across different people, computers, and time.

Many people who don't use Git unwittingly re-invent a poor man's version of it. They take an important file and distribute it via email. Various parties make changes, decorating the file name with initials, dates, and other descriptors. Before you know it, the original file is the root of a complicated phylogeny that no amount of "Track changes" and good intentions can resolve.

The Git way is to track the evolution of that file, through a series of commits, each equipped with an explanatory message and a nickname. All collaborators sync regularly to a common version, acknowledging that the difficulty of merging goes up faster than the size of the difference (cite good enough). Especially important versions get a human-readable tag, to signal a meaningful milestone. Yes, there is some pain in adopting the formalism of Git, but it is worth it.

Who should read this and what to expect
---------------------------------------

The target reader is anyone who does statistical research, analysis, or instruction. Those whose work is some combination of these three may find the work style described here especially rewarding.

This article does not provide step-by-step instructions on how to use Git and GitHub. This format would not be effective, but we do provide links to such resources. Instead, I'll convey what the workflow feels like and what the payoffs are, with special attention to the statsitics and R context. The goal is to help the Git-curious generate the activation energy needed to get started.

What is GitHub?
---------------

[GitHub](https://github.com) is currently the most popular Git hosting service. Others include [GitLab](https://about.gitlab.com) and [Bitbucket](https://bitbucket.org). These services provide a home for Git-based projects on the internet. It is a bit like DropBox or Google Drive, but more structured, powerful, and programmatic.

The remote host acts as a distribution channel or clearinghouse for a Git-managed project. This allows other people to see the project files, sync up with the current version, and perhaps even make or propose changes. These hosting providers offer well-designed web interfaces that are a dramatic improvement over traditional Unix Git servers. Many operations can be done entirely in the browser, such as viewing current or past versions of a file, commenting on a recent change, and editing or adding files.

Even for private solo projects, there are two advantages to keeping a synced copy on GitHub:

1.  When you are new with Git (or, frankly, even when you're not), it's common to goof up the Git infrastructure for a project. Note that your files can absolutely be intact and safe, even while the Git tracking is a bit confused. Of course there are official Git remedies, but sometimes the easiest fix is to clone a fresh copy from GitHub, patch things up with the changes that only exist locally, and move on with your life. This workaround obviously requires the existence of a recent copy on GitHub.
2.  The highly functional web interfaces mentioned above are often the most pleasant and natural way to navigate and search your files, even though all the same information exists locally. It is a pleasure to browse through your own work, across multiple projects or files and across time, as if it's a well-designed website. You must push your work to GitHub to enjoy this.

GitHub **issues** are another powerful feature of the platform. Recall that we are repurposing Git, a tool designed to facilitate software development. The issues for a project are its bug tracker. For projects that are not pure software development, we use this machinery to organize our to do list more generally. The basic unit is an issue and you can interact with them in two ways. First, issues are integrated into the project's web interface on GitHub, with a rich set of options for linking to project files and incremental changes. Second, issues and their associated comment threads appear in your email, just like regular messages (this can, of course, be configured). The result is that all correspondence about a project comes through your normal channels, but is also tracked inside the project itself, with excellent navigability and search capabilities.

Issues can be assigned to specific people and they can be labelled, e.g. "bug", "simulation-study", or "final-exam". Coupled with the ability to cross-link issues and the project files or file changes, you have extraordinary power to document why things have happened in the past and to organize what needs to happen in the future.

Initial Git setup
-----------------

This is one-time or once-per-computer setup.

-   Register for a free account with GitHub.

-   Install Git. Depending on your OS, Git might already be installed. But many of us will need to do this.

-   Install a local Git client. Optional but highly recommended. A Git client is software that provides a graphical user interface for Git, which is otherwise command-line only. If you are an R user, you will find that RStudio provides a great deal of this functionality. There are some notable gaps, however, so you might still choose to install a dedicated and comprehensive Git client such as SourceTree or GitKraken. Git is a file-based system, so you can do some operations from RStudio, others from SourceTree, and others from the shell.

-   Confirm, with a practice repository, that local Git can send and receive the current version of the repository on GitHub, known as *pushing* and *pulling*, respectively. This will require authenticating yourself with GitHub from a local shell or Git client. At this point, most people elect to do a bit of extra setup to ensure that they are not repeatedly challenged for their GitHub credentials going forward.

Don't get caught up on these things
-----------------------------------

I target [GitHub](https://github.com) -- not [Bitbucket](https://bitbucket.org) or [GitLab](https://about.gitlab.com) -- for the sake of specificity. However, all the big-picture principles and even some mechanics will carry over to these alternative hosting platforms. I am advocating for the use of hosted version control as a general concept, with GitHub being the best and most common provider today. I note that many companies and even universities are starting to make GitHub Enterprise or GitLab available internally.

Don't fret too much about public versus private repositories at this point. All the major hosting providers offer private repositories with flexible control over who can read or write to the repo. There are many ways to get private repositories for low or no cost, especially for academics. Just get started and figure out if and how Git/GitHub is going to work for you. If you outgrow this initial arrangement, you can throw some combination of technical savvy and money at the problem. You can either pay for a higher level of service, self-host one of these platforms, or connect with / advocate for organization-wide solutions. You can also leave more things public than you think, because one's early days with Git and GitHub generally do not attract a keen audience. It is also easy to delete repos or clear the history.

Is this going to hurt?
----------------------

Yes.

Git was built neither for the exact usage described here, nor for broad usability. You will undoubtedly notice this, so, no, it's not you. Happily there are many helpful tools that mediate your interactions with Git. GitHub itself is a fine example. In addition to pointing out tools that soften Git's sharpest edges, I recommend specific habits and attitudes that reduce frustration.

General recommendations for agony reduction:

-   Consider installing a graphical front-end for Git, a.k.a. a "Git client", on your computer, versus restricting yourself to the command line interface.
-   Establish confidence in the basics (e.g. make a change, commit it, push it) before wading into more advanced usage (e.g. branching).
-   Commit yourself to Git usage on a project that will provide sustained practice over several months. Usage in a course is great, because it provides a relentless stream of small deadlines.
-   Realize that no one is giving out Git style points. It's ok to "power-cycle", i.e. re-initialize the Git repository, to get unstuck.

Repositories and workflow
-------------------------

For new or existing projects, you will:

-   Dedicate a directory (a.k.a "folder") to it.
-   Make it an RStudio Project. Optional but recommended; obviously only applies to projects involving R and users of RStudio.
-   Make it a Git repository.

This is once-per-project setup and can happen at project inception or at any later point. Chances are your project already lives in a dedicated directory. Making this directory an RStudio Project and Git repository boils down to allowing those applications to leave notes for themselves in hidden files or directories. The project is still a regular directory on your computer, that you can locate, name, and interact with as you wish.

Here is the daily workflow:

-   Go about your usual business, e.g. writing R scripts or authoring reports in LaTeX or R Markdown. But instead of only *saving* individual files, periodically you make a **commit**, which takes a multi-file snapshot of the entire project.
    -   Have you ever versioned a file [by adding your initials or the date](http://www.phdcomics.com/comics/archive.php?comicid=1531)? That is effectively a **commit**, albeit only for a single file: it is a version that is significant to you and that you might want to inspect or revert to later.
-   Push commits to GitHub periodically.
    -   This is like sharing a document with colleagues on DropBox or sending it out as an email attachment. It signals you're ready to make your work visible to others and invite comment or edits.

This is a moderate change to your normal, daily workflow. It feels weird at first, but quickly becomes second nature. FWIW, [STAT 545](http://stat545.com) students are required to submit all coursework via GitHub. This is a major topic in class and office hours for the first two weeks. Then we practically never discuss it again.

Commits, diffs, and tags
------------------------

The *commit* is one of the most fundamental concepts in Git, along with *repository*. A commit functions like a snapshot of all the files in the repo, at a specific moment. Under the hood, that is not exactly how Git implements things. Mental models don't have to be accurate in order to be useful, but in this case there's some value in aligning the two.

*this is really crying out for an example and/or diagrams*

Consider version A of a file and then version B, which comes from modifying version A. Assume that version A was part of a Git commit and version B was part of the next commit. The set of differences between A and B is called a *diff* and Git users contemplate diffs a lot. Diff inspection is how you re-explain to yourself how version A differs from version B. Diff inspection is not limited to adjacent commits. You can inspect the diffs between any two commits.

In fact, Git's notion of version B of your file is as an accumulation of diffs. At some earlier point, the file was created in the first place. That version of the file was part of a commit and, therefore, a diff. Git stores Version A of the file as the initial version, plus all the intervening diffs in the history that affect the file. And version B simply includes one more. We'll set these internal details aside now, but understanding the importance of these deltas will eventually make Git's operations less baffling.

So, it's easy to see how two snapshots differ, but what about the why?

Every time you make a commit you must also write a short *commit message*. Ideally, this conveys the *motivation* for the change. Remember, the diff will show the content. When you revisit a project after a break or need to digest recent changes made by a colleague, looking at the *history*, by reading commit messages and skimming through diffs, is an extremely efficient way to get back up to speed.

Every commit needs some sort of nickname, so you can identify it. Git does this automatically, assigning each commit what is called a *SHA*, a seemingly random string of 40 letters and numbers (it is not, in fact, random but is a checksum hash and is technically a SHA-1). Though you will be exposed to these, you don't have to handle them directly very often and, when you do, usually the first 7 characters suffice. You can also designate certain snapshots as special with a *tag*, which is a name of your choosing. In a software project, it is typical to tag a release with its version, e.g., "v1.0.3". For a manuscript or analytical project, you might tag the version submitted to a journal or transmitted to external collaborators.

Markdown is special
-------------------

This may seem unrelated to Git and R, but it's time to talk about Markdown. Markdown is a markup language, like HTML and LaTeX, but designed to be as lightweight as possible. The goal is still to separate form and content, but also to preserve human-readability, even at the cost of fancy features. Markdown is in wide use on sites like Wikipedia, WordPress, StackOverflow, and, yes, GitHub. Do not build this up into some heroic, LaTeX-level learning task, for it is not. If you can write an email, you can write Markdown.

Any file written in Markdown is rendered in an HTML-like way on GitHub. In particular, formatting and links "just work". This is the last piece we needed to seal my claim that merely pushing your project to GitHub gives it a web presence for zero extra work. If you make even a modest effort to embed a few explanatory Markdown files in your repo, you will get an automatically-updated project website for free.

Markdown is extra special for R users because of R Markdown, which is just Markdown that includes chunks of R code. Again, do not build this up into something you must clear your schedule to learn. If you can write email and a bit of R code, you can write R Markdown. The rmarkdown package converts R Markdown (`.Rmd` files) to Markdown (`.md` files), running the code and inserting the results, including figures, into the document. This is powered by another package, knitr, under the hood. This process is made very easy in RStudio, but is by no means limited to users of that application.

These R-derived Markdown files, if committed and pushed, then enjoy the usual privileged treatment on GitHub already described. The overall effect is that a directory that is an RStudio project and GitHub-synced Git repo can simultaneously be the code-heavy back end of a project and the outward-facing front end.

One last point about R Markdown more generally: the rmarkdown package can render `.Rmd` files to many more formats than Markdown. In addition to knitr, rmarkdown uses Pandoc and, optionally, LaTeX, to convert `.Rmd` to a wide array of output formats, including HTML, PDF, and Word (`.docx`). The Markdown must be created regardless. Sometimes it is all you need, such as on GitHub, and, in other contexts, it is just a necessary intermediate and may even be discarded.

Which files to commit
---------------------

The files in a project play different roles and arise in different ways. Let's have a few examples in mind for this discussion:

-   R markdown `.Rmd` --&gt; markdown `.md`
-   R markdown `.Rmd` --&gt; markdown `.md` --&gt; `.html` or `.pdf` or `.docx`
-   R script `.R` --&gt; results as `.csv` or `.rds` and figures `.png`
-   LaTeX `.tex` --&gt; WHAT GOES HERE NOW? --&gt; `.pdf`

The files at the far left are clearly source files. In the case of an R script, this is literally true, but it's morally true for R markdown and LaTeX files too. These are files that you directly create and edit "by hand".

The files at the far right are clearly derived and are often described as "targets". These files are programmatically generated from source files (and possibly other inputs). These files are the product and they have external value, often for communicating ideas and results.

The files in the middle are intermediates. Like targets, they are programmatically generated, but, unlike targets, no one necessarily cares about them. However, note that intermediate Markdown `.md` is an exception, since it is extremely useful on GitHub -- much more so than `.html`, `.pdf`, or `.docx` -- and is more like an additional target.

A critical issue for workflow happiness is figuring out how to manage the production and storage of source, intermediates, and targets with respect to Git. You can direct Git to ignore specific files or certain types of files, such as autosaves created by your editor. This reduces clutter in your project: Git will not pester you to commit changes to these files and they will not appear in the associated GitHub repository. A file that Git does not ignore is said to be *tracked*.

The only point on which there is consensus is that source files should absolutely be tracked. The status of intermediates and targets with respect to Git is much less clear cut.

Therefore, the main message for intermediates and targets is that you can pick a policy that works for you and adapt as your needs change. There is no right answer. I suggest erring on the side of committing everything at first.

What are the main considerations when deciding whether to track a derived file or file type?

*Is it immediately useful to someone?* If so, that is a reason to track it and push it to GitHub. There is a taboo against committing derived products, inherited from Git's software development roots. The reasoning is that compiled programs are platform-specific and, therefore, people are better served by getting current source from Git and compiling themselves. I think data analytic targets, like figures and rendered reports, are very different beasts and it's misguided to reflexively exclude them from version control. They are immediately useful, especially to consumers of a project (versus the makers). To the extent that a GitHub repo is meant for communication, there is no reason to burden every consumer with unnecessary friction. Most simply will not bother to clone the repo, install all the necessary dependencies, and remake the products. Make them readily available.

*Is it available elsewhere?* If so, then perhaps you don't need to track it and push it to GitHub. Many people who have a policy of not tracking derived products also have a system that makes these available elsewhere, such as on a separate website. There are ways to automate this via GitHub, but that is beyond the scope of this article and not recommended for your early days with Git and GitHub. Beware those who recommend the exclusion of derived products without offering any practical solution for making them available some other way.

*Is it huge or changing often? Is it a format that is of little use on GitHub?* These are all good reasons to not track a file with Git. They can make your repository bloated and slow down pushes and pulls. If a file is binary, such as a Word document or Excel spreadsheet, Git and Git clients will not be able to provide human-readable diffs. Neither will GitHub be able to directly display this file in the browser. Be aware, however, that Git/GitHub-friendliness is more complicated than "is it plain text?". GitHub has excellent support for non-code files, such as image formats (PNG, JPG, GIF, PSD, and SVG) and PDFs. And, while HTML is plain text, it is of little direct use on GitHub, because it is not rendered.

*Will diffs be useful to you?* Some derived files are simply too big or miserable to read casually, such as `.csv` files of processed results or `.html` derived from `.Rmd`. But they may still be worth tracking with Git, because the diffs are often modest and quite interesting. I have caught unexpected changes in analytical results and student-facing webpages this way. When you re-run an analysis with updated input data or after updating R packages, the diffs presented by Git help you quickly pinpoint the downstream consequences.

In summary, I recommend you default to including a file in your Git repository, unless there's a specific reason not to. But good reasons absolutely do exist.

Collaboration
-------------

Collaboration is probably the most compelling reason to manage a project with Git and GitHub. I have a broad definition of collaboration here, that includes hands-on participation by multiple people as well as a more asymmetric model, in which some people are active makers and others only read or review.

Consider two different models of collaboration on a document:

-   **Edit, save, attach.** In this workflow, everyone has one (or more!) copies of the document and they circulate via email attachment, accumulating initials and dates in the filename. Which one is "master"? Does this question even make sense anymore? How do different versions of the document relate to each other? If you want to see a version combining the best versions of each section, how would you reconcile the different copies into one? All of this usually gets sorted out by social contract, a fairly manual process, and at least one miserable person.

-   **Google Doc.** In this workflow, there is only one copy of the document and it lives in the cloud. Anyone can access the most recent version on demand. Anyone can edit or comment or propose a change and this is immediately available to everyone else. Anyone can see who's been editing the document and how and, if disaster strikes, can revert to a previous version. A great deal of ambiguity and annoying reconciliation work has been designed away.

Managing a project via Git/GitHub is much more like the Google Doc scenario and enjoys many of the same advantages. It is definitely more complicated than collaborating on a Google Doc, but also more powerful. How does collaboration work?

Git is a decentralized version control system, meaning each collaborator has their own complete copy of the repo and its history. Everyone can work offline and/or simultaneously. GitHub plays the role of another collaborator, but a very special one. By convention, everyone agrees that it keeps the master copy of the project. GitHub is the clearinghouse. The joke is that GitHub puts the "central" in decentralized version control. You pull regularly from GitHub, to receive and integrate changes made by your collaborators. You also push regularly to GitHub, to return the favor, and to maintain its status as the comprehensive, authoritative version of the project.

*These two points were written as comparisons with Google Docs, but now there are intervening paragraphs. Is it too disconnected?*

*Manage multiple files*. A Git repository is inherently multi-file and therefore well suited to projects comprised of many files, evolving in a coordinated fashion. Examples include a data analysis, a course website, a blog, an R package, or a book. If there is any way to proactively check or enforce their joint functionality, this is something you could verify manually prior to a commit or at certain milestones. In the case of a website, you might choose to rebuild the site prior to a commit. In the case of an R package, `R CMD check` is one of the easiest things to automate on GitHub.

*Diffs and time travel*. Google Docs are fantastic for simple collaborative work, when you don't need detailed access to the history. But the version control offered by Google Drive is very limited compared to Git. You can't compare versions at arbitrary points in time, temporarily checkout previous versions, or maintain two lines of development.

*Needs a segue, which depends on what happens above.*

Merge conflicts are the most frustrating thing about using Git and GitHub. You can avoid them if you only work alone, on one computer, but I've also said that collaboration is the best reason to use GitHub! So this problem must be confronted.

What is a merge conflict? Your first encounter will probably look like this: your collaborator makes a change to a file, commits it locally, and pushes to GitHub. Meanwhile you also make a different change to the same file and also commit locally. When you try to push your commit to GitHub, it will fail because there are commits on GitHub that you do not have. You must pull from GitHub. The good news is that quite often, this will "just work", i.e. the GitHub version and your version will merge cleanly. Git is quite clever at reconciliation and changes to different files or distinct parts of the same file will merge.

But sometimes it's not clear how to reconcile your changes with the new ones from GitHub and you get a *merge conflict*. You must inspect the locations of conflict, where the two competing versions will have been left for you, and reconcile them. Then, and only then, will you be able to move forward and push a version integrating your recent changes to GitHub.

The best way to deal with merge conflicts is to avoid them altogether. This is another reason for all parties to commit, pull, and push often. Small changes, being integrated frequently, are easy for Git to merge, usually without conflict. The difficulty of merging (by Git or by you) is proportional to the evolutionary distance between two lines of work. So keep it small with lots of small commits and regular syncing with GitHub.

GitHub as course management system
----------------------------------

*adapt from here: <http://happygitwithr.com/classroom-overview.html>*

*Want to convey utility for managing the course materials/website, discussion board via issues, student repositories for coursework.*

R specific stuff
----------------

*Much of this appears elsewhere in some form. Perhaps I should find a home for what's not covered and kill this section?*

-   The active R package development community on GitHub. The read-only mirrors of R source and all of CRAN. Coupled with GitHub search features, you can answer alot of your own questions this way.
-   Specific workflows for R and Rmd destined to GitHub. `github_document`!!! `keep_md = TRUE`!!!
-   Git- and GitHub-related features of the [RStudio IDE](https://www.rstudio.com/products/rstudio-desktop/).

Special features of GitHub
--------------------------

*at this point, just fodder mined from various locations in Happy Git*

-   **Pull requests.** Git allows a project to have multiple, independent branches of development, with the notion that some should eventually be merged back into the main development branch. These are technical Git terms but hopefully also make sense on their own. A pull request is a formal proposal that says: "Here are some changes I would like to make." It might be linked to a specific issue: "Related to \#14." or "Fixes \#56". GitHub facilitates and preserves the discussion of the proposal, holistically and line-by-line.

**Be a keener!** If you care deeply about someone else's project, such as an R package you use heavily, you can track its development on GitHub. You can watch the repository to get notified of major activity. You can fork it to keep your own copy. You can modify your fork to add features or fix bugs and send them back to the owner as a proposed change.

### GitHub as web presence

Simply having a project on GitHub gives it a web presence.

If someone needs to see your work or if you want them to try out your code, they can easily get it from GitHub. If they use Git, they can clone or fork your repository. If they don't use Git, they can still browse your project on GitHub like a normal website and even grab everything by downloading a zip archive.

There are many things you can do a "working" repository to make it double as a project website.

-   [Make a GitHub repo browsable](http://happygitwithr.com/repo-browsability.html)

If you want a more proper website, GitHub, rmarkdown, and, especially, the combination provide several options:

-   <https://github.com/blog/2289-publishing-with-github-pages-now-as-easy-as-1-2-3>
-   <https://help.github.com/categories/github-pages-basics/>
-   <http://rmarkdown.rstudio.com/rmarkdown_websites.html>
-   <https://bookdown.org/yihui/bookdown/>
-   <https://bookdown.org/yihui/blogdown/>
-   <https://hadley.github.io/pkgdown/>

Random things lying around
--------------------------

Does creation and presence in GitHub repo make the project more readable and navigable? If so DO IT.

need to add a ton of links, citations

make some bespoke examples or diagrams?

Doing = documenting = sharing

<https://help.github.com/categories/working-with-non-code-files/>

<https://help.github.com/articles/rendering-and-diffing-images/>

make statistical thought and implementation available

Transparency about process and product is increasingly important in science. The SOMETHING for reproducibility is well accepted. A more underappreciated benefit is democratization of our field, as this affords a much broader audience a clear view of how scientists and programmers work.

Who can do what?

A public repository is readable by the world. The owner can grant higher levels of permission to others, such as the ability to push commits.

A private repository is invisible to the world. The owner can grant read, write (push), or admin access to others.

There is also a formal notion of an organization, which can be useful for managing repository permissions for entire teams of people.

why sharing intermediate md is better than html (not readable) or pdf (merge conflicts). markdown is the magical intersection of git-friendly (plain text) and human-friendly (becasue GitHub renders it nicely)

possible github explainer <https://www.wired.com/2015/03/github-conquered-google-microsoft-everyone-else/>

<http://stackoverflow.com/questions/2712421/r-and-version-control-for-the-solo-data-analyst>

my tips around md are the large concept of "make things navigable/readable" of GitHub, particularized to R code

<https://www.onshape.com/cad-blog/how-google-solved-the-version-control-problem>
