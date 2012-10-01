---
title: Sonar Installation
date: '2012-10-01'
description: Sonar Code Metrics
categories: sysadmin
tags:
    - precise
    - build

---

Sonar is an open platform to manage code quality. Quality management is an important part of any project, but sometimes it can be difficult to get a global picture. Any given metric, such as code coverage or code complexity, can be difficult to interpret in isolation. This is where Sonar comes into the picture. Sonar gives you a dynamic view of both snapshot and historical data coming from all of these tools. 

## Installation

Sonar is available as a BlackBox package `bbsonar`. Install with

    $ sudo apt-get install bbsonar

Before starting Sonar, enable MySQL by editing `/opt/bbsonar/current/conf/sonar.properties`. Comment out the Hypersonic entry:

    # Comment the following line to deactivate the default embedded database.
    # sonar.jdbc.url:                            jdbc:h2:tcp://localhost:9092/sonar

And uncomment the MySQL entries:

    #----- MySQL 5.x/6.x
    # Comment the embedded database and uncomment the following line to use MySQL
    sonar.jdbc.url:                            jdbc:mysql://localhost:3306/sonar?...

    # Optional properties
    sonar.jdbc.driverClassName:                com.mysql.jdbc.Driver

Start sonar and tail the log file:

    $ sudo service sonar start && tail -f /opt/bbsonar/current/logs/sonar.log

Once the initial startup completes, connect to sonar at `http://{sonarhost}:9000`. The default _username_ and _password_ combination is `admin/admin`.

## Security

Sonar has an LDAP plugin that integrates logins with a directory server. Go to the _Update Center_ under _Configuration_. Find _LDAP_ under _Available Plugins_ and install. Sonar will need to be stopped after the installation to update the configuration file `/opt/bbsonar/current/conf/sonar.properties`. Configuration instructions are [available](http://docs.codehaus.org/display/SONAR/LDAP+Plugin#LDAPPlugin-UsageInstallation). Add the following entries to the bottom of the file:

    sonar.security.realm=LDAP
    ldap.url=ldap://yourldaphost:389
    ldap.user.baseDn=ou=users,dc=example,dc=com
    ldap.group.baseDn=ou=groups,dc=example,dc=com

Save the edits and start Sonar.

    $ sudo service sonar start

LDAP users will now be able to log in. The admin role allows flexible configuration of security access controls.
