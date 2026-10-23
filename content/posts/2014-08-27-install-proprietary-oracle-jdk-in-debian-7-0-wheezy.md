---
author: rodush
categories:
- Debian
- Java
- System
date: '2014-08-27T07:29:58+00:00'
tags:
- custom
- debian
- installation
- java
- jdk
- jre
- jvm
- manual
- oracle
- wheezy
title: Install proprietary Oracle JDK in Debian 7.0 Wheezy
url: /2014/08/install-proprietary-oracle-jdk-in-debian-7-0-wheezy/
---
This is a YAP (yet another post) about how one can manually install Oracle&#8217;s proprietary JDK/JRE version (in Debian 7.0 Wheezy as an example).

First of all, download fresh version of JDK/JRE from the [Oracle website][1].
  
Copy archive to desired location, in the following example we will use 

`/usr/lib/jvm`

as an installation source directory.
  
Unpack the archive and run next commands:

```sh
sudo update-alternatives --install /usr/bin/java java /usr/lib/jvm/jdk/bin/java 1071
sudo update-alternatives --install /usr/bin/javac javac /media/mydisk/jdk/javac 1071
sudo update-alternatives --install /usr/bin/jcontrol jcontrol /media/mydisk/jdk/bin/jcontrol 1071
```

You may need read man pages for update-alternatives to check out the parameters and what they mean.

Now, if you want freshly installed version of java/javac to be default in your system, run next commands:

```bash
sudo update-alternatives --config java
sudo update-alternatives --config javac
sudo update-alternatives --config jcontrol
```

Follow the instructions issued by update-alternatives to select default version among the list of available installations.
  
After that, check if everything worked fine by issuing commands

```bash
java -version
javac -version
```

You should see 1.8.0 for both.

 [1]: http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html "jdk8-downloads"