# GIT
---
For Derek:
![Memorizing Six Commands](./resources/memorizing-six.png)
---
## *Agenda*
+ What is Git?
+ How we use Git
+ Hands-on training
---
# *What is Git?*
---
Changes, not Code
---
Distributed
---
# *How we use Git*
---
GitFlow
---
+ Upstream
+ Origin
+ Local
---
Forks
---
https://github.com/OpenWhere/git-lesson
---
Clone
---
Create Local Repo:

```
$ git clone
https://github.com/<YOU>/git-lesson.git
```
---
Origin
---
Upstream
---
```
$ git remote add upstream
https://github.com/OpenWhere/git-lesson.git
```
---
One-way Data Flow
---
```
git fetch upstream
git checkout upstream/develop
git branch my-new-branch
git checkout my-new-branch
```
---
*Branches*

+ Lightweight Pointers
+ Collections of Commits
---
*Commits*

+ Code Changes
+ Atomic
---
*Pull Requests*

+ One (or more!) Commits
+ Whole feature/bugfix
+ Great for Code Reviews
---
*Code Reviews*

+ Improve code quality
+ Hone skills
+ BEFORE merge (important for CI)
---
# *Hands-on Training*
---
So far:

+ Forking
+ Cloning
+ Branching
---
Now:

+ Committing
+ Submitting
+ Pull Requests
+ Merge Conflicts
---
Committing
---
Submitting
---
Pull Requests
---
Merge Conflicts
---
# Questions?
---
# Thanks!
