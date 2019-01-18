---
title: PHP strtotime — проблема с датами со слешем (slash)
author: admin
type: post
date: 2011-01-29T12:48:17+00:00
url: /2011/01/php-strtotime-проблема-с-датами-со-слешем-slash/
wp-syntax-cache-content:
  - |
    a:1:{i:1;s:933:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="php" style="font-family:monospace;"><span style="color: #000088;">$date</span> <span style="color: #339933;">=</span> <span style="color: #990000;">strtotime</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">&quot;21/10/2010&quot;</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
    <span style="color: #b1b100;">echo</span> <span style="color: #990000;">date</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">&quot;d.m.Y&quot;</span><span style="color: #339933;">,</span> <span style="color: #000088;">$date</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span></pre></td></tr></table><p class="theCode" style="display:none;">$date = strtotime(&quot;21/10/2010&quot;);
    echo date(&quot;d.m.Y&quot;, $date);</p></div>
    ";}
categories:
  - PHP

---
Есть одна особенность у РНР функции **strtotime**: она не умеет распознавать даты, которые записаны через слеш &#171;/&#187;. Если мы применим даную функцию к дате, записаной в виде, скажем &#171;21/01/2010&#187;, то на выходе получим:

<pre lang="PHP">$date = strtotime("21/10/2010");
echo date("d.m.Y", $date);
</pre>

Вызов данного скрипта выведет такое:

<pre>01.01.1970
</pre>