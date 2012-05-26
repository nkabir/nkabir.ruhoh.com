---

title: Blackbox Sage Library
date: '2012-05-26'
description: The bash library for the Blackbox stack.
categories: sysadmin
tags:
    - ubuntu
    - bash
    - precise
    - blackbox

layout: post

---

## Introduction

Sage is a collection of `bash` utilities that are used throughout the Blackbox technology stack. Sage is packaged as `bbsage`. It is the lowest level (base) package for Blackbox.

The source code for `sage` is available at [http://bitbucket.org/autonomy/sage](http://bitbucket.org/autonomy/sage).

The packaging source is available at 
[http://bitbucket.org/autonomy/bbpackage](http://bitbucket.org/autonomy/bbpackage).

## Installation

To get started, you'll need to update your `sources.list`. Start with a fresh Ubuntu 12.04 LTS virtual machine and replace its `/etc/apt/sources.list` with the one located at [https://gist.github.com/2703110](https://gist.github.com/2703110).

	$ sudo apt-get update
	$ sudo apt-get install bbsage

This installs `sage` into `/opt/bbsage/` where the current version is always symlinked to `/opt/bbsage/current`.

## Sage Tour

`sage` provides numerous commonly used `bash` functions. For example:

<dl>
<dt><code>defined()</code></dt>
<dd>Returns <code>true</code> if the argument has been defined.</dd>
<dt><code>has_value()</code></dt>
<dd>Returns <code>true</code> if the argument has been defined and has a value.</dd>
<dt><code>directory_exists()</code></dt>
<dd>Returns <code>true</code> if the specified directory exists.</dd>
<dt><code>file_exists()</code></dt>
<dd>Returns <code>true</code> if the file exists.</dd>
</dl>

Please see [the source](http://bitbucket.org/autonomy/sage) for additional useful functions.
