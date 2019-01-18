---
title: Postgres and earthdistance extension
author: admin
type: post
date: 2013-09-24T20:50:49+00:00
url: /2013/09/postgres-and-earthdistance-extension/
wp-syntax-cache-content:
  - |
    a:10:{i:1;s:1324:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="bash" style="font-family:monospace;">root<span style="color: #000000; font-weight: bold;">@</span>debian:<span style="color: #000000; font-weight: bold;">/</span>home<span style="color: #000000; font-weight: bold;">/</span>web<span style="color: #666666; font-style: italic;"># apt-cache search postgres | grep contrib</span>
    postgresql-contrib - additional facilities <span style="color: #000000; font-weight: bold;">for</span> PostgreSQL <span style="color: #7a0874; font-weight: bold;">&#40;</span>supported version<span style="color: #7a0874; font-weight: bold;">&#41;</span>
    postgresql-contrib-<span style="color: #000000;">8.4</span> - additional facilities <span style="color: #000000; font-weight: bold;">for</span> PostgreSQL
    postgresql-contrib-<span style="color: #000000;">9.1</span> - additional facilities <span style="color: #000000; font-weight: bold;">for</span> PostgreSQL</pre></td></tr></table><p class="theCode" style="display:none;">root@debian:/home/web# apt-cache search postgres | grep contrib
    postgresql-contrib - additional facilities for PostgreSQL (supported version)
    postgresql-contrib-8.4 - additional facilities for PostgreSQL
    postgresql-contrib-9.1 - additional facilities for PostgreSQL</p></div>
    ";i:2;s:374:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="bash" style="font-family:monospace;"><span style="color: #c20cb9; font-weight: bold;">apt-get install</span> postgresql-contrib postgresql-contrib-x.y</pre></td></tr></table><p class="theCode" style="display:none;">apt-get install postgresql-contrib postgresql-contrib-x.y</p></div>
    ";i:3;s:432:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="bash" style="font-family:monospace;"><span style="color: #000000; font-weight: bold;">/</span>etc<span style="color: #000000; font-weight: bold;">/</span>init.d<span style="color: #000000; font-weight: bold;">/</span>postgresql restart</pre></td></tr></table><p class="theCode" style="display:none;">/etc/init.d/postgresql restart</p></div>
    ";i:4;s:282:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="bash" style="font-family:monospace;"><span style="color: #c20cb9; font-weight: bold;">su</span> postgres</pre></td></tr></table><p class="theCode" style="display:none;">su postgres</p></div>
    ";i:5;s:707:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="bash" style="font-family:monospace;"><span style="color: #7a0874; font-weight: bold;">cd</span> <span style="color: #000000; font-weight: bold;">/</span>usr<span style="color: #000000; font-weight: bold;">/</span>share<span style="color: #000000; font-weight: bold;">/</span>postgresql<span style="color: #000000; font-weight: bold;">/</span><span style="color: #000000;">8.4</span><span style="color: #000000; font-weight: bold;">/</span>contrib<span style="color: #000000; font-weight: bold;">/</span></pre></td></tr></table><p class="theCode" style="display:none;">cd /usr/share/postgresql/8.4/contrib/</p></div>
    ";i:6;s:421:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="bash" style="font-family:monospace;">psql <span style="color: #660033;">-U</span> user_name <span style="color: #660033;">-d</span> database_name <span style="color: #660033;">-f</span> module_name.sql</pre></td></tr></table><p class="theCode" style="display:none;">psql -U user_name -d database_name -f module_name.sql</p></div>
    ";i:7;s:647:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="bash" style="font-family:monospace;">psql <span style="color: #660033;">-U</span> postgres <span style="color: #660033;">-d</span> your_database_name <span style="color: #660033;">-f</span> cube.sql
    psql <span style="color: #660033;">-U</span> postgres <span style="color: #660033;">-d</span> your_database_name <span style="color: #660033;">-f</span> earthdistance.sql</pre></td></tr></table><p class="theCode" style="display:none;">psql -U postgres -d your_database_name -f cube.sql
    psql -U postgres -d your_database_name -f earthdistance.sql</p></div>
    ";i:8;s:653:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="bash" style="font-family:monospace;"><span style="color: #7a0874; font-weight: bold;">cd</span> <span style="color: #000000; font-weight: bold;">/</span>usr<span style="color: #000000; font-weight: bold;">/</span>share<span style="color: #000000; font-weight: bold;">/</span>postgresql<span style="color: #000000; font-weight: bold;">/</span><span style="color: #000000;">9.1</span><span style="color: #000000; font-weight: bold;">/</span>extension</pre></td></tr></table><p class="theCode" style="display:none;">cd /usr/share/postgresql/9.1/extension</p></div>
    ";i:9;s:906:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="sql" style="font-family:monospace;"><span style="color: #993333; font-weight: bold;">CREATE</span> EXTENSION <span style="color: #ff0000;">&quot;cube&quot;</span>; <span style="color: #808080; font-style: italic;">-- you will not be able install &quot;earthdistance&quot; w/o &quot;cube&quot; extension</span>
    <span style="color: #993333; font-weight: bold;">CREATE</span> EXTENSION <span style="color: #ff0000;">&quot;earthdistance&quot;</span>; <span style="color: #808080; font-style: italic;">--or any other extension you need</span></pre></td></tr></table><p class="theCode" style="display:none;">CREATE EXTENSION &quot;cube&quot;; -- you will not be able install &quot;earthdistance&quot; w/o &quot;cube&quot; extension
    CREATE EXTENSION &quot;earthdistance&quot;; --or any other extension you need</p></div>
    ";i:10;s:1340:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="sql" style="font-family:monospace;"><span style="color: #66cc66;">...</span> <span style="color: #993333; font-weight: bold;">WHERE</span> earth_box<span style="color: #66cc66;">&#40;</span>ll_to_earth<span style="color: #66cc66;">&#40;</span><span style="color: #66cc66;">&#123;</span>longitude_float_value<span style="color: #66cc66;">&#125;</span><span style="color: #66cc66;">,</span> <span style="color: #66cc66;">&#123;</span>latitude_float_value<span style="color: #66cc66;">&#125;</span><span style="color: #66cc66;">&#41;</span><span style="color: #66cc66;">,</span> <span style="color: #66cc66;">&#123;</span>radius_in_meters<span style="color: #66cc66;">&#125;</span><span style="color: #66cc66;">&#41;</span> @<span style="color: #66cc66;">&gt;</span> ll_to_earth<span style="color: #66cc66;">&#40;</span>some_table<span style="color: #66cc66;">.</span>latitude<span style="color: #66cc66;">,</span> some_table<span style="color: #66cc66;">.</span>longitude<span style="color: #66cc66;">&#41;</span></pre></td></tr></table><p class="theCode" style="display:none;">... WHERE earth_box(ll_to_earth({longitude_float_value}, {latitude_float_value}), {radius_in_meters}) @&gt; ll_to_earth(some_table.latitude, some_table.longitude)</p></div>
    ";}
categories:
  - Databases
  - Debian
  - PostgreSQL
tags:
  - coordinates
  - distance
  - earth
  - earthbox
  - extension
  - geolocation
  - postgis
  - postgres
  - spatial

---
First of all, let me describe how one can install extensions for your Postgresql.
  
It depends whether you have version 8.4+ or 9.1+ installed.

In following sections I will describe procedure related to Debian based OSes.

First of all, you have to install contrib packages for corresponding version:

<pre lang="bash">root@debian:/home/web# apt-cache search postgres | grep contrib
postgresql-contrib - additional facilities for PostgreSQL (supported version)
postgresql-contrib-8.4 - additional facilities for PostgreSQL
postgresql-contrib-9.1 - additional facilities for PostgreSQL
</pre>

with command:

<pre lang="bash">apt-get install postgresql-contrib postgresql-contrib-x.y
</pre>

After that, restart postgresql daemon:

<pre lang="bash">/etc/init.d/postgresql restart
</pre>

Change to the database owner account, e.g.:

<pre lang="bash">su postgres
</pre>

Change to the contrib modules&#8217; directory:

<pre lang="bash">cd /usr/share/postgresql/8.4/contrib/
</pre>

Now, there are 2 different way how you could install extensions for your database.

**1. Postgres-8.4.x**
  
Load the SQL files for needed extension using command:

<pre lang="bash">psql -U user_name -d database_name -f module_name.sql
</pre>

for example,

<pre lang="bash">psql -U postgres -d your_database_name -f cube.sql
psql -U postgres -d your_database_name -f earthdistance.sql
</pre>

**2. Postgres-9.1.x**
  
Extensions are stored under _/usr/share/postgresql/9.1/extension_ directory,
  
so you need to cd to it:

<pre lang="bash">cd /usr/share/postgresql/9.1/extension
</pre>

and then launch _psql_.
  
In opened database console run this query:

<pre lang="sql">CREATE EXTENSION "cube"; -- you will not be able install "earthdistance" w/o "cube" extension
CREATE EXTENSION "earthdistance"; --or any other extension you need
</pre>

That is all &#8212; you can use installed extension.

Okay, now lets proceed to the main topic of the post.
  
What is earthdistance?
  
It is a simplified solution to make calculations over spatial coordinates (latitude, longitude), calculate distance between two points in the Earth.
  
In case if you do not want install and learn PostGIS extension for the Postgres DB, although that extension provides much more functionality, you can go with earthdistance.
  
In earthdistance the Earth is treated as an ideal sphere and if it works for you &#8212; you don&#8217;t have too precise calculations -, then you can earthdistance.
  
Otherwise you definitely should take a look at PostGIS.

So, here is the main point &#8212; what the SQL should look like when you want to search location of some subject based on its coordinates?
  
Just use such expression in WHERE part of you SQL (for example):

<pre lang="SQL">... WHERE earth_box(ll_to_earth({longitude_float_value}, {latitude_float_value}), {radius_in_meters}) @> ll_to_earth(some_table.latitude, some_table.longitude)
</pre>

of course values in curly braces should be just numbers, no need to put { and } outside.