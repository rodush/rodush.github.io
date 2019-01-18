---
title: Для PHP-5.4 Debian — нет suhosin, xcache, xdebug расширений
author: admin
type: post
date: 2012-03-25T12:44:23+00:00
url: /2012/03/для-php-5-4-debian-нет-suhosin-xcache-xdebug-расширений/
categories:
  - PHP
  - System
tags:
  - debian
  - extension
  - fatal error
  - module
  - 'null'
  - php5.4
  - suhosin
  - xcache

---
Сегодня проапгрейдил свою Debian OS 6.0 (настроено apt-pinning).
  
Среди прочих апдейтов при выполнении dist-upgrade привалили и обновления для ряда установленных модулей php5.  Обновился и сам PHP, собственно до версии 5.4.0-2. Но&#8230; тут начались непонятные проблемы &#8212; ни один локальный сайт не работал! В логах были непонятные ошибки, скажем, для сайта, основанного на фреймворке  YII было сообщение:

<pre>[Sun Mar 25 13:32:51 2012] [error] [client 127.0.0.1] PHP Fatal error:  Call to undefined function (null)() in /home/web/ccc/frontend/index.php on line 4</pre>

А на той строке 4 ничего не было особенного, окромя dirname(\_\_FILE\_\_)!
  
Порыскав-поискав в интернете похожие ошибки, не нашел ничего. Запостил баг на php.net.
  
Но дело-то неприятное! Ничегошеньки ведь не работает&#8230;
  
Начал копаться дальше. Попробовал запустить скрипты php из консоли, дабы проверить &#8212; неужто dirname() убрали? 🙂 И обнаружил еще ряд замечательных уведомлений warnings:

> rodush@rdushko:/var/www$ php test.php
  
> Failed loading /usr/lib/php5/20090626+lfs/xdebug.so: /usr/lib/php5/20090626+lfs/xdebug.so: cannot open shared object file: No such file or directory
  
> PHP Warning: PHP Startup: Unable to load dynamic library &#8216;/usr/lib/php5/20100525+lfs/suhosin.so&#8217; &#8212; /usr/lib/php5/20100525+lfs/suhosin.so: cannot open shared object file: No such file or directory in Unknown on line 0
  
> PHP Warning: PHP Startup: Unable to load dynamic library &#8216;/usr/lib/php5/20100525+lfs/xhprof.so&#8217; &#8212; /usr/lib/php5/20100525+lfs/xhprof.so: cannot open shared object file: No such file or directory in Unknown on line 0

А дальше директива dirname() отработала и подключился файл, который я подключал.
  
Заглянув в директорию, указанную в сообщении, я обнаружил, что таких библиотек действительно нету!
  
Пока решил не морочить голову: допишут &#8212; обновлюсь; решил убрать конфиги php для данных библиотек.
  
Они расположены в директории /etc/php5/conf.d/
  
просто переименовал все конфиги, на которые не пришли обновления файлы с суффиксом &#171;old&#187; (на будущее пригодятся :), думаю) 

> suhosin.ini.old xdebug.ini.old xcache.ini.old xhprof.ini.old

Попробовал вызов из консоли &#8212; не ругается php. Попробовал зайти на сайты в броузере и &#8212; о чудо! &#8212; всё работает!!
  
Вот такие вот причуды могут быть, если php ругается на невозможность подключить дополнительные модули-библиотеки.