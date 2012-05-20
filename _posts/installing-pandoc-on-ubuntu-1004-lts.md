---
title: Installing Pandoc on Ubuntu 10.04 LTS
date: '2012-05-19'
description: Install the latest Pandoc on Lucid
categories: sysadmin
tags: 
    - ubuntu
    - pandoc
    - lucid

layout: post

---

These instructions are from [Francesco Rodriguez](http://www.frodsan.com/2011/12/27/installing-haskell-ubuntu.html) and are repeated here for completeness.

First install dependencies:

    $ sudo apt-get install libgmp3-dev freeglut3 freeglut3-dev

Next, you must install `GDHC 7.0.4`

    $ wget http://www.haskell.org/ghc/dist/7.0.4/ghc-7.0.4-x86_64-unknown-linux.tar.bz2
    $ tar -xvvf ghc-7.0.4-x86_64-unknown-linux.tar.bz2 
    $ cd ghc-7.0.4
    $ ./configure
    $ sudo make install

Finally, install `Haskell Platform 2011.4.0.0`

    $ wget http://lambda.haskell.org/platform/download/2011.4.0.0/haskell-platform-2011.4.0.0.tar.gz
    $ tar -xvvf haskell-platform-2011.4.0.0
    $ cd haskell-platform-2011.4.0.0
    $ ./configure
    $ sudo make install

Run a quick test to confirm all is well:

    $ ghci
    Prelude> "Hello, Haskell World!"
    "Hello, Haskell World!"
    Prelude> :quit # this is for leaving haskell
    Leaving GHCi.

You now have `cabal` installed.

    $ cabal update
    $ cabal install pandoc

Finally, to ensure you use the new `pandoc`, add `$HOME/.cabal/bin` to your `PATH`. 
