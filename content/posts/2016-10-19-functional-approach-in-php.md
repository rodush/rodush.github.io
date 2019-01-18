---
title: Functional approach in PHP
author: admin
type: post
date: 2016-10-19T12:16:05+00:00
url: /2016/10/functional-approach-in-php/
wp-syntax-cache-content:
  - |
    a:1:{i:1;s:2711:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="php" style="font-family:monospace;"><span style="color: #339933;">&amp;</span>lt<span style="color: #339933;">;</span>?php
    &nbsp;
    <span style="color: #000000; font-weight: bold;">function</span> one<span style="color: #009900;">&#40;</span><span style="color: #000088;">$a</span> <span style="color: #339933;">=</span> <span style="color: #cc66cc;">0</span><span style="color: #009900;">&#41;</span> <span style="color: #009900;">&#123;</span>
        <span style="color: #b1b100;">return</span> <span style="color: #000000; font-weight: bold;">function</span><span style="color: #009900;">&#40;</span>callable <span style="color: #000088;">$b</span><span style="color: #009900;">&#41;</span> <span style="color: #000000; font-weight: bold;">use</span> <span style="color: #009900;">&#40;</span><span style="color: #000088;">$a</span><span style="color: #009900;">&#41;</span> <span style="color: #009900;">&#123;</span>
            <span style="color: #b1b100;">return</span> <span style="color: #990000;">call_user_func</span><span style="color: #009900;">&#40;</span><span style="color: #000088;">$b</span><span style="color: #339933;">,</span> <span style="color: #000088;">$a</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
        <span style="color: #009900;">&#125;</span><span style="color: #339933;">;</span>
    <span style="color: #009900;">&#125;</span>
    &nbsp;
    <span style="color: #990000;">print_r</span><span style="color: #009900;">&#40;</span><span style="color: #990000;">call_user_func</span><span style="color: #009900;">&#40;</span>one<span style="color: #009900;">&#40;</span><span style="color: #cc66cc;">1</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">,</span> <span style="color: #000000; font-weight: bold;">function</span> <span style="color: #009900;">&#40;</span><span style="color: #000088;">$x</span><span style="color: #009900;">&#41;</span> <span style="color: #009900;">&#123;</span> <span style="color: #b1b100;">return</span> <span style="color: #000088;">$x</span> <span style="color: #339933;">+</span> <span style="color: #cc66cc;">4</span><span style="color: #339933;">;</span> <span style="color: #009900;">&#125;</span> <span style="color: #009900;">&#41;</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span></pre></td></tr></table><p class="theCode" style="display:none;">&amp;lt;?php
    
    function one($a = 0) {
        return function(callable $b) use ($a) {
            return call_user_func($b, $a);
        };
    }
    
    print_r(call_user_func(one(1), function ($x) { return $x + 4; } ));</p></div>
    ";}
categories:
  - PHP
tags:
  - closure
  - functional programming
  - php

---
The code snippet below will only work in PHP-5.3+!.
  
Isn&#8217;t it the famous functional programming with _functions as first class citizens_, closures and other functional bla-bla?

<pre lang="php">&lt;?php

function one($a = 0) {
    return function(callable $b) use ($a) {
        return call_user_func($b, $a);
    };
}

print_r(call_user_func(one(1), function ($x) { return $x + 4; } ));
</pre>

This was created just for fun. As you may see, in place of callable you can put any valid PHP callable, e.g.in a form `['Class', 'method']`

Use your imagination for other real things, but also try to stay not cursed later by those who will inherit your untraversable codebase :LOL: