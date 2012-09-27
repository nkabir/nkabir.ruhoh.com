---
title: Virtualization with VirtualBox
date: '2011-10-15'
description: Setting up a VirtualBox development environment
categories: sysadmin
tags:
    - ubuntu
    - blackbox

---

VirtualBox is a free virtualization package [available from Oracle](http://www.virtualbox.org). The makers of VirtualBox were [originally a company purchased by Sun Microsystems](http://en.wikipedia.org/wiki/VirtualBox). Some attractive features of this package include:

* Open source
* Runs on Macintosh, Linux and Windows
* Supports OVF

## Installation on Host Machine

Download the latest [VirtualBox package for your host system](https://www.virtualbox.org/wiki/Downloads) (4.2.0 as of this post). Run the installer.


Be sure to check the **Default Machine Folder** in **Preferences** to ensure you're using _a path without spaces_. On Unix systems, I use `$HOME/vms` for personal installations and `/opt/vms` for shared (server) installations.

<img class="diagram" src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/sysadmin/virtualization-with-virtualbox/config-virtualbox-001.png" />

Next, ensure that you have an _internal network configured_. An internal network is a virtual network managed by VirtualBox that allows you test services that you do not want running on your local lan. For example, a test [DHCP server](http://en.wikipedia.org/wiki/Dynamic_Host_Configuration_Protocol) could disrupt clients on your local network.

<img class="diagram" src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/sysadmin/virtualization-with-virtualbox/config-virtualbox-002.png" />

* Click the plus (+) on the network card icon circled in red.
* Ensure you have an entry `vboxnet0` list in **Host-only Networks**.

Finally, ensure that you do _not_ have a DHCP server running on your internal network. We will use pfSense or our own DHCP servers on our internal networks.

<img class="diagram" src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/sysadmin/virtualization-with-virtualbox/config-virtualbox-003.png" />

<div class="alert alert-success">
That's it! You're ready to start setting up virtual machines.
</div>

<div class="alert alert-info">
<em>Note that when you're installing VirtualBox on your local machine, you can install it as yourself. However, if you're installing it on shared servers, be sure to use a machine account rather than a personal account.</em>
</div>

