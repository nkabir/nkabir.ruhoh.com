---

title: Blackbox Mint Library
date: '2012-05-26'
description: The python library for the Blackbox stack.
categories: sysadmin
tags: 
    - ubuntu
    - python
    - precise
    - blackbox

layout: post

---

## Introduction

Mint is a collection of Python scripts that provide common functionality including:

* `util` --- a package of assorted utilities
* `chrono` --- a date and time library
* `disk` --- a file and folder library
* `template` --- a text templating library based on Jinja2
* `xml` --- an xml parsing library based on lxml
* `store` --- a library for managing the storage of externally sourced data
* `net` --- a networking library
* `arg` --- a command line library
* `config` --- configuration management for Python applications
* `portion` --- Debian-based package management
* `app` --- a package for high level Python applications

`bin` is where executable `mint` scripts are stored. The `mint` packages are layered so that there are no cyclical dependencies. 

The base package is `util`. Each subsequent package may only depend on a previous one. For example, `template` may only depend on `disk`, `chrono`, and `util`.

The source code for `mint` is available at [http://bitbucket.org/autonomy/mint](http://bitbucket.org/autonomy/mint).

The packaging source is available at [http://bitbucket.org/autonomy/bbpackage](http://bitbucket.org/autonomy/bbpackage)

## Installation

`bbmint` depends on `bbsage`. To install `bbmint`:

	$ sudo apt-get update
	$ sudo apt-get install bbmint

This installs `mint` into `/opt/bbmint/` where the current version is always symlinked to `/opt/bbmint/current`.
