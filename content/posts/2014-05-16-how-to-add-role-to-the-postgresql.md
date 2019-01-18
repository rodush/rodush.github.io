---
title: How to add role to the PostgreSQL
author: admin
type: post
date: 2014-05-16T09:15:01+00:00
url: /2014/05/how-to-add-role-to-the-postgresql/
wp-syntax-cache-content:
  - |
    a:1:{i:1;s:383:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="bash" style="font-family:monospace;"><span style="color: #c20cb9; font-weight: bold;">sudo</span> <span style="color: #660033;">-u</span> postgres createuser NEEDED_USERNAME</pre></td></tr></table><p class="theCode" style="display:none;">sudo -u postgres createuser NEEDED_USERNAME</p></div>
    ";}
categories:
  - Databases
  - Debian
  - PostgreSQL
  - System

---
If you need have superuser access to PostgreSQL via command line psql utility, create needed username first:

<pre lang="bash">sudo -u postgres createuser NEEDED_USERNAME</pre>

You will be asked whether role should be a superuser:

> Shall the new role be a superuser? (y/n)

answer Y (yes) if so and hit Enter.
  
Now you have NEEDED_USERNAME allowed to access databases as a superuser via psql.