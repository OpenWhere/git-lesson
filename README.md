# BlackSky Git Resources
This repository contains a list of resources for learning (and teaching) how we
use Git at BlackSky. The resources are as follows:

+ `lesson_plan.md` - Speaking notes for a crash course in Git
+ `slides.md` - A simple set of slides to accompany the lesson plan above
+ `index.html` - The file you open in the browser to view the slides

## Self Study
If you are interested in teaching yourself git, the [Git Immersion](http://gitimmersion.com/)
tutorial is a very good one that has been kicking around for over half a decade
now.

# Updating Slides
If you want to update the slides, you can compile them with [biggie](https://github.com/tmcw/biggie).

First, install biggie:

```
npm install -g biggie
```

Second, change slide content in `slides.md`

Finally, recompile the slides:

```
biggie slides.md --style ./resources/big_styles.css > index.html
```
