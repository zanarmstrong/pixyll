---
layout:     post
title:      Setting Up a Jekyll Blog
summary:    Quick how-to guide for setting up a blog using Jekyll and GitHub Pages
categories: how-to
---

This is my second time using a Jekyll template to set up a blog. It was fairly straightforward because I forked an existing template and because I'd done it once before. The templates each come with instructions, but I thought I'd write a bit about my process to supplement these. 

There is a growing list of [templates for Jekyll](http://jekyllthemes.org/) which seem to generally be open source under the MIT license, and forkable on Github. 

I wanted to keep it looking pretty simple and also responsive, so chose ["Pixyll"](http://jekyllthemes.org/themes/pixyll/). I probably could have spent a few hours exploring different designs, but wanted to get things up and running.  Instructions are in the [Pixyll GitHub repo](https://github.com/johnotander/pixyll).

To customize, it's important to change the title, email, author, description, and URL in the _config.yml file. I knew I wanted to point the site to a subdomain of my own domain name, so my URL is "blog.zanarmstrong.com".  Getting the blog to show up on my own site via GitHub Pages requires a few more steps: 

1. After you fork the Pixyll repo to your GitHub account, change the CNAME file to your blog. For me this was "blog.zanarmstrong.com"

2. After I've made some updates to the posts on the master branch, I pushed them to the gh-pages branch. That branch is the one that is used for the content in your own domain. [This article](https://help.github.com/articles/merging-branches/) documents how to do this from the MAC desktop client application for Github. 

3. In the DNS settings for your own domain, change the CNAME for your subdomain to point to Github.  For me this meant setting up a CNAME with a host of the subdomain "blog" that points to zanarmstrong.github.io. For somebody else it would be their own subdomain name as host pointing to [THEIR GITHUB USERNAME].github.io. It may take some time to "go live", depending on your domain host. If you go your domain, for me blog.zanarmstrong.com, and see a github branded error page like the one below then you've at least done this step right. You may need to still change your CNAME file, ensure that your gh-pages branch is up to date, or wait a little while as GitHub recommends. ![GitHub Error Page](https://lh5.googleusercontent.com/AQmi6sMh217ee9swPV2CM46cyCs0IRZakxjG5rVwX1Vx=w306-h207-p-no)

It's also important to change the name of the files in the posts folder, as well as their content, since the dates come from the title of the files. The "about.md" file also needs to be updated, and can be found in the main part of the repo. 

When I add a file, I'll need to either add it online in my GitHub repo or "push" the new content from the command line or my MAC Github client. I'll also need to merge the branches so that the gh-pages are up-to-date, as described [here](http://stackoverflow.com/questions/5807459/github-mirroring-gh-pages-to-master).

I hope these couple of tips help! I'm looking forward to writing more now that I have this blog set up.  