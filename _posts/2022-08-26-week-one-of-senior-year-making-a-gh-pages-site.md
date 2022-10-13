---
title: "Setting Up This Blog and My Best Coding Experience"
date: '2022-08-26'
categories: [weekly blog]
tags: [blog,technical]
published: true
---

# Setting up the blog

## What blog site to use

When I was instructed to setup a blog for one of my classes, I already knew what I was going to use, which is Jekyll, an open source static site generator that works with github pages. I then looked for a nice theme that could supply documentation and software release needs, had dark mode, and was easily modifiable. That is how I found the Chirpy theme I am using now. This site, long term, is going to be used for documenting software I publicly release and to show off my portfolio.  

## Jekyll + Chirpy theme

This blog is built with [jekyll-chirpy-theme](https://github.com/cotes2020/jekyll-theme-chirpy). When I was building the site, I ran into several issues. so for anyone wanting to use this theme themselves, here is a step by step guide to deploying the Jekyll + Chirpy theme. 

1) Go to the [chirpy starter]() repository and generate your own repository.

2) Clone the repository onto your own computer

3) If you do not have `Ruby`, `RubyGems`, `Jekyll`, and `Bundler` installed, visit the [Jekyll Docs](https://jekyllrb.com/docs/installation/) site now to install them, as they are required for the next steps.

4) Open the downloaded repository root in a terminal and run:
```console
$ bundle install
``` 
5) As of 08/26/22, this theme did not work at this stage of deployment for me. Some tutorials I have seen did not need to do this step, but I did. If you are hosting this site on github pages, I recommend you run the command below in the terminal:
```console
$ bundle lock --add-platform x86_64-linux
$ bundle
```
6) Commit and push your changes and your site should be up at [gh-username].github.com

7) Unique changes can be made in the `./_config.yaml` file

This covers the basic setup of the site. For additional information, follow the instructions that comes with the [theme](https://jekyllrb.com/docs/installation/) or watch [Techno Tim](https://www.youtube.com/watch?v=F8iOU1ci19Q&t=614s) set the site up for himself.

I also recommend [jekyll-compose](https://github.com/jekyll/jekyll-compose) as it simplifies creating new jekyll posts. Follow the instructions at the link to install it on your site.

# My Best Programming Experiences

I have developed a handful of tools for my own use throughout the years. For modding minecraft bedrock, I built a packaging tool for mod files that would construct meta data for the mod from the files, package the mod, and install it into minecraft bedrock. This is one of my favorites tool I have made as it was the first I utilized many of the concepts and practices I was taught in college. Building the tool itself was a great experience that taught me how to utilize a number of different tools to build an application.


