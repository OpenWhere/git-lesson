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

## Distributed
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
A "Fork" is a clone of a repository that lives in the cloud.

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

### Clone
Click the "Clone or Download" button in Github, and copy the URL.

Now, on your computer (I use the command line), you will want to `git clone` and
paste your URL.

Git clones the files to your computer from Github, and now you've got a local
copy of the code!

### Origin
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

Data should only ever flow in one direction. This minimizes how out-of-sync your
local repository becomes with the upstream repository, and ensures that you're
always using the latest code (instead of accidentally introducing unrelated
changes into your codebase).

```
git fetch upstream              # Get the latest code from upstream
git checkout upstream/develop   # Set my local environment to reflect what's on the develop branch of "upstream"
git branch my-new-branch        # Create a new LOCAL branch named my-new-branch
git checkout my-new-branch      # Set my working branch (and local environment) to my-new-branch
```

Right now, `my-new-branch` matches what's in upstream/develop; that means your
local codebase now matches exactly what's already checked in to our upstream
repository, which is the "official" repository for the codebase.

### Branches
You may have noticed that we've created a branch. A "branch" in Git is simply a
lightweight movable pointer to a commit that remembers the history of previous
commits.  We'll come back to this shortly.

### Commits
A "commit" is a collection of changes that has been persisted to a branch. Best
practice states that your commits should be atomic: you want to make commits
that are generally smaller and that encompass only one irreducible feature, fix,
or improvement.

A single commit may not be sufficient to address a new feature or bug. But by
spreading your fixes or features across multiple commits, it becomes very easy
to troubleshoot specific issues you have, or to roll back only a small part of
the code in the event of an error.

### Pull Requests
Every commit you make gets added to the history of your current working branch:

[ DRAW A DAG ON THE WHITEBOARD ]

When you have created all the commits necessary to fulfill the requirements of
your feature or bugfix, you will submit a PULL REQUEST.

A pull request is a way to merge your branch (with your bugfix or feature) into
our upstream repository. It has certain advantages over merging code by hand,
including:

### Code Reviews
+ The ability to tell you if there are any merge conflicts before the code is
  merged
+ The ability for others to view your changes and comment in-line (code reviews)
  BEFORE the code is merged
+ The ability to control who has the ability to merge code into upstream

All of these features lead to fewer errors in the code and more information
sharing across the team.

FOR EXAMPLE, thanks to code reviews, I learned Python in record time (because I
had more experienced people explaining to me things like list comprehensions).

# Hands-on Training
So far in the tutorial, we have covered the following things:

+ Forking a repository
+ Cloning a repository
+ Creating a new branch with the latest code

Now, we're going to cover the following:

+ Committing code
+ Submitting pull requests
+ Participating in pull requests
+ Resolving merge conflicts

## Committing Code

1. Navigate to your local repository
2. Make sure you're on a new branch (my-branch) with the latest from upstream
3. Open `index.html` or `resources/generator.js`
4. Create an enhancement to the project (add a noun, adjective, or some other feature)
5. `git status`
6. `git diff`
7. `git add -p`
8. `git diff --cached`
9. `git commit`

There is lot of literature online for writing [great commit messages](http://chris.beams.io/posts/git-commit/)

## Submitting Pull Requests

1. `git push origin my-branch`
2. Navigate to upstream repo on Github
3. Follow on-screen prompts to create pull request

## Reviewing Code

1. Submitting Comments
2. Resolving Merge conflicts

# Supplemental Advanced topics
Git's branching model is represented by Directed Acyclic Graphs (DAGs), which is
a finite directed graph with no directed cycles. Basically, it is impossible to
go back in time.

[ EXPLAIN VIA WHITEBOARD BRANCHING AND MERGING ]
