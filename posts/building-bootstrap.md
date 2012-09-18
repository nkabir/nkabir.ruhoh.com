---
title: Building Bootstrap
date: '2012-09-18'
description: Working with Twitter's Bootstrap
categories: development
tags:
  - css
  - javascript
  - html

type: draft
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

If you haven't already, set up an account on [GitHub](http://www.github.com)

<script src="https://gist.github.com/2024366.js?file=dropbox.sh"></script>
