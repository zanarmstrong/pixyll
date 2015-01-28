---
layout:     post
title:      GitHub Pages Trick
summary:    Super useful trick for pushing to ghpages branch when you update master
categories: project
---

A few weeks ago I found this tip, and am posting now because I needed it again. I use Github Pages for this blog, as well as some other sites. It's great to be able to update directly from the command line. But, the live version is based on the gh-pages branch and not the master branch. So, typically when I push to master I also want to push to the live version. 

Stackoverflow had the answer [here](http://stackoverflow.com/questions/5807459/github-mirroring-gh-pages-to-master). See the second response. I've copied the contents here: 

> Add the following 2 lines to the [remote "origin"] section of .git/config:

> push = +refs/heads/master:refs/heads/gh-pages
> push = +refs/heads/master:refs/heads/master

> Every time you push it will automatically push master to gh-pages as well.

Fantastic!






