---
title: Symfony, Yaml отключение файла
author: admin
type: post
date: 2010-09-28T12:46:00+00:00
url: /2010/09/symfony-yaml-отключение-файла/
wp-syntax-cache-content:
  - |
    a:3:{i:1;s:396:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="yaml" style="font-family:monospace;"><span style="color: #007F45;">key</span><span style="font-weight: bold; color: brown;">:
    </span>  - value1.css
      - value2.css
      - value3.css</pre></td></tr></table><p class="theCode" style="display:none;">key:
      - value1.css
      - value2.css
      - value3.css</p></div>
    ";i:2;s:400:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="yaml" style="font-family:monospace;"><span style="color: #007F45;">key</span><span style="font-weight: bold; color: brown;">:
    </span>  - value1.css
      - - value2.css
      - value3.css</pre></td></tr></table><p class="theCode" style="display:none;">key:
      - value1.css
      - - value2.css
      - value3.css</p></div>
    ";i:3;s:398:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="yaml" style="font-family:monospace;"><span style="color: #007F45;">key</span><span style="font-weight: bold; color: brown;">:
    </span>  - value1.css
      - -value2.css
      - value3.css</pre></td></tr></table><p class="theCode" style="display:none;">key:
      - value1.css
      - -value2.css
      - value3.css</p></div>
    ";}
categories:
  - symfony
tags:
  - config
  - symfony
  - YAML
  - yml
  - настройка
  - отключить файл

---
Бывает так, что в некоторых конфигурационных файлах для представления view.yml необходимо отключить некоторые из файлов &#8212; css или javascript. Как известно, массив в yml можно определить как 

<pre lang="YAML">key:
  - value1.css
  - value2.css
  - value3.css
</pre>

Отлючается определенный файл с помощью директивы &#171;-&#187; (обычный дефис).
  
Иногда при отключении файла можно случайно либо по незнанию некорректно поставить прочерк (между знаком отключения и название файла появится пробел), т.е., к примеру при желании отключить второй файл value2.css мы напишем:

<pre lang="YAML">key:
  - value1.css
  - - value2.css
  - value3.css
</pre>

В таком случае наша директива не сработает.
  
Корректно писать так:

<pre lang="YAML">key:
  - value1.css
  - -value2.css
  - value3.css
</pre>

Об этом явно говорится в документации. Но часто бывает так, что кто ж её читает, когда есть &#171;гугль в помощь&#187;!