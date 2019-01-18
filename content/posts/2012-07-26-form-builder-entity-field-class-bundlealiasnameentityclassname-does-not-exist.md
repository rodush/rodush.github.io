---
title: 'Form builder — entity field: «Class BundleAliasName:EntityClassName does not exist «'
author: admin
type: post
date: 2012-07-26T12:54:31+00:00
url: /2012/07/form-builder-entity-field-class-bundlealiasnameentityclassname-does-not-exist/
vsw_pmvw_video_source:
  - YouTube
wp-syntax-cache-content:
  - |
    a:2:{i:1;s:1104:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="php" style="font-family:monospace;"><span style="color: #000088;">$builder</span>
                <span style="color: #339933;">-&gt;</span><span style="color: #004000;">add</span><span style="color: #009900;">&#40;</span>
                <span style="color: #0000ff;">'field_name,
                '</span>entity<span style="color: #0000ff;">',
                array(
                     '</span><span style="color: #000000; font-weight: bold;">class</span><span style="color: #0000ff;">' =&gt; '</span>BundleAliasName<span style="color: #339933;">:</span>EntityClassName<span style="color: #0000ff;">',
                     '</span>multiple<span style="color: #0000ff;">' =&gt; true
                )
            )
    .....</span></pre></td></tr></table><p class="theCode" style="display:none;">$builder
                -&gt;add(
                'field_name,
                'entity',
                array(
                     'class' =&gt; 'BundleAliasName:EntityClassName',
                     'multiple' =&gt; true
                )
            )
    .....</p></div>
    ";i:2;s:610:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="php" style="font-family:monospace;"><span style="color: #990000;">array</span><span style="color: #009900;">&#40;</span>
        <span style="color: #0000ff;">'class'</span> <span style="color: #339933;">=&gt;</span> <span style="color: #0000ff;">'Full\Bundle\Path\Entity\EntityClassName'</span><span style="color: #339933;">,</span>
    <span style="color: #009900;">&#41;</span></pre></td></tr></table><p class="theCode" style="display:none;">array(
        'class' =&gt; 'Full\Bundle\Path\Entity\EntityClassName',
    )</p></div>
    ";}
categories:
  - composer
  - PHP
  - symfony
tags:
  - bundle alias
  - doctrine-2.3
  - entity
  - form
  - symfony-2.1

---
После обновления symfony-2.1 до версии из транка (symfony-2.1.0-beta4) отвалилась форма, в которой я использовал поле типа entity, где в качестве класса сущности указал не полный путь к классу, а через bundle alias:

<pre lang="PHP">$builder
            ->add(
            'field_name,
            'entity',
            array(
                 'class' => 'BundleAliasName:EntityClassName',
                 'multiple' => true
            )
        )
.....
</pre>

Код выбрасывал исключение с сообщением 

> &#171;Class BundleAliasName:EntityClassName does not exist&#187;

Если прописать полный путь через пространство имен:

<pre lang="php">array(
    'class' => 'Full\Bundle\Path\Entity\EntityClassName',
)
</pre>

то все работало хорошо.
  
Я открыл по этому поводу [тикет][1] и оказалось, что дело в версии Doctrine! Обновление до 2.3 решило проблему!
  
Огромное спасибо автору комментария на гитхабе [Christophe Coevoet][2]!

 [1]: https://github.com/symfony/symfony/issues/5062
 [2]: https://github.com/stof