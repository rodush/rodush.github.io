---
author: rodush
categories:
  - Programming
date: '2012-07-26T12:54:31+00:00'
hiddenInHomeList: "true"
tags:
  - PHP
  - doctrine
  - entity
  - form
  - symfony
  - upgrade
  - error
title: 'Form builder — entity field: «Class BundleAliasName:EntityClassName does not exist «'
url: /2012/07/form-builder-entity-field-class-bundlealiasnameentityclassname-does-not-exist/
---

После обновления symfony-2.1 до версии из транка (symfony-2.1.0-beta4) отвалилась форма, в которой я использовал поле типа entity, где в качестве класса сущности указал не полный путь к классу, а через bundle alias:

```php
$builder->add('field_name, 'entity',
    array(
        'class' => 'BundleAliasName:EntityClassName',
        'multiple' => true
    )
)
// .....
```

Код выбрасывал исключение с сообщением 

> &#171;Class BundleAliasName:EntityClassName does not exist&#187;

Если прописать полный путь через пространство имен:

```php
array(
    'class' => 'Full\Bundle\Path\Entity\EntityClassName',
)
```

то все работало хорошо.
  
Я открыл по этому поводу [тикет][1] и оказалось, что дело в версии Doctrine! Обновление до 2.3 решило проблему!
  
Огромное спасибо автору комментария на гитхабе [Christophe Coevoet][2]!

 [1]: https://github.com/symfony/symfony/issues/5062
 [2]: https://github.com/stof