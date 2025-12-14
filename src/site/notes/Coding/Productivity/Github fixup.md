---
{"dg-publish":true,"permalink":"/coding/productivity/github-fixup/"}
---

----12/14/2025

So for this week for my learning experience are that I've learnt github fixup, .
It's a cool command useful when we want to amend the commit
in a chain. The usual way is to do the interactive rebase first then commit amend the original commit. which is good
but create a multi step process to amend the commit. To fasten the process we need a better way to change it.

- Using the github fixup we can amend any commit during the interactive rebase and change it's commit using a single command.
The staged changes goes directly through it. and

- How It'll handle this
  - Bring your changes in the staging area, bring only for a single commit
  - use the command git commit fixup #commitHash
  - this'll be handled by the creating a !fixup commit's will be new commit's on the top of the previous commit's
  - we can then sqaush the commit' on the top of the commit which we wanted to have that changes
  - we can also directly squash the changes by using a special command which I don't remember at the moment
  - Neovim will be a lot of helpful using the command's using
  - Sometime github hook's or husky will create a problem while creating a new !fixup commit's, since it'll not follow the
    the commit's rules you can chose to --no-verify using github fixup

- Overall the git fixup is very similar to git commit --amend when creating a amend commit instead of doing for the last
commit we can amend the 2'nd last or 4th last commit's withoug using the git interactive rebase and amending that commit


# Gib Absrob - Automation of Git Fixup

- Git absorb is similar to github fixup but a faster process or a kind of automation which will be helpful when there're
  multiple changes which are kind of small and there are multiple commit's to be amended so it's a kind of automation which
  will be helpful when creating changes in multiple commit's at a time, you can trust this automation at your 95% confidence
  my experience with the automation is been great so far, the only problem is it's create fixup commit's in hunks, which can
  be a overwhelming some of the time, sometime I've observed that 84 commit's has been created to amending that commit's

- We can trust the git absorb since it's a part of hg, facebook alternative to github, you can also check the github fixup
 on the the original git documentation page, which will similar tool's like this but it's is on the top so pretty decent


# Git worktree
- Git worktree is another tool not related to the git fixup, but really useful when you're working for multiple project's
some of the project which are hotfix, mustfix and need a special attention, instead of just stashing the current project changes
we can directly create a new worktree which will internally don't clone the repo but internally create a branch for the
the repo where you can enter any of the branches that exists on the original commit's

 - So you can virtually manage different branches and enter into any of the branch
 -

# Git Path ref/sec
- I've encounter the git path ref/sec since I've to amend on the release branches, so instead of doing the
- git push commit HEAD:ref/for/master we can push HEAD:ref/for/#Branch


-  I think there's a lot of the useful command's need to be learnt along the way, My way is to whenver I felt any
  inconvenience I've just ask any ai model's about how I can automate the repeatative thing's and make the process more
  ergonomic. So I have asked regarding this to the gpt and it'll open a new way to look upon the things and a lot of
  learning along the way. I wish I could learn more about the internal behaviour of the git how it manage across the d
  different distributed databases, Since I know It's a very powerful tool

# Playwright
- The next thing is playwright automation for right now I've to
