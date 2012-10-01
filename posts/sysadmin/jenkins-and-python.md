---
title: Jenkins and Python
date: '2012-10-01'
description: Configuring Jenkins to run Python projects
categories: sysadmin
tags:
    - precise
    - build

---

Python integration with Jenkins is based on the [Shining Panda plugin](https://www.shiningpanda-ci.com/docs/tutorials/101.html). Follow the tutorial with the following modifications.

## Configuration

### Test & Code Coverage

In the command area, use the following expanded set:

    pip install coverage nose pyflakes clonedigger
    coverage run tests/run.py --with-xunit
    coverage xml
    sloccount --duplicates --wide --details . | fgrep -v .svn > sloccount.sc || :
    find . -name "*.py" | egrep -v '^./tests/'| xargs pyflakes  > pyflakes.log || :
    clonedigger --cpd-output . || :

### Static Code Analysis

In the command area, use the following expanded set:

    pip install pylint
    pylint --rcfile scripts/pylintrc -f parseable pygments > pylint.txt


