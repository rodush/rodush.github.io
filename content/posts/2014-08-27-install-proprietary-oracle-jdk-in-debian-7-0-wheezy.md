---
title: Install proprietary Oracle JDK in Debian 7.0 Wheezy
author: admin
type: post
date: 2014-08-27T07:29:58+00:00
url: /2014/08/install-proprietary-oracle-jdk-in-debian-7-0-wheezy/
wp-syntax-cache-content:
  - |
    a:3:{i:1;s:2810:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="bash" style="font-family:monospace;"><span style="color: #c20cb9; font-weight: bold;">sudo</span> update-alternatives <span style="color: #660033;">--install</span> <span style="color: #000000; font-weight: bold;">/</span>usr<span style="color: #000000; font-weight: bold;">/</span>bin<span style="color: #000000; font-weight: bold;">/</span><span style="color: #c20cb9; font-weight: bold;">java</span> <span style="color: #c20cb9; font-weight: bold;">java</span> <span style="color: #000000; font-weight: bold;">/</span>usr<span style="color: #000000; font-weight: bold;">/</span>lib<span style="color: #000000; font-weight: bold;">/</span>jvm<span style="color: #000000; font-weight: bold;">/</span>jdk<span style="color: #000000; font-weight: bold;">/</span>bin<span style="color: #000000; font-weight: bold;">/</span><span style="color: #c20cb9; font-weight: bold;">java</span> <span style="color: #000000;">1071</span>
    <span style="color: #c20cb9; font-weight: bold;">sudo</span> update-alternatives <span style="color: #660033;">--install</span> <span style="color: #000000; font-weight: bold;">/</span>usr<span style="color: #000000; font-weight: bold;">/</span>bin<span style="color: #000000; font-weight: bold;">/</span><span style="color: #c20cb9; font-weight: bold;">javac</span> <span style="color: #c20cb9; font-weight: bold;">javac</span> <span style="color: #000000; font-weight: bold;">/</span>media<span style="color: #000000; font-weight: bold;">/</span>mydisk<span style="color: #000000; font-weight: bold;">/</span>jdk<span style="color: #000000; font-weight: bold;">/</span><span style="color: #c20cb9; font-weight: bold;">javac</span> <span style="color: #000000;">1071</span>
    <span style="color: #c20cb9; font-weight: bold;">sudo</span> update-alternatives <span style="color: #660033;">--install</span> <span style="color: #000000; font-weight: bold;">/</span>usr<span style="color: #000000; font-weight: bold;">/</span>bin<span style="color: #000000; font-weight: bold;">/</span>jcontrol jcontrol <span style="color: #000000; font-weight: bold;">/</span>media<span style="color: #000000; font-weight: bold;">/</span>mydisk<span style="color: #000000; font-weight: bold;">/</span>jdk<span style="color: #000000; font-weight: bold;">/</span>bin<span style="color: #000000; font-weight: bold;">/</span>jcontrol <span style="color: #000000;">1071</span></pre></td></tr></table><p class="theCode" style="display:none;">sudo update-alternatives --install /usr/bin/java java /usr/lib/jvm/jdk/bin/java 1071
    sudo update-alternatives --install /usr/bin/javac javac /media/mydisk/jdk/javac 1071
    sudo update-alternatives --install /usr/bin/jcontrol jcontrol /media/mydisk/jdk/bin/jcontrol 1071</p></div>
    ";i:2;s:839:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="bash" style="font-family:monospace;"><span style="color: #c20cb9; font-weight: bold;">sudo</span> update-alternatives <span style="color: #660033;">--config</span> <span style="color: #c20cb9; font-weight: bold;">java</span>
    <span style="color: #c20cb9; font-weight: bold;">sudo</span> update-alternatives <span style="color: #660033;">--config</span> <span style="color: #c20cb9; font-weight: bold;">javac</span>
    <span style="color: #c20cb9; font-weight: bold;">sudo</span> update-alternatives <span style="color: #660033;">--config</span> jcontrol</pre></td></tr></table><p class="theCode" style="display:none;">sudo update-alternatives --config java
    sudo update-alternatives --config javac
    sudo update-alternatives --config jcontrol</p></div>
    ";i:3;s:447:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="bash" style="font-family:monospace;"><span style="color: #c20cb9; font-weight: bold;">java</span> <span style="color: #660033;">-version</span>
    <span style="color: #c20cb9; font-weight: bold;">javac</span> <span style="color: #660033;">-version</span></pre></td></tr></table><p class="theCode" style="display:none;">java -version
    javac -version</p></div>
    ";}
categories:
  - Debian
  - Java
  - System
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

---
This is a YAP (yet another post) about how one can manually install Oracle&#8217;s proprietary JDK/JRE version (in Debian 7.0 Wheezy as an example).

First of all, download fresh version of JDK/JRE from the [Oracle website][1].
  
Copy archive to desired location, in the following example we will use 

<pre>/usr/lib/jvm</pre>

as an installation source directory.
  
Unpack the archive and run next commands:

<pre lang="bash">sudo update-alternatives --install /usr/bin/java java /usr/lib/jvm/jdk/bin/java 1071
sudo update-alternatives --install /usr/bin/javac javac /media/mydisk/jdk/javac 1071
sudo update-alternatives --install /usr/bin/jcontrol jcontrol /media/mydisk/jdk/bin/jcontrol 1071
</pre>

You may need read man pages for update-alternatives to check out the parameters and what they mean.

Now, if you want freshly installed version of java/javac to be default in your system, run next commands:

<pre lang="bash">sudo update-alternatives --config java
sudo update-alternatives --config javac
sudo update-alternatives --config jcontrol
</pre>

Follow the instructions issued by update-alternatives to select default version among the list of available installations.
  
After that, check if everything worked fine by issuing commands

<pre lang="bash">java -version
javac -version
</pre>

You should see 1.8.0 for both.

 [1]: http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html "jdk8-downloads"