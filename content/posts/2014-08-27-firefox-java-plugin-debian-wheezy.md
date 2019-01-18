---
title: Firefox Java Plugin — Debian Wheezy
author: admin
type: post
date: 2014-08-27T08:54:00+00:00
url: /2014/08/firefox-java-plugin-debian-wheezy/
wp-syntax-cache-content:
  - |
    a:1:{i:1;s:1277:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="bash" style="font-family:monospace;"><span style="color: #c20cb9; font-weight: bold;">sudo</span> <span style="color: #c20cb9; font-weight: bold;">ln</span> <span style="color: #660033;">-s</span> <span style="color: #000000; font-weight: bold;">/</span>usr<span style="color: #000000; font-weight: bold;">/</span>lib<span style="color: #000000; font-weight: bold;">/</span>jvm<span style="color: #000000; font-weight: bold;">/</span>jdk1.8.0_20<span style="color: #000000; font-weight: bold;">/</span>jre<span style="color: #000000; font-weight: bold;">/</span>lib<span style="color: #000000; font-weight: bold;">/</span>amd64<span style="color: #000000; font-weight: bold;">/</span>libnpjp2.so <span style="color: #000000; font-weight: bold;">/</span>usr<span style="color: #000000; font-weight: bold;">/</span>lib<span style="color: #000000; font-weight: bold;">/</span>mozilla<span style="color: #000000; font-weight: bold;">/</span>plugins<span style="color: #000000; font-weight: bold;">/</span>libnpjp2.so</pre></td></tr></table><p class="theCode" style="display:none;">sudo ln -s /usr/lib/jvm/jdk1.8.0_20/jre/lib/amd64/libnpjp2.so /usr/lib/mozilla/plugins/libnpjp2.so</p></div>
    ";}
categories:
  - Debian
  - Java
  - System
tags:
  - debian
  - firefox
  - java
  - plugin

---
By default Firefox has no Java plugin because of security issues.
  
One can install plugin by following next steps:
  
0. Exit Firefox browser if it is running
  
1. Make directory if it does not exist -> `/usr/lib/mozilla/plugins`
  
2. Make a symbolic link for libnpjp2.so file which resides in JRE directory, e.g.:

<pre lang="bash">sudo ln -s /usr/lib/jvm/jdk1.8.0_20/jre/lib/amd64/libnpjp2.so /usr/lib/mozilla/plugins/libnpjp2.so
</pre>

Please note, that _amd64_ is an architecture of the OS you have installed, possibly it could be _i386_ in your case.
  
3. Start Firefox and type <kbd>about:plugins</kbd> in address box to check if browser able to see Java plugin.