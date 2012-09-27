---
title: Building Bootstrap
date: '2012-09-18'
description: Working with Twitter's Bootstrap
categories: design
tags:
  - css
  - javascript
  - html

---

## Design Scaffolding

Twitter released [Bootstrap](http://twitter.github.com/bootstrap/) to share a collection of best practices for web templates. They provide a packaged selection of solid web technologies including the excellent Less library and make it available via Github. Since developers often have little or no web design experience, Bootstrap provides a great way to _bootstrap_ your front end.

We'll cover the process to get Bootstrap installed in our Ubuntu 12.04 environment.

### Prerequisites

You need to prepare your system to make Bootstrap.

    $ sudo apt-get install npm node-uglify
    $ sudo npm -g install jshint
    $ sudo npm -g install recess

### Fork Bootstrap

If you haven't already, set up an account on [GitHub](http://www.github.com). Then be sure to set up an [SSH key to manage your commits](https://help.github.com/articles/generating-ssh-keys). Finally, [fork the Bootstrap repository](https://help.github.com/articles/fork-a-repo) and clone it locally into

    $HOME/gitdev/com.github/$GITHUB_USER/bootstrap

Navigate to your new `bootstrap` folder and run `make`. This generates a `doc` folder that contains an `assets` folder where you'll find all the css, javascript and image files you'll need.
