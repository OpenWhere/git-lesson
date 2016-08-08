# Git

# Agenda
+ What is Git?
+ How we use Git
+ Hands-on Training

# What is Git?
Git is a distributed version control system invented by Linus Torvolds (who many
of you many already know as the inventor of Linux) because other version control
systems were not up to the task of coordinating a large project from many
contributors.

## Changes, not Code
Unlike other version control systems you may be familiar with, Git tracks
CHANGES instead of code.

Every commit to a git repository is a selection of changes, not code.

The codebase is the SUM of ALL CHANGES on a particular branch.

This also makes it very easy to see what the code looked like at any previous
point in time. You just "checkout" the code from a specific commit.

A `git checkout <hash>` says "show me the codebase at the commit represented by
this <hash>."

## Distributed?
Git is a DVCS, which means that everybody has the complete history of the
codebase. Unlike Subversion and CVS (where users will "check out" and "check in"
their code like a book from a library), in Git, everybody has the complete
history (and therefore, all the code), and we use "pull requests" to sync our
repositories with the company's repository.

This allows multiple people to work on the same file at the same time without
any issues. If two people change the same line of code, a human will have to
resolve the "merge conflict," which we will practice doing later.

# How We Use Git

## Gitflow
You may hear the term GitFlow thrown around from time to time. This is simply a
branching strategy that we use to introduce the smallest possible amount of
entropy into the codebase.

Allow me to explain!

## Upstream vs. Forks vs. Origin vs. Local
In Git, when you want to work on a project, you will CLONE the repository.
Remember that Git is a DVCS, so while "check out" (like a library book) might
make sense for a centralized version control system, it's inadequate to describe
what you're doing in a D(ISTRIBUTED) VCS, which is: Give me the entire history of
the whole project.

### Forks
A "Fork" refers to a clone of a repository that lives in the cloud and is
associated with your user.

Forks are an important part of our GitFlow Pull Request setup, because they let
us know from whom a pull request is coming.

**TEACHABLE MOMENT**
Right now, everybody go to http://github.com/OpenWhere/git-lesson and press the
FORK button in the upper right-hand corner.

What you've just done is told Github:
"I want you to create a copy of OpenWhere's git-lesson repository on my behalf"

So now, you've got your own copy of the repository, to which you can make any
changes you want.

But you don't want to write code in the browser (I'm looking at you, Derek), so
we're going to clone the code to our local machines now.

### Origin
Click the "Clone or Download" button in Github, and copy the URL.

Now, on your computer (I use the command line), you will want to `git clone` and
paste your URL.

Git clones the files to your computer from Github, and now you've got a local
copy of the code!

Your FORK is called ORIGIN. This is the default name that git gives to the repo
from which the codebase was cloned.

### Upstream
In order for us to achieve one-way data flow, we'll also need to reference our
UPSTREAM repository.  UPSTREAM is a name we have decided on for company
repositories from which all the developers fork.

We don't get this reference for free, however, so we're going to add it
manually:

```
git remote add upstream <upstream url>
```

Now you have a remote repo ORIGIN, which is your fork, and UPSTREAM, which is
BlackSky's repo

## One-way Data Flow

[DRAW THE GREAT CIRCLE OF GIT ON THE WHITEBOARD]


