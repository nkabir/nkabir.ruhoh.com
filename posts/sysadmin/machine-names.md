---
title: Machine Names
date: '2012-09-13'
description: Assigning names to machines in Ubuntu
categories: sysadmin
tags: 
    - ubuntu
    - precise
    - blackbox

---

## Fully Qualified Machine Name

_Note that this handled automatically by the `bbstaticip` package._

Machines on our network obtain their fully qualified domain names from a DHCP server. But where does the DHCP server obtain its      name? To configure a machine to return a fully qualified domain name (`apollo.example.com`), you need to edit `/etc/hosts`

    127.0.0.1   apollo.example.com apollo localhost
    127.0.1.1   apollo

_Order matters._ This configuration ensures that your fully qualified domain name can be queried by Python's `socket.getfqdn()` function.

