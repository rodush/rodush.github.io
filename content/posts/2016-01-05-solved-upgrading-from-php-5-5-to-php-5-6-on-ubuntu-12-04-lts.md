---
title: '[SOLVED] Upgrading from PHP 5.5 to PHP 5.6 on Ubuntu 12.04 LTS'
author: admin
type: post
date: 2016-01-05T10:50:58+00:00
url: /2016/01/solved-upgrading-from-php-5-5-to-php-5-6-on-ubuntu-12-04-lts/
wp-syntax-cache-content:
  - |
    a:7:{i:1;s:366:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="bash" style="font-family:monospace;"><span style="color: #c20cb9; font-weight: bold;">sudo</span> <span style="color: #c20cb9; font-weight: bold;">apt-get dist-upgrade</span></pre></td></tr></table><p class="theCode" style="display:none;">sudo apt-get dist-upgrade</p></div>
    ";i:2;s:420:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="bash" style="font-family:monospace;"><span style="color: #c20cb9; font-weight: bold;">sudo</span> <span style="color: #c20cb9; font-weight: bold;">apt-get remove</span> php<span style="color: #000000; font-weight: bold;">*</span></pre></td></tr></table><p class="theCode" style="display:none;">sudo apt-get remove php*</p></div>
    ";i:3;s:511:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="bash" style="font-family:monospace;"><span style="color: #c20cb9; font-weight: bold;">sudo</span> <span style="color: #c20cb9; font-weight: bold;">dpkg</span> <span style="color: #660033;">-l</span> <span style="color: #000000; font-weight: bold;">|</span> <span style="color: #c20cb9; font-weight: bold;">grep</span> php</pre></td></tr></table><p class="theCode" style="display:none;">sudo dpkg -l | grep php</p></div>
    ";i:4;s:1089:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="php" style="font-family:monospace;">sudo apt<span style="color: #339933;">-</span>get clean <span style="color: #339933;">&amp;</span>amp<span style="color: #339933;">;&amp;</span>amp<span style="color: #339933;">;</span> sudo apt<span style="color: #339933;">-</span>get autoclean
    sudo apt<span style="color: #339933;">-</span>get udpate <span style="color: #339933;">&amp;</span>amp<span style="color: #339933;">;&amp;</span>amp<span style="color: #339933;">;</span> sudo apt<span style="color: #339933;">-</span>get upgrade <span style="color: #339933;">&amp;</span>amp<span style="color: #339933;">;&amp;</span>amp<span style="color: #339933;">;</span> sudo apt<span style="color: #339933;">-</span>get dist<span style="color: #339933;">-</span>upgrade</pre></td></tr></table><p class="theCode" style="display:none;">sudo apt-get clean &amp;amp;&amp;amp; sudo apt-get autoclean
    sudo apt-get udpate &amp;amp;&amp;amp; sudo apt-get upgrade &amp;amp;&amp;amp; sudo apt-get dist-upgrade</p></div>
    ";i:5;s:1772:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="bash" style="font-family:monospace;"><span style="color: #c20cb9; font-weight: bold;">sudo</span> <span style="color: #c20cb9; font-weight: bold;">apt-get</span> <span style="color: #660033;">-f</span> <span style="color: #c20cb9; font-weight: bold;">install</span> php5-json
    Reading package lists... Done
    Building dependency <span style="color: #c20cb9; font-weight: bold;">tree</span>       
    Reading state information... Done
    Some packages could not be installed. This may mean that you have
    requested an impossible situation or <span style="color: #000000; font-weight: bold;">if</span> you are using the unstable
    distribution that some required packages have not yet been created
    or been moved out of Incoming.
    The following information may <span style="color: #7a0874; font-weight: bold;">help</span> to resolve the situation:
    &nbsp;
    The following packages have unmet dependencies:
     php5-json : Depends: phpapi-<span style="color: #000000;">20121212</span>
    E: Unable to correct problems, you have held broken packages.</pre></td></tr></table><p class="theCode" style="display:none;">sudo apt-get -f install php5-json
    Reading package lists... Done
    Building dependency tree       
    Reading state information... Done
    Some packages could not be installed. This may mean that you have
    requested an impossible situation or if you are using the unstable
    distribution that some required packages have not yet been created
    or been moved out of Incoming.
    The following information may help to resolve the situation:
    
    The following packages have unmet dependencies:
     php5-json : Depends: phpapi-20121212
    E: Unable to correct problems, you have held broken packages.</p></div>
    ";i:6;s:4134:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="bash" style="font-family:monospace;"><span style="color: #000000; font-weight: bold;">/</span>etc<span style="color: #000000; font-weight: bold;">/</span>apt<span style="color: #000000; font-weight: bold;">/</span>sources.list.d$ ll
    total <span style="color: #000000;">32</span>
    drwxr-xr-x <span style="color: #000000;">2</span> root root <span style="color: #000000;">4096</span> Jan  <span style="color: #000000;">5</span> <span style="color: #000000;">11</span>:<span style="color: #000000;">12</span> .<span style="color: #000000; font-weight: bold;">/</span>
    drwxr-xr-x <span style="color: #000000;">6</span> root root <span style="color: #000000;">4096</span> Jan  <span style="color: #000000;">5</span> <span style="color: #000000;">11</span>:<span style="color: #000000;">11</span> ..<span style="color: #000000; font-weight: bold;">/</span>
    <span style="color: #660033;">-rw-r--r--</span> <span style="color: #000000;">1</span> root root  <span style="color: #000000;">138</span> Jan  <span style="color: #000000;">5</span> <span style="color: #000000;">10</span>:<span style="color: #000000;">32</span> chris-lea-node_js-precise.list
    <span style="color: #660033;">-rw-r--r--</span> <span style="color: #000000;">1</span> root root  <span style="color: #000000;">138</span> Jan  <span style="color: #000000;">5</span> <span style="color: #000000;">10</span>:<span style="color: #000000;">32</span> chris-lea-node_js-precise.list.save
    <span style="color: #660033;">-rw-r--r--</span> <span style="color: #000000;">1</span> root root   <span style="color: #000000;">60</span> Jan  <span style="color: #000000;">5</span> <span style="color: #000000;">10</span>:<span style="color: #000000;">32</span> nginx-stable-lucid.list
    <span style="color: #660033;">-rw-r--r--</span> <span style="color: #000000;">1</span> root root   <span style="color: #000000;">60</span> Jan  <span style="color: #000000;">5</span> <span style="color: #000000;">10</span>:<span style="color: #000000;">32</span> nginx-stable-lucid.list.save
    <span style="color: #660033;">-rw-r--r--</span> <span style="color: #000000;">1</span> root root  <span style="color: #000000;">134</span> Jan  <span style="color: #000000;">5</span> <span style="color: #000000;">10</span>:<span style="color: #000000;">32</span> ondrej-php5-<span style="color: #000000;">5</span>_6-precise.list
    <span style="color: #660033;">-rw-r--r--</span> <span style="color: #000000;">1</span> root root  <span style="color: #000000;">134</span> Jan  <span style="color: #000000;">5</span> <span style="color: #000000;">10</span>:<span style="color: #000000;">32</span> ondrej-php5-<span style="color: #000000;">5</span>_6-precise.list.save
    <span style="color: #660033;">-rw-r--r--</span> <span style="color: #000000;">1</span> root root  <span style="color: #000000;">126</span> Jan  <span style="color: #000000;">5</span> <span style="color: #000000;">10</span>:<span style="color: #000000;">32</span> ondrej-php5-precise.list
    <span style="color: #660033;">-rw-r--r--</span> <span style="color: #000000;">1</span> root root  <span style="color: #000000;">126</span> Jan  <span style="color: #000000;">5</span> <span style="color: #000000;">10</span>:<span style="color: #000000;">32</span> ondrej-php5-precise.list.save</pre></td></tr></table><p class="theCode" style="display:none;">/etc/apt/sources.list.d$ ll
    total 32
    drwxr-xr-x 2 root root 4096 Jan  5 11:12 ./
    drwxr-xr-x 6 root root 4096 Jan  5 11:11 ../
    -rw-r--r-- 1 root root  138 Jan  5 10:32 chris-lea-node_js-precise.list
    -rw-r--r-- 1 root root  138 Jan  5 10:32 chris-lea-node_js-precise.list.save
    -rw-r--r-- 1 root root   60 Jan  5 10:32 nginx-stable-lucid.list
    -rw-r--r-- 1 root root   60 Jan  5 10:32 nginx-stable-lucid.list.save
    -rw-r--r-- 1 root root  134 Jan  5 10:32 ondrej-php5-5_6-precise.list
    -rw-r--r-- 1 root root  134 Jan  5 10:32 ondrej-php5-5_6-precise.list.save
    -rw-r--r-- 1 root root  126 Jan  5 10:32 ondrej-php5-precise.list
    -rw-r--r-- 1 root root  126 Jan  5 10:32 ondrej-php5-precise.list.save</p></div>
    ";i:7;s:2706:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="bash" style="font-family:monospace;"><span style="color: #c20cb9; font-weight: bold;">sudo</span> <span style="color: #c20cb9; font-weight: bold;">apt-get install</span> php5
    Reading package lists... Done
    Building dependency <span style="color: #c20cb9; font-weight: bold;">tree</span>
    Reading state information... Done
    The following packages were automatically installed and are no longer required:
      shtool libc-client2007e node-node-uuid libicu52 libicu48 libv8-3.7.12.22 libmcrypt4 libt1-<span style="color: #000000;">5</span> mlock libssl-dev libvpx1 libssl-doc zlib1g-dev libgd3 libev4 libv8-dev libc-ares2 libev-dev
      libc-ares-dev
    Use <span style="color: #ff0000;">'apt-get autoremove'</span> to remove them.
    The following extra packages will be installed:
      libapache2-mod-php5 php5-cli php5-json php5-readline
    Suggested packages:
      php-pear
    The following NEW packages will be installed:
      libapache2-mod-php5 php5 php5-cli php5-json php5-readline
    <span style="color: #000000;">0</span> upgraded, <span style="color: #000000;">5</span> newly installed, <span style="color: #000000;">0</span> to remove and <span style="color: #000000;">0</span> not upgraded.
    Need to get <span style="color: #000000;">5</span>,<span style="color: #000000;">575</span> kB of archives.
    After this operation, <span style="color: #000000;">18.9</span> MB of additional disk space will be used.
    Do you want to <span style="color: #7a0874; font-weight: bold;">continue</span> <span style="color: #7a0874; font-weight: bold;">&#91;</span>Y<span style="color: #000000; font-weight: bold;">/</span>n<span style="color: #7a0874; font-weight: bold;">&#93;</span>? Y</pre></td></tr></table><p class="theCode" style="display:none;">sudo apt-get install php5
    Reading package lists... Done
    Building dependency tree
    Reading state information... Done
    The following packages were automatically installed and are no longer required:
      shtool libc-client2007e node-node-uuid libicu52 libicu48 libv8-3.7.12.22 libmcrypt4 libt1-5 mlock libssl-dev libvpx1 libssl-doc zlib1g-dev libgd3 libev4 libv8-dev libc-ares2 libev-dev
      libc-ares-dev
    Use 'apt-get autoremove' to remove them.
    The following extra packages will be installed:
      libapache2-mod-php5 php5-cli php5-json php5-readline
    Suggested packages:
      php-pear
    The following NEW packages will be installed:
      libapache2-mod-php5 php5 php5-cli php5-json php5-readline
    0 upgraded, 5 newly installed, 0 to remove and 0 not upgraded.
    Need to get 5,575 kB of archives.
    After this operation, 18.9 MB of additional disk space will be used.
    Do you want to continue [Y/n]? Y</p></div>
    ";}
categories:
  - Debian
  - PHP
  - System
tags:
  - php
  - php56
  - ubuntu 12.04 LTS
  - upgrade

---
Recently I had to upgrade PHP version on the build server based on Ubuntu 12.04 LTS to PHP 5.6 At that moment there was PHP 5.5 installed on the server. Everything should have been as easy and promising as described, for example, in [this post][1]. Yes, it was going well to the moment

<pre lang="bash">sudo apt-get dist-upgrade</pre>

Then dpkg claimed unmet dependencies&#8230; You know, as usual. I decided &#8212; f&#8230;k it, I will remove existing php and everything related. Simple removal with

<pre lang="bash">sudo apt-get remove php*</pre>

did not work fine and stuck on removing _phpmyadmin_.

That guysexited with an error code 10 being reported from its post-remove script. After pretty short googling, I found [the solution which worked][2] for me.

The similar shit happened with _php5-imagick_ package, so the solution I used was similar to phpmyadmin removal. Afterwards, I checked for presence anything starting with or inlcuding _php_:

<pre lang="bash">sudo dpkg -l | grep php</pre>

Everything was clean. OK, here we go&#8230;

<pre lang="php">sudo apt-get clean && sudo apt-get autoclean
sudo apt-get udpate && sudo apt-get upgrade && sudo apt-get dist-upgrade
</pre>

&#8230;and still the same error in result:

> Reading package lists&#8230; Done Building dependency tree Reading state information&#8230; Done Some packages could not be installed. This may mean that you have requested an impossible situation or if you are using the unstable distribution that some required packages have not yet been created or been moved out of Incoming. The following information may help to resolve the situation: The following packages have unmet dependencies: php5 : Depends: libapache2-mod-php5 (>= 5.6.16+dfsg-2+deb.sury.org~precise+1~) but it is not going to be installed or libapache2-mod-php5filter (>= 5.6.16+dfsg-2+deb.sury.org~precise+1~) but it is not going to be installed or php5-cgi (>= 5.6.16+dfsg-2+deb.sury.org~precise+1~) but it is not going to be installed or php5-fpm (>= 5.6.16+dfsg-2+deb.sury.org~precise+1~) but it is not going to be installed E: Unable to correct problems, you have held broken packages.

I tried install with **-f** flag, package-by-package. Nothing worked. The final unmet dependency was:

<pre lang="bash">sudo apt-get -f install php5-json
Reading package lists... Done
Building dependency tree       
Reading state information... Done
Some packages could not be installed. This may mean that you have
requested an impossible situation or if you are using the unstable
distribution that some required packages have not yet been created
or been moved out of Incoming.
The following information may help to resolve the situation:

The following packages have unmet dependencies:
 php5-json : Depends: phpapi-20121212
E: Unable to correct problems, you have held broken packages.
</pre>

And here I stuck, as googling at this point didn&#8217;t help me at all&#8230; I visited the [home of php5.6 PPA][3] hoping to find something there. And a brilliant idea came to my mind &#8212; I should check APT&#8217;s sources list! I saw this files inside **/etc/apt/sources.list.d**:

<pre lang="bash">/etc/apt/sources.list.d$ ll
total 32
drwxr-xr-x 2 root root 4096 Jan  5 11:12 ./
drwxr-xr-x 6 root root 4096 Jan  5 11:11 ../
-rw-r--r-- 1 root root  138 Jan  5 10:32 chris-lea-node_js-precise.list
-rw-r--r-- 1 root root  138 Jan  5 10:32 chris-lea-node_js-precise.list.save
-rw-r--r-- 1 root root   60 Jan  5 10:32 nginx-stable-lucid.list
-rw-r--r-- 1 root root   60 Jan  5 10:32 nginx-stable-lucid.list.save
-rw-r--r-- 1 root root  134 Jan  5 10:32 ondrej-php5-5_6-precise.list
-rw-r--r-- 1 root root  134 Jan  5 10:32 ondrej-php5-5_6-precise.list.save
-rw-r--r-- 1 root root  126 Jan  5 10:32 ondrej-php5-precise.list
-rw-r--r-- 1 root root  126 Jan  5 10:32 ondrej-php5-precise.list.save
</pre>

I realised, the problem could be that packages were overwritten from older php-5.5, which apparently was installed manually to the server some time earlier. Once I removed these two files:

> ondrej-php5-precise.list ondrej-php5-precise.list.save

and updated apt one more time, I was able to install PHP 5.6 as usual:

<pre lang="bash">sudo apt-get install php5
Reading package lists... Done
Building dependency tree
Reading state information... Done
The following packages were automatically installed and are no longer required:
  shtool libc-client2007e node-node-uuid libicu52 libicu48 libv8-3.7.12.22 libmcrypt4 libt1-5 mlock libssl-dev libvpx1 libssl-doc zlib1g-dev libgd3 libev4 libv8-dev libc-ares2 libev-dev
  libc-ares-dev
Use 'apt-get autoremove' to remove them.
The following extra packages will be installed:
  libapache2-mod-php5 php5-cli php5-json php5-readline
Suggested packages:
  php-pear
The following NEW packages will be installed:
  libapache2-mod-php5 php5 php5-cli php5-json php5-readline
0 upgraded, 5 newly installed, 0 to remove and 0 not upgraded.
Need to get 5,575 kB of archives.
After this operation, 18.9 MB of additional disk space will be used.
Do you want to continue [Y/n]? Y</pre>

The main idea of this story, before adding new custom repository for PHP, make sure you removed any other old ones! Good luck and happy coding!

 [1]: http://joshtronic.com/2014/09/14/upgrade-php-53-to-php-56-on-ubuntu-1204-lts/ "PHP 5.3 to PHP 5.6 on Ubuntu 12.04"
 [2]: http://ubuntuforums.org/showthread.php?t=881086
 [3]: https://launchpad.net/~ondrej/+archive/ubuntu/php5-5.6