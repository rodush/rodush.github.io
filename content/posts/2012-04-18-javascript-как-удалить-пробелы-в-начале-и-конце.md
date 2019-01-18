---
title: JavaScript — как удалить пробелы в начале и конце строки (trim)
author: admin
type: post
date: 2012-04-18T12:57:57+00:00
url: /2012/04/javascript-как-удалить-пробелы-в-начале-и-конце/
categories:
  - JavaScript
tags:
  - extend
  - howto
  - javascript
  - leading
  - space
  - trailing
  - trim

---
Уже миллионы раз написано, но вставлю и я свои &#171;5 копеек&#187; в тему.
  
В javascript нет встроенной функции для обрезания лишних пробелов в начале и конце строки.
  
Чтобы реализовать такую возможность можно добавить необходимый метод в объект String javascript:
  
<code lang="javascript">&lt;br />
String.prototype.trim = function(str) { return str.replace(/^\s+|\s+$/g, ""); }&lt;br />
</code>