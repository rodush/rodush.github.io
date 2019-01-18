---
title: Как обновить проект с symfony-2.0 до symfony-2.1
author: admin
type: post
date: 2012-07-07T19:57:18+00:00
url: /2012/07/как-обновить-проект-с-symfony-2-0-до-symfony-2-1/
vsw_pmvw_video_source:
  - YouTube
wp-syntax-cache-content:
  - |
    a:5:{i:1;s:362:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="bash" style="font-family:monospace;">php bin<span style="color: #000000; font-weight: bold;">/</span>vendors <span style="color: #c20cb9; font-weight: bold;">install</span></pre></td></tr></table><p class="theCode" style="display:none;">php bin/vendors install</p></div>
    ";i:2;s:252:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="bash" style="font-family:monospace;">php composer.phar update</pre></td></tr></table><p class="theCode" style="display:none;">php composer.phar update</p></div>
    ";i:3;s:462:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="bash" style="font-family:monospace;">php composer.phar create-project symfony<span style="color: #000000; font-weight: bold;">/</span>framework-standard-edition path<span style="color: #000000; font-weight: bold;">/</span></pre></td></tr></table><p class="theCode" style="display:none;">php composer.phar create-project symfony/framework-standard-edition path/</p></div>
    ";i:4;s:411:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="yml" style="font-family:monospace;">{
        &quot;require&quot;: {
            &quot;friendsofsymfony/user-bundle&quot;: &quot;*&quot;
        }
    }</pre></td></tr></table><p class="theCode" style="display:none;">{
        &quot;require&quot;: {
            &quot;friendsofsymfony/user-bundle&quot;: &quot;*&quot;
        }
    }</p></div>
    ";i:5;s:252:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="bash" style="font-family:monospace;">php composer.phar update</pre></td></tr></table><p class="theCode" style="display:none;">php composer.phar update</p></div>
    ";}
categories:
  - composer
  - PHP
  - symfony
  - Без рубрики
tags:
  - howto
  - project
  - symfony
  - upgrade

---
Изначально я создавал свой проект на версии symfony 2.0 без vendors (standard edition). Все зависимости были установлены через

<pre lang="bash">php bin/vendors install</pre>

Проект находился в git-репозитории.

Сразу оговорка &#8212; на момент написания статьи версия symfony 2.1 находилась в стадии бета-тестирования.
  
Тем не менее, основная тенденция уже была понятна и значительных изменений в АПИ не предвиделось.
  
Одно из ключевых нововведений в symfony 2.1 &#8212; использование <a href="http://getcomposer.org/" title="Composer" target="_blank">Composer</a>.
  
На вебсайте фреймворка Symfony можно найти описание процесса создания **нового** проекта, но нет информации как обновить существующий.

Итак, начнем-с.
  
Изначально я попытался просто скопировать содержимое файла composer.json, находящегося в директории фреймворка Symnofy на github, и выполнить команду

<pre lang="bash">php composer.phar update</pre>

но там нет всех зависимостей, необходимых для нормального функционирования проекта.
  
Потому я просто решил создать новый &#171;пустой&#187; проект:

<pre lang="bash">php composer.phar create-project symfony/framework-standard-edition path/</pre>

в отдельной ветке git-репозитория и потом перенести изменения из ветки с версией symfony-2.0.

Признаюсь, что пришлось порешать конфликты в файлах apps/AppKernel.php, файлах config.yml, security.yml и других.
  
Но это не было слишком сложным заданием.
  
Также необходимо проапгрейдить все дополнительные bundle, которые вы используете до соответствующих версий под symfony-2.1
  
К примеру, для FOSUserBundle (https://github.com/FriendsOfSymfony/FOSUserBundle/blob/master/Resources/doc/index.md#installation) 

<pre lang="yml">{
    "require": {
        "friendsofsymfony/user-bundle": "*"
    }
}
</pre>

и далее выполнить команду

<pre lang="bash">php composer.phar update</pre>

Таже необходимо сделать изменения согласно [этой инструкции][1] в файлах форм и других местах. Тут уже дело персональное &#8212; смотря кто какие фичи использовал в своем проекте.

Таким образом, после всех проделанных манипуляций проект запустился успешно.
  
Из видимых изменений &#8212; добавили красивостей к web-debug-toolbar &#8212; появились тултипы со сводной информацией по каждому из разделов, которые показываются при наведении мышью на соответствующую иконку.

П.С.: Вот на днях встретил другой вариант апгрейда до symfony-2.1: http://buildthedamnproduct.com/upgrading-symfony-to-21-10415

 [1]: https://github.com/symfony/symfony/blob/master/UPGRADE-2.1.md