---
author: rodush
date: '2013-09-24T20:50:49+00:00'
hiddenInHomeList: "true"
categories:
  - Programming
  - Databases
tags:
  - coordinates
  - distance
  - earth
  - earthbox
  - extension
  - geolocation
  - postgis
  - postgres
  - postgresql
  - spatial
title: Postgres and earthdistance extension
url: /2013/09/postgres-and-earthdistance-extension/
---

First of all, let me describe how one can install extensions for your Postgresql.
  
It depends whether you have version 8.4+ or 9.1+ installed.

In following sections I will describe procedure related to Debian based OSes.

First of all, you have to install contrib packages for corresponding version:

```sh
root@debian:/home/web# apt-cache search postgres | grep contrib
postgresql-contrib - additional facilities for PostgreSQL (supported version)
postgresql-contrib-8.4 - additional facilities for PostgreSQL
postgresql-contrib-9.1 - additional facilities for PostgreSQL
```

with command:

```sh
apt-get install postgresql-contrib postgresql-contrib-x.y
```

After that, restart postgresql daemon:

```sh
/etc/init.d/postgresql restart
```

Change to the database owner account, e.g.:

```sh
su postgres
```

Go to the contrib modules' directory:

```sh
cd /usr/share/postgresql/8.4/contrib/
```

Now, there are 2 different way how you could install extensions for your database.

## Postgres-8.4.x
  
Load the SQL files for needed extension using command:

```sh
psql -U user_name -d database_name -f module_name.sql
```

for example,

```sh
psql -U postgres -d your_database_name -f cube.sql
psql -U postgres -d your_database_name -f earthdistance.sql
```

## Postgres-9.1.x
  
Extensions are stored under _/usr/share/postgresql/9.1/extension_ directory,
  
so you need to cd to it:

```sh
cd /usr/share/postgresql/9.1/extension
```

and then launch _psql_.
  
In the opened database console run this query:

```sql
CREATE EXTENSION "cube"; -- you will not be able install "earthdistance" w/o "cube" extension
CREATE EXTENSION "earthdistance"; --or any other extension you need
```

That is all &#8212; you can use installed extension.

Okay, now lets proceed to the main topic of the post.
  
What is earthdistance?
  
It is a simplified solution to make calculations over spatial coordinates (latitude, longitude), calculate distance between two points in the Earth.
  
In case if you do not want install and learn PostGIS extension for the Postgres DB, although that extension provides much more functionality, you can go with earthdistance.
  
In earthdistance the Earth is treated as an ideal sphere and if it works for you &#8212; you don&#8217;t have too precise calculations -, then you can earthdistance.
  
Otherwise you definitely should take a look at PostGIS.

So, here is the main point &#8212; what the SQL should look like when you want to search location of some subject based on its coordinates?
  
Just use such expression in WHERE part of you SQL (for example):

```sql
...
WHERE earth_box(ll_to_earth({longitude_float_value}, {latitude_float_value}), {radius_in_meters}) @> ll_to_earth(some_table.latitude, some_table.longitude)
```

of course, values inside curly braces should be just numbers, no need to put `{` and `}` outside.