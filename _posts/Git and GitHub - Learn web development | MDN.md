> 本文由 [简悦 SimpRead](http://ksria.com/simpread/) 转码， 原文地址 [developer.mozilla.org](https://developer.mozilla.org/en-US/docs/Learn/Tools_and_testing/GitHub)

Git and GitHub
==============

All developers will use some kind of **version control system** (**VCS**), a tool to allow them to collaborate with other developers on a project without the danger of them overwriting each other's work, and roll back to previous versions of the code base if a problem is discovered later on. The most popular VCS (at least among web developers) is **Git**, along with **GitHub**, a site that provides hosting for your repositories and several tools for working with them. This module aims to teach you what you need to know about both of them.

[Overview](#overview)
---------------------

VCSes are essential for software development:

*   It is rare that you will work on a project completely on your own, and as soon as you start working with other people you start to run the risk of conflicting with each other's work — this is when both of you try to update the same piece of code at the same time. You need to have some kind of mechanism in place to manage the occurrences, and help avoid loss of work as a result.
*   When working on a project on your own or with others, you'll want to be able to back up the code in a central place, so it is not lost if your computer breaks.
*   You will also want to be able to roll back to earlier versions if a problem is later discovered. You might have started doing this in your own work by creating different versions of the same file, e.g. `myCode.js`, `myCode_v2.js`, `myCode_v3.js`, `myCode_final.js`, `myCode_really_really_final.js`, etc., but this is really error-prone and unreliable.
*   Different team members will commonly want to create their own separate versions of the code (called **branches** in Git), work on a new feature in that version, and then get it merged in a controlled manner (in GitHub we use **pull requests**) with the master version when they are done with it.

VCSes provide tools to meet the above needs. [Git](https://git-scm.com/) is an example of a VCS, and [GitHub](https://github.com/) is a web site + infrastructure that provides a Git server plus a number of really useful tools for working with git repositories individually or in teams, such as reporting issues with the code, reviewing tools, project management features such as assigning tasks and task statuses, and more.

**Note:** Git is actually a _distributed_ version control system, meaning that a complete copy of the repository containing the codebase is made on your computer (and everyone else's). You make changes to your own copy and then push those changes back up to the server, where an administrator will decide whether to merge your changes with the master copy.

#### Looking to become a front-end web developer?

We have put together a course that includes all the essential information you need to work towards your goal.

[**Get started**](/en-US/docs/Learn/Front-end_web_developer)

[Prerequisites](#prerequisites)
-------------------------------

To use Git and GitHub, you need:

*   A desktop computer with Git installed on it (see the [Git downloads page](https://git-scm.com/downloads)).
*   A tool to use Git. Depending on how you like to work, you could use a [Git GUI client](https://git-scm.com/downloads/guis/) (we'd recommend GitHub Desktop, SourceTree or Git Kraken) or just stick to using a terminal window. In fact, it is probably useful for you to get to know at least the basics of git terminal commands, even if you intend to use a GUI.
*   A [GitHub account](https://github.com/join). If you haven't already got one, sign up now using the provided link.

In terms of prerequisite knowledge, you don't need to know anything about web development, Git/GitHub, or VCSes to start this module. However, it is recommended that you know some coding so that you have reasonable computer literacy, and some code to store in your repositories!

It is also preferable that you have some basic terminal knowledge, so for example moving between directories, creating files, and modifying the system `PATH`.

**Note:** GitHub is not the only site/toolset you can use with Git. There are other alternatives such as [GitLab](https://about.gitlab.com/) that you could try, and you could also try setting your own Git server up and using it instead of GitHub. We've only stuck with GitHub in this course to provide a single way that works.

[Guides](#guides)
-----------------

Note that the links below take you to resources on external sites. Eventually, we are aiming to have our own dedicated Git/GitHub course, but for now, these will help you get to grips with the subject at hand.

[Hello, World (from GitHub)](https://docs.github.com/en/get-started/quickstart/hello-world)

This is a good place to start — this practical guide gets you to jump right into using GitHub, learning the basics of Git such as creating repositories and branches, making commits, and opening and merging pull requests.

[Git Handbook (from GitHub)](https://docs.github.com/en/get-started/using-git/about-git)

This Git Handbook goes into a little more depth, explaining what a VCS is, what a repository is, how the basic GitHub model works, Git commands and examples, and more.

[Forking Projects (from GitHub)](https://docs.github.com/en/get-started/quickstart/contributing-to-projects)

Forking projects is essential when you want to contribute to someone else's code. This guide explains how.

[About Pull Requests (from GitHub)](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/about-pull-requests)

A useful guide to managing pull requests, the way that your suggested code changes are delivered to people's repositories for consideration.

[Mastering issues (from GitHub)](https://docs.github.com/en/issues/tracking-your-work-with-issues/about-issues)

Issues are like a forum for your GitHub project, where people can ask questions and report problems, and you can manage updates (for example assigning people to fix issues, clarifying the issue, letting people know things are fixed). This article tells you what you need to know about issues.

**Note:** There is **a lot more** that you can do with Git and GitHub, but we feel that the above represents the minimum you need to know to start using Git effectively. As you get deeper into Git, you'll start to realize that it is easy to go wrong when you start using more complicated commands. Don't worry, even professional web developers find Git confusing sometimes, and often solve problems by searching for solutions on the web, or consulting sites like [Flight rules for Git](https://github.com/k88hudson/git-flight-rules) and [Dangit, git!](https://dangitgit.com/)

[See also](#see_also)
---------------------

*   [Understanding the GitHub flow](https://docs.github.com/en/get-started/quickstart/github-flow)
*   [Git command list](https://git-scm.com/docs)
*   [Mastering markdown](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax) (the text format you write in on PR, issue comments, and `.md` files).
*   [Getting Started with GitHub Pages](https://docs.github.com/en/pages/quickstart) (how to publish demos and websites on GitHub).
*   [Learn Git branching](https://learngitbranching.js.org/)
*   [Flight rules for Git](https://github.com/k88hudson/git-flight-rules) (a very useful compendium of ways to achieve specific things in Git, including how to correct things when you went wrong).
*   [Dangit, git!](https://dangitgit.com/) (another useful compendium, specifically of ways to correct things when you went wrong).

### Found a problem with this page?

*   [Edit on **GitHub**](https://github.com/mdn/content/edit/main/files/en-us/learn/tools_and_testing/github/index.md "You're going to need to sign in to GitHub first (Opens in a new tab)")
*   [Source on **GitHub**](https://github.com/mdn/content/blob/main/files/en-us/learn/tools_and_testing/github/index.md?plain=1 "Folder: en-us/learn/tools_and_testing/github (Opens in a new tab)")
*   [Report a problem with this content on **GitHub**](https://github.com/mdn/content/issues/new?template=page-report.yml&mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FLearn%2FTools_and_testing%2FGitHub&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EPage+report+details%3C%2Fsummary%3E%0A%0A*+Folder%3A+%60en-us%2Flearn%2Ftools_and_testing%2Fgithub%60%0A*+MDN+URL%3A+https%3A%2F%2Fdeveloper.mozilla.org%2Fen-US%2Fdocs%2FLearn%2FTools_and_testing%2FGitHub%0A*+GitHub+URL%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fblob%2Fmain%2Ffiles%2Fen-us%2Flearn%2Ftools_and_testing%2Fgithub%2Findex.md%0A*+Last+commit%3A+https%3A%2F%2Fgithub.com%2Fmdn%2Fcontent%2Fcommit%2F904cdf09c7e328b7a15a6a4db6bc6bd31f969cce%0A*+Document+last+modified%3A+2022-09-09T05%3A00%3A53.000Z%0A%0A%3C%2Fdetails%3E "This will take you to GitHub to file a new issue")
*   Want to fix the problem yourself? See [our Contribution guide](https://github.com/mdn/content/blob/main/README.md).

**Last modified:** Sep 9, 2022, [by MDN contributors](/en-US/docs/Learn/Tools_and_testing/GitHub/contributors.txt)