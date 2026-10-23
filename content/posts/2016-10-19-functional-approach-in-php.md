---
author: rodush
categories:
- PHP
date: '2016-10-19T12:16:05+00:00'
tags:
- closure
- functional programming
- php
title: Functional approach in PHP

url: /2016/10/functional-approach-in-php/

---
The code snippet below will only work in PHP-5.3+!.
  
Isn&#8217;t it the famous functional programming with _functions as first class citizens_, closures and other functional bla-bla?

```php
<?php>

function one($a = 0) {
    return function(callable $b) use ($a) {
        return call_user_func($b, $a);
    };
}

print_r(call_user_func(one(1), function ($x) { return $x + 4; } ));
```

This was created just for fun. As you may see, in place of callable you can put any valid PHP callable, e.g.in a form `['Class', 'method']`

Use your imagination for other real things, but also try to stay not cursed later by those who will inherit your untraversable codebase :LOL: