---
title: Composer — minimum-stability по-умолчанию считается stable
author: admin
type: post
date: 2012-07-04T20:39:30+00:00
url: /2012/07/composer-minimum-stability-по-умолчанию-считается-stable/
vsw_pmvw_video_source:
  - YouTube
categories:
  - composer
  - PHP
  - symfony
tags:
  - beta
  - composer
  - dev
  - stability
  - stable
  - symfony
  - update

---
Сегодня (4 июля 2012) Composer изменяет значение по-умолчанию свойства stability с dev на stable.
  
Подробнее [здесь][1] и [здесь][2].
  
Что это значит? Что по-умолчанию Composer будет игнорировать пакеты RC, beta, alpha или dev.
  
Столкнулся я с этим, когда попытался проапдейтить зависимости проекта, использующего symfony-2.1.x, которая на момент написания заметки находится на стадии бета-тестирования.

`<br />
rodush@debian:~/gtrs$ php composer.phar update<br />
Updating dependencies<br />
Your requirements could not be solved to an installable set of packages.<br />
` 

Вот что подсказал скрипт:

> Potential causes:
   
> &#8212; A typo in the package name
   
> &#8212; The package is not available in a stable-enough version according to your minimum-stability setting
     
> see https://groups.google.com/d/topic/composer-dev/_g3ASeIFlrc/discussion for more details. 

Чтобы обойти данную проблему, самый простой способ &#8212; это в файл composer.json добавить свойство
  
`"minimum-stability": "dev"`

 [1]: https://groups.google.com/forum/#!topic/composer-dev/_g3ASeIFlrc/discussion
 [2]: http://getcomposer.org/doc/04-schema.md#minimum-stability