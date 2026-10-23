---
author: rodush
categories:
- PHP
- databases
date: '2011-03-27T12:26:40+00:00'
tags:
- cookie
- php
- pma
- session
- timeout
title: How to change PHPMyAdmin session timeout
url: /2011/03/how-to-change-phpmyadmin-session-timeout/
---
By default, the session lifetime in a new PhpMyAdmin installation using the "cookie"; authentication method is 1440 seconds (24 minutes). That is, after 24 minutes of inactivity, the next request will take the user to the login page. To increase the session lifetime, set the value of the variable to say, 60x longer:

```php
$cfg['LoginCookieValidity'] = 1440 * 60; // 86400 means one day (24-hours)
```
