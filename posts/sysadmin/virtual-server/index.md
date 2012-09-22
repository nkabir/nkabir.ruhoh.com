---
title: Creating a Virtual Server
date: '2012-09-13'
description: Building an Ubuntu 12.04 LTS Server
categories: sysadmin
tags: 
    - ubuntu
    - precise
    - blackbox

---

Ubuntu 12.04 LTS comes in two primary flavors: desktop and server. The server is a bare-bones installation that provides an excellent foundation for deploying services like Apache, Postgres, Liferay and other server applications.

_We assume you've already configured your [VirtualBox environment](sysadmin/virtualization-with-virtualbox)._

## New Virtual Machine

Create a new virtual machine instance.

<img class="diagram" src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/sysadmin/creating-a-virtual-server/virtualbox-001.png" />

<div class="alert alert-info">
Naming is very important if you plan to stay organized with your virtual machines. It's not unusual to have dozens to test various software packages and configurations. 
</div>

### Recommended Naming Convention

    nk-sbp01

* The first part of the name contains my initials. This prevents name collisions when I test my machine on a LAN with other developers. 
* The `s` stands for _server_ (as opposed to `d` when I install a desktop instance).
* The `b` stands for _bridged_ networking.
* The `p` stands for _Precise Pangolin_ (the version of Ubuntu)
* The `01` is incremented as needed for additional machines

<img class="diagram" src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/sysadmin/creating-a-virtual-server/virtualbox-002.png" />

Virtual machines should be allocated at least 2Gb of RAM.

<img class="diagram" src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/sysadmin/creating-a-virtual-server/virtualbox-003.png" />

### Storage

VirtualBox allows virtual machines to allocate more storage space than they'll actually used on disk. These dynamically allocated partitions start out quite small (4Gb) and grow as needed to a specified maximum size. 

<img class="diagram" src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/sysadmin/creating-a-virtual-server/virtualbox-004.png" />

Choose a VDI instance.

<img class="diagram" src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/sysadmin/creating-a-virtual-server/virtualbox-005.png" />

Specify dynamic.

<img class="diagram" src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/sysadmin/creating-a-virtual-server/virtualbox-006.png" />

500GB is a reasonable size for a development virtual machine.

<div class="alert alert-error">
If you're working on a laptop with smaller SSD storage, make this smaller. 50GB will work for most applications.
</div>

<img class="digram" src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/sysadmin/creating-a-virtual-server/server-001.png" />

## Machine Configuration

Once storage has been allocated, choose **Settings** to configure the new virtual machine.

<img class="diagram" src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/sysadmin/creating-a-virtual-server/server-002.png" />

**Be sure to give your machine a clear description.** This will come in handy when you've assembled a large collection of VMs.

<img class="diagram" src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/sysadmin/creating-a-virtual-server/server-003.png" />

<img class="diagram" src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/sysadmin/creating-a-virtual-server/server-004.png" />

Enable **Host I/O cache** for SATA storage.

<img class="diagram" src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/sysadmin/creating-a-virtual-server/server-005.png" />

## Installing Ubuntu Server 12.04 LTS

Download the [64-bit Ubuntu 12.04 LTS iso](http://releases.ubuntu.com/12.04/). Then mount it on your new virtual machine (select the **Empty** icon under the IDE Controller). Make the CD/DVD Drive the Primary Master.

<img class="diagram" src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/sysadmin/creating-a-virtual-server/server-006.png" />

Under the **Network** section, select **Bridged Adapter**.

<div class="alert alert-info">
<em>If you plan to use this on a laptop (instead of a desktop on a LAN), choose NAT.</em> With NAT, your VM will utilize your laptop's connection. This can be helpful is situations where only one IP address is available.
</div>

<img class="diagram" src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/sysadmin/creating-a-virtual-server/server-007.png" />

Hit **OK**.

## Start Your VM

You're ready to start your new VM and install Ubuntu 12.04 LTS Server. Choose **Start** (with the green arrow).

<img class="diagram" src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/sysadmin/creating-a-virtual-server/server-008.png" />

You'll be greeted by the Ubuntu installer. Select **Install Ubuntu Server**.

<img class="diagram" src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/sysadmin/creating-a-virtual-server/server-009.png" />

Enter the same hostname you've selected for the this new VM.

<img class="diagram" src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/sysadmin/creating-a-virtual-server/server-010.png" />

**Create a default user on your machines that is not connected to a specific individual.** Create a user `ubuntu` with password `secret`. This enables developers to quickly be able to log into a colleague's machine to troubleshoot. Obviously, this account is not deployed into production environments.

<img class="diagram" src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/sysadmin/creating-a-virtual-server/server-011.png" />

Next, format the VM's virtual storage. [LVM is unnecessary for a virtual machine guest](http://en.wikipedia.org/wiki/Logical_Volume_Manager_%28Linux%29).

<img class="diagram" src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/sysadmin/creating-a-virtual-server/server-012.png" />

Finally, install SSH to enable remote access to the new server.

<img class="diagram" src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/sysadmin/creating-a-virtual-server/server-013.png" />

## Snapshots

Full machine snapshots are one of the most useful features of virtualization. The entire state of a machine can be saved and restored. Take a snapshot of the newly installed server. First, power off the machine.

<img class="diagram" src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/sysadmin/creating-a-virtual-server/server-014.png" />

Next, click on the **Snapshots** tab on the top right of the window. The click on the camera icon circled in red below.

<img class="diagram" src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/sysadmin/creating-a-virtual-server/server-015.png" />

Be sure to document your snapshot with an appropriate description.

<img class="diagram" src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/sysadmin/creating-a-virtual-server/server-016.png" />

<div class="alert alert-success">
The new virtual machine is ready. You can now experiment and always know that you can revert to a clean installation. In the future, we'll take advantage of <em>cloning</em> so we don't have to repeat this installation procedure.
</div>

<img class="diagram" src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/sysadmin/creating-a-virtual-server/server-017.png" />


