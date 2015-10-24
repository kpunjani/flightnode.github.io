---
layout: page
title: Git Tips and Tutorials
comments: false
category: programming
tags: [toolkit]
sharing: true
---

## Tutorials

Git is a fabulous tool for source control management. While incredibly powerful, 
it can be a little daunting to learn at first. The following tutorials will
help. They are organized from simplest to more advanced.

* [tryGit](https://try.github.io/levels/1/challenges/1), an interactive tutorial
* [Learn Git Branching](http://pcottle.github.io/learnGitBranching/), an interactive tutorial
* [GitFlow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow), a very 
  good read on the basic workflow / process used for FlightNode development
* [Forking Workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/forking-workflow),
  in fact we using the Forking Workflow to facilitate collaboration, but with the
  *GitFlow* branching structure at the core.
  * In your local clones, create a new *remote* called *upstream**, pointing to the
    main repository: `git remote add upstream https://github.com/FlightNode/FlightNode.xyz`
  * When you want to get the latest code from the shared repository, you'll now
    be able to use `git pull upstream <somebranch>`.
* [Pull Request Tutorial]9https://github.com/yangsu/pull-request-tutorial), 
  with many nice screenshots and some advanced functionality, such as *squash*,
  *rebase*, and *cherry-pick*.
* [Pro Git](https://git-scm.com/book/en/v2), the entire book, is available online for free.

## Typical Workflow

Once you've created your forks on GitHub, and your clones on your workstation,
a typical day might look like this:

1. Open Git-bash and cd to a workspace: `cd /c/workspaces/FlightNode/FlightNode.Identity`
1. Planning on working on Issue #10 today... so create a feature branch:
   `git checkout -b feature/10`
1. You don't want to get out-of-date, or you may start running into major merge
   difficulties. Therefore: `git pull upstream develop`
1. Work on some code in your editor of choice.
1. Stage your code:
   1. New file: `git add full/path/to/new/file.cs`
   1. All existing files: `git add -u :/`
   1. All existing files in a particular directory: `git add -u :full/path`
1. Do some more work, stage some more work.
1. Commit your changes: `git commit -m "10 - brief description"` (for longer
   description, enter a brief description on first line, then hit enter to 
   type the longer description starting on the next line. Finish with ").
1. Done for the day? Want to backup your code? Push to your fork: 
   `git push origin feature/10`
1. Is the feature ready for other people to use? Then create a pull request
   in GitHub. In the pull request, add comments directly in the file
   if you want to explain something about your work. And invite others to 
   review your code.