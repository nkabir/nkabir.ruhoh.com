---
title: Portion Package Enhancement
date: '2012-09-28'
description: 

categories: sysadmin
tags:
    - apt
    - precise
    - blackbox

-type: draft

---

## Package Enhancement

I created portion to enhance the standard packaging process. The end goal is to create a packaging and deployment process that is easy to orchestrate with [CfEngine](http://www.cfengine.org). `portion` allows me to package software in a consistent way while continuing to leverage the standard Ubuntu repositories.

### Base Packages

The base packages for portion are bbsage and bbmint. These contain bash and python scripts respectively that are used to bootstrap all other packages. They are special packages--all other packages are built using the facilities included in these two packages.

### Bootstrapping

To bootstrap a new machine to use these facilities, execute the following command:

    $ curl -s get.fimero.org | sudo bash

This command updates `/etc/apt/sources.list` with the appropriate repositories and creates a backup of the original file in the same folder. [get.fimero.org](http://get.fimero.org) is a `bash` script.

## Sage

`sage` is a collection of bash functions that are used throughout the Portion ecosystem. The source code is [available](https://bitbucket.org/nkabir/sage) and the package is installed via 

    $ sudo apt-get update
    $ sudo apt-get install bbsage
