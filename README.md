# BlackSky Git Resources
This repository contains a list of resources for learning (and teaching) how we
use Git at BlackSky. The resources are as follows:

+ `crash_course.md` - Speaking notes for a crash course in Git
+ `slides.md` - A simple set of slides to accompany the lesson plan above
+ `crash_course.html` - The file you open in the browser to view the slides
+ `index.html` - The playground in which we will practice our git-fu
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
