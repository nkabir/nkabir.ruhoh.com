---
title: Production Repository
date: '2012-09-29'
description: Installation and integration of production source code repository
categories: development
tags:
    - precise
    - mercurial

type: draft

---

We use [BitBucket](http://www.bitbucket.com) and [GitHub](http://www.github.com) to host our code. This works great for developers&mdash;but we also need to manage and deploy code from behind our firewall. [RhodeCode](http://rhodecode.org/) is an excellent package for managing Mercurial repositories. It also supports Git.

## Installation

`bbrhodecode` is a BlackBox package that installs RhodeCode into a [virtualenv](http://www.virtualenv.org/en/latest/index.html) sandbox along with required libraries.

To install,

    $ sudo apt-get install bbrhodecode

This will also install `bbpostgresql` to provide a database where RhodeCode stores its configuration and statistics. The installer will ask a series of questions. Most are self explanatory. The installer generate an Apache proxy file in `/var/tmp/rhodecode` that configures a virtual host that is used to forward requests from an Apache server to RhodeCode. This is helpful for enabling access through a firewall via SSL

    Apache alias to use for this service { hg.intranet.lan }: source.example.com
    Apache entry FQDN of host { host.intranet.lan } hg.example.com

Apache supports a primary server name (FQDN) as well as aliases (separated by spaces).

## Configuration

Once you've installed the `bbrhodecode` package, you'll need to configure LDAP. Log in with your administrator account.

<img class="diagram" src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/development/production-repository/rhodecode-001.png" />
<br/>
Under _Admin_, select _ldap_.

<img class="diagram" src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/development/production-repository/rhodecode-002.png" />

## LDAP Configuration

Depending on how the LDAP server is configured, you may not need to fill in all fields. 

### Connection Settings

* **Host**&mdash;_(ip address of LDAP server)_
* **Port**&mdash;_(typically 389 or 636)_
* **Account and Password**&mdash;_(if LDAP queries require authentication)_

### Search Settings

These setting depend on your LDAP schema.

* **Base DN**&mdash;_the base dn of your users_
* **LDAP Filter**&mdash;_constrain the query to specific objectClasses (not used)_
* **LDAP Search Scope**&mdash;_ensure this is set to_ `SUBTREE`

### Attribute Mappings

* **Login Attribute**&mdas;_typically set to_ `uid`
* **First Name Attribute**&mdash;_typically set to_ `givenName`
* **Last Name Attribute**&mdash;_typically set to surname_ `sn`
* **E-mail Attribute**&mdash;_typically set to_ `mail`

<img class="diagram" src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/development/production-repository/rhodecode-005.png" />

<div class="alert alert-success">
Your production code repository is ready!
</div>
