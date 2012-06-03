---
title: Blackbox Apt-Cacher Client
date: '2012-05-27'
description: A debian package cache
categories: sysadmin
tags:
    - ubuntu
    - precise
    - blackbox

layout: post

---

## Introduction

Apt-Cacher NG is a debian package cache. There are two components--a client and a server. 

<img src="{{paths.media}}/apt-cacher-ng.png"/>

## Installation

### Server

Choose a machine on your network to be the apt cache server. Ideally, you should create a `CNAME` entry for this service in DNS (e.g. `debcache`). Install the server with

	$ sudo apt-get install apt-cacher-ng

You'll need the hostname or `CNAME` of this machine for the client installation.

### Client

To configure clients, install the `bbacngclient` package.

	$ sudo apt-get install bbacngclient

You'll be asked for the hostname and port of your `apt-cacher-ng` server. A default port, `3142`, is provided.


