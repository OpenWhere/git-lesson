# BlackSky Git Resources
This repository contains a list of resources for learning (and teaching) how we
use Git at BlackSky. The resources are as follows:

+ `crash_course.md` - Speaking notes for a crash course in Git
+ `slides.md` - A simple set of slides to accompany the lesson plan above
+ `crash_course.html` - The file you open in the browser to view the slides
+ `index.html` - The playground in which we will practice our git-fu
  - `resources/generator.js` - The Javascript file to accompany our playground
+ `great_commit_messages.html` - Another set of slides + speaking notes on the
  importance of writing great commit messages.

## Self Study
If you are interested in **learning git**, the [Git Immersion](http://gitimmersion.com/)
tutorial is a very good one that has been kicking around for over half a decade
now.

If you are interested in learning about why it is important to write **good
commit messages**, start with [this post](http://chris.beams.io/posts/git-commit/).
If you need to read the same thing from different people to believe something,
maybe [this post](http://alistapart.com/article/the-art-of-the-commit) will
convince you of the importance of writing good commit messages. :)

# Git-Sensei's Protips
Add the following to your `~/.gitconfig` for an amazing command-line git experience:

```
[color]
    ui = auto
[alias]
    co = checkout
    st = status
    diffs = diff --stat
    diffc = diff --cached
    hist = log --pretty=format:\"%h %ad | %s%d [%an]\" --graph --date=short
    newb = "!git fetch upstream && git checkout upstream/develop && git co -b $2"
    cleanup = "!git branch -r --merged | grep origin | grep -v '>' | grep -v master | xargs -L1 | cut -d\"/\" -f2- | xargs git push origin --delete"
[push]
    default = simple
```

Let's talk about each option in detail:

+ Color: Colors your diffs green/red when lines are added/removed
+ Aliases:
  - `co`: `git co` to checkout instead of `git checkout`
  - `st`: `git st` instead of `git status`
  - `diffs`: Shows some information about the changes you haven't yet committed
  ```
  $ git diffs
   package.json           |  1 +
   webpack.config.js      | 13 ++++++++++++-
   webpack.prod.config.js | 17 ++++++++++++++---
   3 files changed, 27 insertions(+), 4 deletions(-)
  ```
  - 'diffc': Same as `git diff --cached`, which shows files you've ADDED to a commit (but not yet committed)
  - `hist`: Pretty-print your git history!
  - `newb`: Automates the "new branch" part of the workflow; fetches the latest from upstream and creates a new branch from it
  - `cleanup`: Careful with this one! This will delete all the merged branches on your origin (merged may not mean the pull-request has been accepted!)
+ Push: States that `push` will only push the working branch to a target repo (rather than to all repos with a branch of the same name).


# Updating Slides
If you find you have become the person in charge of the Git Crash Course
contained herein, you may be interested in updating the slides. The crash course
slides are written in markdown, and you can compile them to HTML with [biggie](https://github.com/tmcw/biggie).

1. Install biggie:
```
npm install -g biggie
```
2. Change slide content in `slides.md`
3. Recompile the slides:
```
biggie slides.md --style ./resources/big_styles.css > crash_course.html
```

The slides for `great_commit_messages` were painstaking crafted by hand in raw
HTML, so you'll have to forego Markup when editing those.
