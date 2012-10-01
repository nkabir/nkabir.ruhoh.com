---
title: Jenkins Installation
date: '2012-10-01'
description: Setting up Jenkins with security
categories: sysadmin
tags:
    - precise

---

Jenkins is a service that monitors the software build process in a controlled clean-room environment. 

## Installation

Jenkins is available as a BlackBox package `bbjenkins`. Install with 

    $ sudo apt-get install bbjenkins

Once installed, change the default port to `8888` from `8080`. This setting is configured in `/etc/default/jenkins`. Restart the service with

    $ sudo service jenkins restart

Then point your browser to `http://{hostname}:8888`

<img class="diagram" src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/jenkins-installation/jenkins-001.png" />

## Plugins

Jenkins has a large collection of plugins to extend its functionality. Since we'll be managing both Java and Python projects, we'll need _at least_ the following set of plugins activated:

* javadoc
* Analysis Collector Plugin
* artifactory plugin
* Crap4j
* Dependency Graph Viewer Plugin
* Disk Usage Plugin
* Maven Integration Plugin
* Static Code Analysis Plugin
* Warnings Plugin
* Violations Plugin
* EnvInject Plugin
* SLOCCount Plugin
* Sonar Plugin
* ShiningPanda Plugin
* xUnit Plugin
* PMD Plugin
* FindBugs Plugin
* Mercurial Plugin
* Cobertura Plugin

Click on the _Manage Plugins_ link.

<img class="diagram" src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/jenkins-installation/jenkins-002.png" />

Next, choose the _Available_ tab and use `ctrl-F` to find plugins matching the ones in the list above.

<img class="diagram" src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/jenkins-installation/jenkins-003.png" />

Once you've selected all the plugins, press _Download now and install after restart_.

<img class="diagram" src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/jenkins-installation/jenkins-004.png" />

Finally, check the box _Restart Jenkins when installation is complete and no jobs are running_.

## Security

Jenkins supports integration with LDAP along with fine-grained security. To enable security, check the box highlighted below:

<img class="diagram" src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/jenkins-installation/jenkins-005.png" />

Then enter the details for your LDAP server. If you enter a _root DN_, all subsequent entries should be relative DNs rather than full DNs (e.g. `ou=users` instead of `ou=users,dc=example,dc=com`).

<img class="diagram" src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/jenkins-installation/jenkins-006.png" />

Finally, select _Matrix-based security_ and set the appropriate permissions. See example (right click and _view image_ to get a closer look).

<img class="diagram" src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/jenkins-installation/jenkins-security-001.png" />

<div class="alert alert-success">
Jenkins is ready to be configured for Python and Java projects!
</div>
