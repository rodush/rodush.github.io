---
title: PHPMyAdmin session timeout
author: admin
type: post
date: 2011-03-27T12:26:40+00:00
url: /2011/03/phpmyadmin-session-timeout/
wp-syntax-cache-content:
  - |
    a:1:{i:1;s:749:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="php" style="font-family:monospace;"><span style="color: #000088;">$cfg</span><span style="color: #009900;">&#91;</span><span style="color: #0000ff;">'LoginCookieValidity'</span><span style="color: #009900;">&#93;</span> <span style="color: #339933;">=</span> <span style="color: #cc66cc;">1440</span> <span style="color: #339933;">*</span> <span style="color: #cc66cc;">60</span><span style="color: #339933;">;</span> <span style="color: #666666; font-style: italic;">// 86400 means one day (24-hours)</span></pre></td></tr></table><p class="theCode" style="display:none;">$cfg['LoginCookieValidity'] = 1440 * 60; // 86400 means one day (24-hours)</p></div>
    ";}
categories:
  - Без рубрики
tags:
  - cookie
  - php
  - pma
  - session
  - timeout

---
По-умолчанию время жизни сессии в новой инсталляции PhpMyAdmin и способе авторизации &#8216;cookie&#8217; составляет 1440 секунд (24 минуты). Т.е. после 24 минут бездействия следующее обращение приведёт пользователя на страницу авторизации. Чтобы увеличить время жизни сессии, необходимо установить значение переменной 

<pre lang="PHP">$cfg['LoginCookieValidity'] = 1440 * 60; // 86400 means one day (24-hours)</pre>

, скажем в 60 раз, что составит сутки.