---
title: OpenGrok Search Engine
date: '2012-09-29'
description: Source code search engine
categories: sysadmin
tags:
    - java
    - search

---

OpenGrok is fast code search engine that was open source by Sun Microsystems. It was originally used to index the [OpenSolaris operating system source base](http://src.opensolaris.org/source/) but it works wonderfully on any source code including ours. It helps you search, cross-reference and navigate your source tree. It can understand various program file formats and
version control histories.

<blockquote><em>If people can not easily understand how a piece of software source code works, or if people cannot easily and accurately search through it, then it is as bad as any proprietary software or data formats which are difficult for general public to understand.
<br/><br/>
OpenGrok in that sense is a true enabler for source code that is open source. It lets people easily and quickly find the source code, look at it, understand the history and changes made to the source. It makes a developers life easy.</em>
<small>OpenGrok Team</small>
</blockquote>

## Installation

`bbopengrok` is available as a BlackBox package. To install

    $ sudo apt-get install bbopengrok

<div class="alert alert-info">
Note you'll need an LDAP server with an entry for a Tomcat Manager (<code>manager-gui</code> group).
</div>

The installer will query for the LDAP server base dn, the home folder for Tomcat6 (typically `/opt/bbtomcat6/current`), and the home folder for the indexed source code (typically `/opt/src/og`). This entire process is managed by `bbtomca6` so it's imperative that all folders are owned by the `bbtomca6` user.

Once installation is complete, test it with a sample project.

    $ cd /opt/src/og
    $ sudo -u bbtomca6 hg clone https://{some project}/{user}/{name}

Fill in any project for which you have access. This ensures there's something to index. Next, run the crontab entry to ensure your environment is configured properly. The cron entry runs the following script:

<script src="https://bitbucket.org/nkabir/blackbox-12.04/src/4083e0e0c780/bbopengrok/generate-opengrok.sh.j2?embed=t"></script>

The template entries (e.g. `source_root`) are filled in during installation. After executing the crontab entry, uncomment it so it runs regularly.

Finally, start `bbtomcat6`

    $ sudo service bbtomcat6 start

And point your browser to `http://{your host}:8080/source`. You should see the main screen:

<img class="diagram" src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/development/opengrok-search-engine/opengrok-001.png" />

