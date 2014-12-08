---
layout: post
title: "Hello World!"
date: 2014-12-08 17:20:59 +0100
comments: true
categories: 
---

This is the obligatory "Hello World!" post 

To get here and create your own blog using [octopress], follow the
instructions below:

* Install ruby, as explained on the
  [here](http://octopress.org/docs/setup/)
 * I've used Ruby 2.1.5p273 (2014-11-13 revision 48405) \[x64-mingw32\]
   (``ruby --version``)
* Configure your blog. See
  [here](http://octopress.org/docs/configuring/)
* Install octopress: ````rake install````
* Start the server with ````rake preview````. You should see a basic
  template (CSS) with your blog name, the author, etcetera
* Create your first post. 

 ````cmd
rake new_post["Hello World!"]
````

* Refresh the browser and see the new post appear
* Edit the .markdown file in "source\\_posts" using a markup editor
* Execute ````rake preview```` to see your first post (this)
* Execute ````rake setup_github_pages```` for every computer you want to
  publish from
* Execute ````rake generate && rake deploy````. After a few minutes, you
  should go to
  <username>.github.io to find your new blog in there

* Happy blogging!

