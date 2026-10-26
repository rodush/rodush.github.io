---
author: rodush
categories:
  - HowTo
  - Databases
tags:
  - databases
  - Debian
  - PostgreSQL
  - system
date: '2014-05-16T09:15:01+00:00'
hiddenInHomeList: "true"
title: How to add role to the PostgreSQL
url: /2014/05/how-to-add-role-to-the-postgresql/
---
If you need have superuser access to PostgreSQL via command line psql utility, create needed username first:

```sh
sudo -u postgres createuser NEEDED_USERNAME
```

You will be asked whether role should be a superuser:

> Shall the new role be a superuser? (y/n)

answer "_Y_" (yes) if so and hit `Enter`.
  
Now you allowed the `NEEDED_USERNAME` to access databases as a superuser via `psql`.