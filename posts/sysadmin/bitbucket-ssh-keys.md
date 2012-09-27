---
title: Multiple SSH Keys with BitBucket
date: '2012-09-27'
description: Generate and associate multiple identities with BitBucket
categories: sysadmin
tags:
    - mercurial
    - bitbucket

---

The SSH interface to both Mercurial and GitHub is more reliable and scalable than their HTTP/HTTPS interfaces. Building on instructions from [BitBucket](https://confluence.atlassian.com/pages/viewpage.action?pageId=271943168#ConfiguringMultipleSSHIdentitiesforGitBash,MacOSX,&Linux-CreatemultipleidentitiesforMacOSX,GitBash,andLinux), we'll outline the setup process for Ubuntu 12.04 LTS.

## Prerequisites

Sign up for a free account at [Bitbucket](http://www.bitbucket.org). You'll receive a confirmation email to the address you used to register. Be sure to confirm your account.

<img src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/sysadmin/multiple-ssh-keys-with-bitbucket/bitbucket-001.png" />

Ensure SSH is installed on your machine:

    $ sudo apt-get install ssh

Next, generate an ssh key pair to associate with your BitBucket account.

    agrothendieck@nk-sbp01:~$ ssh-keygen -f ~/.ssh/bb-agrothendieck -C "bb-agrothendieck"
    Generating public/private rsa key pair.
    Created directory '/home/agrothendieck/.ssh'.
    Enter passphrase (empty for no passphrase): 
    Enter same passphrase again: 
    Your identification has been saved in /home/agrothendieck/.ssh/bb-agrothendieck.
    Your public key has been saved in /home/agrothendieck/.ssh/bb-agrothendieck.pub.
    The key fingerprint is:
    xx:xx:xx:xx:xx:xx:xx:xx:xx:xx:xx:xx:xx:xx:xx:xx bb-agrothendieck
    59:2b:9b:ed:79:67:50:35:2a:fc:a8:7b:bc:78:22:b1 bb-agrothendieck
    The key's randomart image is:
    +--[ RSA 2048]----+
    |                 |
    |               ..|
    |          o   ...|
    |         o + ..  |
    |        S . +.   |
    |       . = ...   |
    |        = +  .   |
    |       E +.=. o  |
    |        .oBo.o   |
    +-----------------+

<div class="alert alert-info">
<span class="label label-info">Note</span> If you intend to use multiple BitBucket accounts, you'll need to generate a new public/private key pair for <em>each account</em>.
</div>

Multiple SSH identities are managed via an SSH `config` file. The format is as follows:

    Host { alias } # a short alias for your identity
        HostName { host } # actual remote host e.g. bitbucket.org or github.com
        PreferredAuthentications publickey
        IdentityFile { path to secret key } # the secret part of your key pair

To access BitBucket via Mercurial, use

    ssh://hg@alias/username/reponame

To access BitBucket via Git, use

    git@alias:username/reponame.git

## Local Mercurial Configuration

Enable `ssh` compression for Mercurial by adding the following entry to your `~/.hgrc` file under `[ui]`:

    [ui]
    username = Alexander Grothendieck <agrothendieck@example.com>
    ssh = ssh -C

### Load Public Keys into BitBucket

Log into BitBucket and go to your Account page (under your username on the top right) and select _SSH keys_. 

<img src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/sysadmin/multiple-ssh-keys-with-bitbucket/bitbucket-002.png" />

`xclip` is a handy tool for cutting and pasting text from the Linux shell. Install it with 

    $ sudo apt-get install xclip

Now you can copy your public key to the clipboard with

    $ xclip -sel clip < ~/.ssh/bb-agrothendieck.pub

<img src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/sysadmin/multiple-ssh-keys-with-bitbucket/bitbucket-003.png" />

<div class="alert alert-error">
<span class="label label-important">Warning</span> Be sure you upload your <em>public</em> key (ends in <tt>pub</tt>).
</div>

<img src="http://dl.dropbox.com/u/59707331/ruhoh/nkabir.ruhoh.com/posts/sysadmin/multiple-ssh-keys-with-bitbucket/bitbucket-004.png" />

Next, ensure `ssh-agent` is running. You can start it up with

    $ ssh-agent bash

<div class="alert alert-info">
<span class="label label-info">Note</span> You do not need <tt>sudo</tt> for this operation.
</div>

List the currently loaded keys with `ssh-add -l`. If your key is not listed, add it with `ssh-add ~/.ssh/bb-agrothendieck`. List the keys again to ensure the add was successful `ssh-add -l`.

## Clone a Repository with SSH

Go to the repository you'd like to clone and select the SSH URL. Then enter the `ssh` clone command. Be sure you're in your `$HOME\hgdev\org.bitbucket\$USER` folder.

    $ hg clone ssh://hg@bb-agrothendieck/agrothendieck/hello

Note that we're using the _alias_ from our `~/.ssh/config` file as the _host_ (`@bb-agrothendieck`).

    agrothendieck@nk-sbp01:~/hgdev/org.bitbucket/agrothendieck$ hg clone ssh://hg@bb-agrothendieck/agrothendieck/hello
    The authenticity of host 'bitbucket.org (207.223.240.181)' can't be established.
    RSA key fingerprint is 97:8c:1b:f2:6f:14:6b:5c:3b:ec:aa:46:46:74:7c:40.
    Are you sure you want to continue connecting (yes/no)? yes
    destination directory: hello
    requesting all changes
    adding changesets
    adding manifests
    adding file changes
    added 1 changesets with 1 changes to 1 files
    updating to branch default
    1 files updated, 0 files merged, 0 files removed, 0 files unresolved
    remote: Warning: Permanently added 'bitbucket.org,207.223.240.181' (RSA) to the list of known hosts.
    agrothendieck@nk-sbp01:~/hgdev/org.bitbucket/agrothendieck$ 

<div class="alert alert-success">You're ready to push and pull with ssh!</div>
