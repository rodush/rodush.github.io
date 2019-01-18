---
title: Symfony sfThumbnailPlugin как виджет формы
author: admin
type: post
date: 2010-06-28T20:20:31+00:00
url: /2010/06/пример-использования-sfthumbnailplugin-как-виджета/
wp-syntax-cache-content:
  - |
    a:3:{i:1;s:2788:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="php" style="font-family:monospace;"><span style="color: #666666; font-style: italic;">//................................</span>
    <span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">function</span> configure<span style="color: #009900;">&#40;</span><span style="color: #009900;">&#41;</span>
    <span style="color: #009900;">&#123;</span>
      <span style="color: #000088;">$this</span><span style="color: #339933;">-&gt;</span><span style="color: #004000;">widgetSchema</span><span style="color: #009900;">&#91;</span><span style="color: #0000ff;">'photo'</span><span style="color: #009900;">&#93;</span> <span style="color: #339933;">=</span> <span style="color: #000000; font-weight: bold;">new</span> sfWidgetFormInputFileEditable<span style="color: #009900;">&#40;</span>
        <span style="color: #990000;">array</span><span style="color: #009900;">&#40;</span>
          <span style="color: #0000ff;">'file_src'</span>  <span style="color: #339933;">=&gt;</span> <span style="color: #0000ff;">'/uploads/doctors/thumb/'</span> <span style="color: #339933;">.</span> <span style="color: #000088;">$this</span><span style="color: #339933;">-&gt;</span><span style="color: #004000;">getObject</span><span style="color: #009900;">&#40;</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">-&gt;</span><span style="color: #004000;">getPhoto</span><span style="color: #009900;">&#40;</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">,</span>
          <span style="color: #0000ff;">'is_image'</span>  <span style="color: #339933;">=&gt;</span> <span style="color: #009900; font-weight: bold;">true</span><span style="color: #339933;">,</span>
          <span style="color: #0000ff;">'with_delete'</span> <span style="color: #339933;">=&gt;</span> <span style="color: #009900; font-weight: bold;">true</span><span style="color: #339933;">,</span>
          <span style="color: #0000ff;">'delete_label'</span>  <span style="color: #339933;">=&gt;</span> <span style="color: #0000ff;">&quot;Удалить фото&quot;</span>
        <span style="color: #009900;">&#41;</span>
    <span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span></pre></td></tr></table><p class="theCode" style="display:none;">//................................
    public function configure()
    {
      $this-&gt;widgetSchema['photo'] = new sfWidgetFormInputFileEditable(
        array(
          'file_src'  =&gt; '/uploads/doctors/thumb/' . $this-&gt;getObject()-&gt;getPhoto(),
          'is_image'  =&gt; true,
          'with_delete' =&gt; true,
          'delete_label'  =&gt; &quot;Удалить фото&quot;
        )
    );</p></div>
    ";i:2;s:4447:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="php" style="font-family:monospace;"><span style="color: #000088;">$this</span><span style="color: #339933;">-&gt;</span><span style="color: #004000;">validatorSchema</span><span style="color: #009900;">&#91;</span><span style="color: #0000ff;">'photo'</span><span style="color: #009900;">&#93;</span> <span style="color: #339933;">=</span> <span style="color: #000000; font-weight: bold;">new</span> sfValidatorFileThumb<span style="color: #009900;">&#40;</span>
      <span style="color: #990000;">array</span><span style="color: #009900;">&#40;</span>
        <span style="color: #0000ff;">'path'</span>        <span style="color: #339933;">=&gt;</span> sfConfig<span style="color: #339933;">::</span><span style="color: #004000;">get</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">'sf_upload_dir'</span><span style="color: #009900;">&#41;</span> <span style="color: #339933;">.</span> <span style="color: #009900; font-weight: bold;">DIRECTORY_SEPARATOR</span> <span style="color: #339933;">.</span> <span style="color: #0000ff;">'doctors'</span><span style="color: #339933;">,</span>
        <span style="color: #0000ff;">'required'</span>    <span style="color: #339933;">=&gt;</span> <span style="color: #009900; font-weight: bold;">false</span><span style="color: #339933;">,</span>
        <span style="color: #0000ff;">'mime_types'</span>  <span style="color: #339933;">=&gt;</span> <span style="color: #0000ff;">'web_images'</span><span style="color: #339933;">,</span>
        <span style="color: #666666; font-style: italic;">// Part below concerning a thumbnail</span>
        <span style="color: #0000ff;">'with_thumb'</span>  <span style="color: #339933;">=&gt;</span> <span style="color: #009900; font-weight: bold;">true</span><span style="color: #339933;">,</span>
        <span style="color: #0000ff;">'thumb_path'</span>  <span style="color: #339933;">=&gt;</span> sfConfig<span style="color: #339933;">::</span><span style="color: #004000;">get</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">'sf_upload_dir'</span><span style="color: #009900;">&#41;</span> <span style="color: #339933;">.</span> <span style="color: #009900; font-weight: bold;">DIRECTORY_SEPARATOR</span> <span style="color: #339933;">.</span> <span style="color: #0000ff;">'doctors/thumb'</span><span style="color: #339933;">,</span>
        <span style="color: #0000ff;">'thumb_scale'</span> <span style="color: #339933;">=&gt;</span> <span style="color: #009900; font-weight: bold;">true</span><span style="color: #339933;">,</span>
        <span style="color: #0000ff;">'thumb_inflate'</span> <span style="color: #339933;">=&gt;</span> <span style="color: #009900; font-weight: bold;">true</span><span style="color: #339933;">,</span>
        <span style="color: #0000ff;">'thumb_quality'</span> <span style="color: #339933;">=&gt;</span> <span style="color: #cc66cc;">80</span><span style="color: #339933;">,</span> <span style="color: #666666; font-style: italic;">// must be in a range [0-100]</span>
        <span style="color: #0000ff;">'thumb_dimensions'</span>  <span style="color: #339933;">=&gt;</span> <span style="color: #990000;">array</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">'width'</span> <span style="color: #339933;">=&gt;</span> <span style="color: #cc66cc;">116</span><span style="color: #339933;">,</span> <span style="color: #0000ff;">'height'</span> <span style="color: #339933;">=&gt;</span> <span style="color: #cc66cc;">154</span><span style="color: #009900;">&#41;</span>
    <span style="color: #009900;">&#41;</span>
    <span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span></pre></td></tr></table><p class="theCode" style="display:none;">$this-&gt;validatorSchema['photo'] = new sfValidatorFileThumb(
      array(
        'path'        =&gt; sfConfig::get('sf_upload_dir') . DIRECTORY_SEPARATOR . 'doctors',
        'required'    =&gt; false,
        'mime_types'  =&gt; 'web_images',
        // Part below concerning a thumbnail
        'with_thumb'  =&gt; true,
        'thumb_path'  =&gt; sfConfig::get('sf_upload_dir') . DIRECTORY_SEPARATOR . 'doctors/thumb',
        'thumb_scale' =&gt; true,
        'thumb_inflate' =&gt; true,
        'thumb_quality' =&gt; 80, // must be in a range [0-100]
        'thumb_dimensions'  =&gt; array('width' =&gt; 116, 'height' =&gt; 154)
    )
    );</p></div>
    ";i:3;s:32393:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="php" style="font-family:monospace;"><span style="color: #000000; font-weight: bold;">class</span> sfValidatorFileThumb <span style="color: #000000; font-weight: bold;">extends</span> sfValidatorFile
    <span style="color: #009933; font-style: italic;">/**
    * Configures the current validator.
    *
    * @access protected
    *
    * @param array $options   An array of options
    * @param array $messages  An array of error messages
    */</span>
    <span style="color: #000000; font-weight: bold;">protected</span> <span style="color: #000000; font-weight: bold;">function</span> configure<span style="color: #009900;">&#40;</span><span style="color: #000088;">$options</span> <span style="color: #339933;">=</span> <span style="color: #990000;">array</span><span style="color: #009900;">&#40;</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">,</span> <span style="color: #000088;">$messages</span> <span style="color: #339933;">=</span> <span style="color: #990000;">array</span><span style="color: #009900;">&#40;</span><span style="color: #009900;">&#41;</span><span style="color: #009900;">&#41;</span>
    <span style="color: #009900;">&#123;</span>
    <span style="color: #666666; font-style: italic;">// First configure the parent object</span>
    parent<span style="color: #339933;">::</span><span style="color: #004000;">configure</span><span style="color: #009900;">&#40;</span><span style="color: #000088;">$options</span><span style="color: #339933;">,</span> <span style="color: #000088;">$messages</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
    &nbsp;
    <span style="color: #666666; font-style: italic;">// Add options</span>
    <span style="color: #000088;">$this</span><span style="color: #339933;">-&gt;</span><span style="color: #004000;">addOption</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">'with_thumb'</span><span style="color: #339933;">,</span> <span style="color: #990000;">isset</span><span style="color: #009900;">&#40;</span><span style="color: #000088;">$options</span><span style="color: #009900;">&#91;</span><span style="color: #0000ff;">'with_thumb'</span><span style="color: #009900;">&#93;</span><span style="color: #009900;">&#41;</span> ? <span style="color: #000088;">$options</span><span style="color: #009900;">&#91;</span><span style="color: #0000ff;">'with_thumb'</span><span style="color: #009900;">&#93;</span> <span style="color: #339933;">:</span> <span style="color: #009900; font-weight: bold;">false</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
    <span style="color: #000088;">$this</span><span style="color: #339933;">-&gt;</span><span style="color: #004000;">addOption</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">'thumb_path'</span><span style="color: #339933;">,</span> <span style="color: #990000;">isset</span><span style="color: #009900;">&#40;</span><span style="color: #000088;">$options</span><span style="color: #009900;">&#91;</span><span style="color: #0000ff;">'thumb_path'</span><span style="color: #009900;">&#93;</span><span style="color: #009900;">&#41;</span> ? <span style="color: #000088;">$options</span><span style="color: #009900;">&#91;</span><span style="color: #0000ff;">'thumb_path'</span><span style="color: #009900;">&#93;</span> <span style="color: #339933;">:</span> sfConfig<span style="color: #339933;">::</span><span style="color: #004000;">get</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">'sf_upload_dir'</span><span style="color: #009900;">&#41;</span> <span style="color: #339933;">.</span> <span style="color: #009900; font-weight: bold;">DIRECTORY_SEPARATOR</span> <span style="color: #339933;">.</span> <span style="color: #0000ff;">'assets'</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
    <span style="color: #000088;">$this</span><span style="color: #339933;">-&gt;</span><span style="color: #004000;">addOption</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">'thumb_dimensions'</span><span style="color: #339933;">,</span> <span style="color: #990000;">isset</span><span style="color: #009900;">&#40;</span><span style="color: #000088;">$options</span><span style="color: #009900;">&#91;</span><span style="color: #0000ff;">'thumb_dimensions'</span><span style="color: #009900;">&#93;</span><span style="color: #009900;">&#41;</span> ? <span style="color: #000088;">$options</span><span style="color: #009900;">&#91;</span><span style="color: #0000ff;">'thumb_dimensions'</span><span style="color: #009900;">&#93;</span> <span style="color: #339933;">:</span> <span style="color: #009900; font-weight: bold;">null</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
    <span style="color: #000088;">$this</span><span style="color: #339933;">-&gt;</span><span style="color: #004000;">addOption</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">'thumb_scale'</span><span style="color: #339933;">,</span> <span style="color: #990000;">isset</span><span style="color: #009900;">&#40;</span><span style="color: #000088;">$options</span><span style="color: #009900;">&#91;</span><span style="color: #0000ff;">'thumb_scale'</span><span style="color: #009900;">&#93;</span><span style="color: #009900;">&#41;</span> ? <span style="color: #000088;">$options</span><span style="color: #009900;">&#91;</span><span style="color: #0000ff;">'thumb_scale'</span><span style="color: #009900;">&#93;</span> <span style="color: #339933;">:</span> <span style="color: #009900; font-weight: bold;">false</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
    <span style="color: #000088;">$this</span><span style="color: #339933;">-&gt;</span><span style="color: #004000;">addOption</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">'thumb_inflate'</span><span style="color: #339933;">,</span> <span style="color: #990000;">isset</span><span style="color: #009900;">&#40;</span><span style="color: #000088;">$options</span><span style="color: #009900;">&#91;</span><span style="color: #0000ff;">'thumb_inflate'</span><span style="color: #009900;">&#93;</span><span style="color: #009900;">&#41;</span> ? <span style="color: #000088;">$options</span><span style="color: #009900;">&#91;</span><span style="color: #0000ff;">'thumb_inflate'</span><span style="color: #009900;">&#93;</span> <span style="color: #339933;">:</span> <span style="color: #009900; font-weight: bold;">false</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
    <span style="color: #000088;">$this</span><span style="color: #339933;">-&gt;</span><span style="color: #004000;">addOption</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">'thumb_quality'</span><span style="color: #339933;">,</span> <span style="color: #990000;">isset</span><span style="color: #009900;">&#40;</span><span style="color: #000088;">$options</span><span style="color: #009900;">&#91;</span><span style="color: #0000ff;">'thumb_quality'</span><span style="color: #009900;">&#93;</span><span style="color: #009900;">&#41;</span> ? <span style="color: #000088;">$options</span><span style="color: #009900;">&#91;</span><span style="color: #0000ff;">'thumb_quality'</span><span style="color: #009900;">&#93;</span> <span style="color: #339933;">:</span> <span style="color: #009900; font-weight: bold;">false</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
    &nbsp;
    <span style="color: #666666; font-style: italic;">// Add messages:</span>
    <span style="color: #666666; font-style: italic;">//    $this-&gt;addMessage('thumb_path', 'Path does not exists or directory is not writeble!');</span>
    &nbsp;
    <span style="color: #666666; font-style: italic;">// Add our custom class that will handle uploaded file</span>
    <span style="color: #000088;">$this</span><span style="color: #339933;">-&gt;</span><span style="color: #004000;">addOption</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">'validated_file_class'</span><span style="color: #339933;">,</span> <span style="color: #0000ff;">'withThumbnailValidatedFile'</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
    <span style="color: #009900;">&#125;</span>
    &nbsp;
    <span style="color: #009933; font-style: italic;">/**
    * Make validation for a file
    *
    * @access protected
    * @author Roman Dushko
    *
    * @see sfValidatorFile
    */</span>
    <span style="color: #000000; font-weight: bold;">protected</span> <span style="color: #000000; font-weight: bold;">function</span> doClean<span style="color: #009900;">&#40;</span><span style="color: #000088;">$value</span><span style="color: #009900;">&#41;</span>
    <span style="color: #009900;">&#123;</span>
    <span style="color: #666666; font-style: italic;">// Validated file object</span>
    <span style="color: #000088;">$validatedFileObj</span> <span style="color: #339933;">=</span> parent<span style="color: #339933;">::</span><span style="color: #004000;">doClean</span><span style="color: #009900;">&#40;</span><span style="color: #000088;">$value</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
    &nbsp;
    <span style="color: #b1b100;">if</span> <span style="color: #009900;">&#40;</span><span style="color: #000088;">$this</span><span style="color: #339933;">-&gt;</span><span style="color: #004000;">getOption</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">'with_thumb'</span><span style="color: #009900;">&#41;</span><span style="color: #009900;">&#41;</span>
    <span style="color: #009900;">&#123;</span>
    <span style="color: #666666; font-style: italic;">// Check if plugin sfThumpnailPlugin exists</span>
    <span style="color: #b1b100;">if</span> <span style="color: #009900;">&#40;</span><span style="color: #339933;">!</span><span style="color: #990000;">class_exists</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">'sfThumbnail'</span><span style="color: #009900;">&#41;</span><span style="color: #009900;">&#41;</span> <span style="color: #666666; font-style: italic;">// @todo: Could we not to check if plugin is enabled? Or should we check?</span>
    <span style="color: #009900;">&#123;</span>
    <span style="color: #b1b100;">throw</span> <span style="color: #000000; font-weight: bold;">new</span> Exception<span style="color: #009900;">&#40;</span><span style="color: #990000;">sprintf</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">'A class for making the thumbnails &quot;%s&quot; is not found'</span><span style="color: #339933;">,</span> <span style="color: #0000ff;">'sfThumbnail'</span><span style="color: #009900;">&#41;</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
    <span style="color: #009900;">&#125;</span>
    &nbsp;
    <span style="color: #666666; font-style: italic;">// Check if a path where thumbnail will be stored is provided</span>
    <span style="color: #b1b100;">if</span><span style="color: #009900;">&#40;</span><span style="color: #009900; font-weight: bold;">null</span> <span style="color: #339933;">===</span> <span style="color: #000088;">$this</span><span style="color: #339933;">-&gt;</span><span style="color: #004000;">getOption</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">'thumb_path'</span><span style="color: #009900;">&#41;</span><span style="color: #009900;">&#41;</span>
    <span style="color: #009900;">&#123;</span>
    <span style="color: #b1b100;">throw</span> <span style="color: #000000; font-weight: bold;">new</span> Exception<span style="color: #009900;">&#40;</span><span style="color: #0000ff;">'Path to thumbnails is not provided!'</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
    <span style="color: #009900;">&#125;</span>
    &nbsp;
    <span style="color: #666666; font-style: italic;">// Set needed validated file properties</span>
    <span style="color: #000088;">$validatedFileObj</span><span style="color: #339933;">-&gt;</span><span style="color: #004000;">setWithThumbnail</span><span style="color: #009900;">&#40;</span><span style="color: #009900; font-weight: bold;">true</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
    <span style="color: #000088;">$validatedFileObj</span><span style="color: #339933;">-&gt;</span><span style="color: #004000;">setThumbProperties</span><span style="color: #009900;">&#40;</span>
    <span style="color: #990000;">array</span><span style="color: #009900;">&#40;</span>
    <span style="color: #0000ff;">'thumb_path'</span> <span style="color: #339933;">=&gt;</span> <span style="color: #000088;">$this</span><span style="color: #339933;">-&gt;</span><span style="color: #004000;">getOption</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">'thumb_path'</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">,</span>
    <span style="color: #0000ff;">'thumb_dimensions'</span> <span style="color: #339933;">=&gt;</span> <span style="color: #000088;">$this</span><span style="color: #339933;">-&gt;</span><span style="color: #004000;">getOption</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">'thumb_dimensions'</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">,</span>
    <span style="color: #0000ff;">'thumb_scale'</span> <span style="color: #339933;">=&gt;</span> <span style="color: #000088;">$this</span><span style="color: #339933;">-&gt;</span><span style="color: #004000;">getOption</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">'thumb_scale'</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">,</span>
    <span style="color: #0000ff;">'thumb_inflate'</span> <span style="color: #339933;">=&gt;</span> <span style="color: #000088;">$this</span><span style="color: #339933;">-&gt;</span><span style="color: #004000;">getOption</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">'thumb_inflate'</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">,</span>
    <span style="color: #0000ff;">'thumb_quality'</span> <span style="color: #339933;">=&gt;</span> <span style="color: #000088;">$this</span><span style="color: #339933;">-&gt;</span><span style="color: #004000;">getOption</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">'thumb_quality'</span><span style="color: #009900;">&#41;</span>
    <span style="color: #009900;">&#41;</span>
    <span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
    <span style="color: #009900;">&#125;</span>
    &nbsp;
    <span style="color: #b1b100;">return</span> <span style="color: #000088;">$validatedFileObj</span><span style="color: #339933;">;</span>
    <span style="color: #009900;">&#125;</span>
    &nbsp;
    <span style="color: #009900;">&#125;</span>
    &nbsp;
    <span style="color: #000000; font-weight: bold;">class</span> withThumbnailValidatedFile <span style="color: #000000; font-weight: bold;">extends</span> sfValidatedFile
    <span style="color: #009900;">&#123;</span>
    <span style="color: #000000; font-weight: bold;">protected</span> <span style="color: #000088;">$withTumbnail</span> <span style="color: #339933;">=</span> <span style="color: #009900; font-weight: bold;">false</span><span style="color: #339933;">;</span>
    <span style="color: #000000; font-weight: bold;">protected</span> <span style="color: #000088;">$thumbProperties</span> <span style="color: #339933;">=</span> <span style="color: #990000;">array</span><span style="color: #009900;">&#40;</span>
    <span style="color: #0000ff;">'thumb_path'</span> <span style="color: #339933;">=&gt;</span> <span style="color: #009900; font-weight: bold;">null</span><span style="color: #339933;">,</span>
    <span style="color: #0000ff;">'thumb_dimensions'</span> <span style="color: #339933;">=&gt;</span> <span style="color: #009900; font-weight: bold;">null</span><span style="color: #339933;">,</span>
    <span style="color: #0000ff;">'thumb_scale'</span> <span style="color: #339933;">=&gt;</span> <span style="color: #009900; font-weight: bold;">false</span><span style="color: #339933;">,</span>
    <span style="color: #0000ff;">'thumb_inflate'</span> <span style="color: #339933;">=&gt;</span> <span style="color: #009900; font-weight: bold;">false</span><span style="color: #339933;">,</span>
    <span style="color: #0000ff;">'thumb_quality'</span> <span style="color: #339933;">=&gt;</span> <span style="color: #009900; font-weight: bold;">null</span>
    <span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
    &nbsp;
    <span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">function</span> save<span style="color: #009900;">&#40;</span><span style="color: #000088;">$file</span> <span style="color: #339933;">=</span> <span style="color: #009900; font-weight: bold;">null</span><span style="color: #339933;">,</span> <span style="color: #000088;">$fileMode</span> <span style="color: #339933;">=</span> <span style="color: #208080;">0666</span><span style="color: #339933;">,</span> <span style="color: #000088;">$create</span> <span style="color: #339933;">=</span> <span style="color: #009900; font-weight: bold;">true</span><span style="color: #339933;">,</span> <span style="color: #000088;">$dirMode</span> <span style="color: #339933;">=</span> <span style="color: #208080;">0777</span><span style="color: #009900;">&#41;</span>
    <span style="color: #009900;">&#123;</span>
    <span style="color: #666666; font-style: italic;">// Save original image</span>
    <span style="color: #000088;">$savedFile</span> <span style="color: #339933;">=</span> parent<span style="color: #339933;">::</span><span style="color: #004000;">save</span><span style="color: #009900;">&#40;</span><span style="color: #000088;">$file</span><span style="color: #339933;">,</span> <span style="color: #000088;">$fileMode</span><span style="color: #339933;">,</span> <span style="color: #000088;">$create</span><span style="color: #339933;">,</span> <span style="color: #000088;">$dirMode</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
    &nbsp;
    <span style="color: #666666; font-style: italic;">// Check if we need to upload a thumbnail</span>
    <span style="color: #b1b100;">if</span> <span style="color: #009900;">&#40;</span><span style="color: #000088;">$this</span><span style="color: #339933;">-&gt;</span><span style="color: #004000;">withTumbnail</span><span style="color: #009900;">&#41;</span>
    <span style="color: #009900;">&#123;</span>
    <span style="color: #666666; font-style: italic;">// Get dimension for thumbnail</span>
    <span style="color: #000088;">$thumbDimensions</span> <span style="color: #339933;">=</span> <span style="color: #000088;">$this</span><span style="color: #339933;">-&gt;</span><span style="color: #004000;">getThumbProperty</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">'thumb_dimensions'</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
    <span style="color: #b1b100;">if</span> <span style="color: #009900;">&#40;</span><span style="color: #000088;">$thumbDimensions</span><span style="color: #009900;">&#41;</span>
    <span style="color: #009900;">&#123;</span>
    <span style="color: #000088;">$thumbWidth</span> <span style="color: #339933;">=</span> <span style="color: #990000;">isset</span><span style="color: #009900;">&#40;</span><span style="color: #000088;">$thumbDimensions</span><span style="color: #009900;">&#91;</span><span style="color: #0000ff;">'width'</span><span style="color: #009900;">&#93;</span><span style="color: #009900;">&#41;</span> ? <span style="color: #000088;">$thumbDimensions</span><span style="color: #009900;">&#91;</span><span style="color: #0000ff;">'width'</span><span style="color: #009900;">&#93;</span> <span style="color: #339933;">:</span> <span style="color: #009900; font-weight: bold;">null</span><span style="color: #339933;">;</span>
    <span style="color: #000088;">$thumbHeight</span> <span style="color: #339933;">=</span> <span style="color: #990000;">isset</span><span style="color: #009900;">&#40;</span><span style="color: #000088;">$thumbDimensions</span><span style="color: #009900;">&#91;</span><span style="color: #0000ff;">'height'</span><span style="color: #009900;">&#93;</span><span style="color: #009900;">&#41;</span> ? <span style="color: #000088;">$thumbDimensions</span><span style="color: #009900;">&#91;</span><span style="color: #0000ff;">'height'</span><span style="color: #009900;">&#93;</span> <span style="color: #339933;">:</span> <span style="color: #009900; font-weight: bold;">null</span><span style="color: #339933;">;</span>
    <span style="color: #009900;">&#125;</span>
    &nbsp;
    <span style="color: #666666; font-style: italic;">// Create instance of thumbnailer</span>
    <span style="color: #009933; font-style: italic;">/**
    * @todo: make it possible to define 'adapterClass' for sfThumbnail (and it's options) in factories.yml
    */</span>
    <span style="color: #000088;">$thumnailer</span> <span style="color: #339933;">=</span> <span style="color: #000000; font-weight: bold;">new</span> sfThumbnail<span style="color: #009900;">&#40;</span>
    <span style="color: #000088;">$thumbWidth</span><span style="color: #339933;">,</span>
    <span style="color: #000088;">$thumbHeight</span><span style="color: #339933;">,</span>
    <span style="color: #000088;">$this</span><span style="color: #339933;">-&gt;</span><span style="color: #004000;">getThumbProperty</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">'thumb_scale'</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">,</span>
    <span style="color: #000088;">$this</span><span style="color: #339933;">-&gt;</span><span style="color: #004000;">getThumbProperty</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">'thumb_inflate'</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">,</span>
    <span style="color: #000088;">$this</span><span style="color: #339933;">-&gt;</span><span style="color: #004000;">getThumbProperty</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">'thumb_quality'</span><span style="color: #009900;">&#41;</span>
    <span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
    <span style="color: #666666; font-style: italic;">// Load saved file</span>
    <span style="color: #000088;">$thumnailer</span><span style="color: #339933;">-&gt;</span><span style="color: #004000;">loadFile</span><span style="color: #009900;">&#40;</span><span style="color: #000088;">$this</span><span style="color: #339933;">-&gt;</span><span style="color: #004000;">getSavedName</span><span style="color: #009900;">&#40;</span><span style="color: #009900;">&#41;</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
    <span style="color: #666666; font-style: italic;">// Save a thumbnail</span>
    <span style="color: #000088;">$thumnailer</span><span style="color: #339933;">-&gt;</span><span style="color: #004000;">save</span><span style="color: #009900;">&#40;</span><span style="color: #000088;">$this</span><span style="color: #339933;">-&gt;</span><span style="color: #004000;">getThumbProperty</span><span style="color: #009900;">&#40;</span><span style="color: #0000ff;">'thumb_path'</span><span style="color: #009900;">&#41;</span> <span style="color: #339933;">.</span> <span style="color: #009900; font-weight: bold;">DIRECTORY_SEPARATOR</span> <span style="color: #339933;">.</span> <span style="color: #990000;">basename</span><span style="color: #009900;">&#40;</span><span style="color: #000088;">$this</span><span style="color: #339933;">-&gt;</span><span style="color: #004000;">getSavedName</span><span style="color: #009900;">&#40;</span><span style="color: #009900;">&#41;</span><span style="color: #009900;">&#41;</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span>
    <span style="color: #009900;">&#125;</span>
    &nbsp;
    <span style="color: #b1b100;">return</span> <span style="color: #000088;">$savedFile</span><span style="color: #339933;">;</span>
    <span style="color: #009900;">&#125;</span>
    &nbsp;
    <span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">function</span> setWithThumbnail<span style="color: #009900;">&#40;</span><span style="color: #000088;">$with_thumb</span> <span style="color: #339933;">=</span> <span style="color: #009900; font-weight: bold;">false</span><span style="color: #009900;">&#41;</span>
    <span style="color: #009900;">&#123;</span>
    <span style="color: #000088;">$this</span><span style="color: #339933;">-&gt;</span><span style="color: #004000;">withTumbnail</span> <span style="color: #339933;">=</span> <span style="color: #000088;">$with_thumb</span><span style="color: #339933;">;</span>
    <span style="color: #009900;">&#125;</span>
    &nbsp;
    <span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">function</span> getWithThumbnail<span style="color: #009900;">&#40;</span><span style="color: #009900;">&#41;</span>
    <span style="color: #009900;">&#123;</span>
    <span style="color: #b1b100;">return</span> <span style="color: #000088;">$this</span><span style="color: #339933;">-&gt;</span><span style="color: #004000;">withTumbnail</span><span style="color: #339933;">;</span>
    <span style="color: #009900;">&#125;</span>
    &nbsp;
    <span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">function</span> setThumbProperties<span style="color: #009900;">&#40;</span><span style="color: #000088;">$properties</span><span style="color: #009900;">&#41;</span>
    <span style="color: #009900;">&#123;</span>
    <span style="color: #000088;">$this</span><span style="color: #339933;">-&gt;</span><span style="color: #004000;">thumbProperties</span> <span style="color: #339933;">=</span> <span style="color: #000088;">$properties</span><span style="color: #339933;">;</span>
    <span style="color: #009900;">&#125;</span>
    &nbsp;
    <span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">function</span> getThumbProperties<span style="color: #009900;">&#40;</span><span style="color: #009900;">&#41;</span>
    <span style="color: #009900;">&#123;</span>
    <span style="color: #b1b100;">return</span> <span style="color: #000088;">$this</span><span style="color: #339933;">-&gt;</span><span style="color: #004000;">thumbProperties</span><span style="color: #339933;">;</span>
    <span style="color: #009900;">&#125;</span>
    &nbsp;
    <span style="color: #000000; font-weight: bold;">public</span> <span style="color: #000000; font-weight: bold;">function</span> getThumbProperty<span style="color: #009900;">&#40;</span><span style="color: #000088;">$propName</span><span style="color: #009900;">&#41;</span>
    <span style="color: #009900;">&#123;</span>
    <span style="color: #b1b100;">return</span> <span style="color: #000088;">$this</span><span style="color: #339933;">-&gt;</span><span style="color: #004000;">thumbProperties</span><span style="color: #009900;">&#91;</span><span style="color: #000088;">$propName</span><span style="color: #009900;">&#93;</span><span style="color: #339933;">;</span>
    <span style="color: #009900;">&#125;</span>
    &nbsp;
    <span style="color: #009900;">&#125;</span></pre></td></tr></table><p class="theCode" style="display:none;">class sfValidatorFileThumb extends sfValidatorFile
    /**
    * Configures the current validator.
    *
    * @access protected
    *
    * @param array $options   An array of options
    * @param array $messages  An array of error messages
    */
    protected function configure($options = array(), $messages = array())
    {
    // First configure the parent object
    parent::configure($options, $messages);
    
    // Add options
    $this-&gt;addOption('with_thumb', isset($options['with_thumb']) ? $options['with_thumb'] : false);
    $this-&gt;addOption('thumb_path', isset($options['thumb_path']) ? $options['thumb_path'] : sfConfig::get('sf_upload_dir') . DIRECTORY_SEPARATOR . 'assets');
    $this-&gt;addOption('thumb_dimensions', isset($options['thumb_dimensions']) ? $options['thumb_dimensions'] : null);
    $this-&gt;addOption('thumb_scale', isset($options['thumb_scale']) ? $options['thumb_scale'] : false);
    $this-&gt;addOption('thumb_inflate', isset($options['thumb_inflate']) ? $options['thumb_inflate'] : false);
    $this-&gt;addOption('thumb_quality', isset($options['thumb_quality']) ? $options['thumb_quality'] : false);
    
    // Add messages:
    //    $this-&gt;addMessage('thumb_path', 'Path does not exists or directory is not writeble!');
    
    // Add our custom class that will handle uploaded file
    $this-&gt;addOption('validated_file_class', 'withThumbnailValidatedFile');
    }
    
    /**
    * Make validation for a file
    *
    * @access protected
    * @author Roman Dushko
    *
    * @see sfValidatorFile
    */
    protected function doClean($value)
    {
    // Validated file object
    $validatedFileObj = parent::doClean($value);
    
    if ($this-&gt;getOption('with_thumb'))
    {
    // Check if plugin sfThumpnailPlugin exists
    if (!class_exists('sfThumbnail')) // @todo: Could we not to check if plugin is enabled? Or should we check?
    {
    throw new Exception(sprintf('A class for making the thumbnails &quot;%s&quot; is not found', 'sfThumbnail'));
    }
    
    // Check if a path where thumbnail will be stored is provided
    if(null === $this-&gt;getOption('thumb_path'))
    {
    throw new Exception('Path to thumbnails is not provided!');
    }
    
    // Set needed validated file properties
    $validatedFileObj-&gt;setWithThumbnail(true);
    $validatedFileObj-&gt;setThumbProperties(
    array(
    'thumb_path' =&gt; $this-&gt;getOption('thumb_path'),
    'thumb_dimensions' =&gt; $this-&gt;getOption('thumb_dimensions'),
    'thumb_scale' =&gt; $this-&gt;getOption('thumb_scale'),
    'thumb_inflate' =&gt; $this-&gt;getOption('thumb_inflate'),
    'thumb_quality' =&gt; $this-&gt;getOption('thumb_quality')
    )
    );
    }
    
    return $validatedFileObj;
    }
    
    }
    
    class withThumbnailValidatedFile extends sfValidatedFile
    {
    protected $withTumbnail = false;
    protected $thumbProperties = array(
    'thumb_path' =&gt; null,
    'thumb_dimensions' =&gt; null,
    'thumb_scale' =&gt; false,
    'thumb_inflate' =&gt; false,
    'thumb_quality' =&gt; null
    );
    
    public function save($file = null, $fileMode = 0666, $create = true, $dirMode = 0777)
    {
    // Save original image
    $savedFile = parent::save($file, $fileMode, $create, $dirMode);
    
    // Check if we need to upload a thumbnail
    if ($this-&gt;withTumbnail)
    {
    // Get dimension for thumbnail
    $thumbDimensions = $this-&gt;getThumbProperty('thumb_dimensions');
    if ($thumbDimensions)
    {
    $thumbWidth = isset($thumbDimensions['width']) ? $thumbDimensions['width'] : null;
    $thumbHeight = isset($thumbDimensions['height']) ? $thumbDimensions['height'] : null;
    }
    
    // Create instance of thumbnailer
    /**
    * @todo: make it possible to define 'adapterClass' for sfThumbnail (and it's options) in factories.yml
    */
    $thumnailer = new sfThumbnail(
    $thumbWidth,
    $thumbHeight,
    $this-&gt;getThumbProperty('thumb_scale'),
    $this-&gt;getThumbProperty('thumb_inflate'),
    $this-&gt;getThumbProperty('thumb_quality')
    );
    // Load saved file
    $thumnailer-&gt;loadFile($this-&gt;getSavedName());
    // Save a thumbnail
    $thumnailer-&gt;save($this-&gt;getThumbProperty('thumb_path') . DIRECTORY_SEPARATOR . basename($this-&gt;getSavedName()));
    }
    
    return $savedFile;
    }
    
    public function setWithThumbnail($with_thumb = false)
    {
    $this-&gt;withTumbnail = $with_thumb;
    }
    
    public function getWithThumbnail()
    {
    return $this-&gt;withTumbnail;
    }
    
    public function setThumbProperties($properties)
    {
    $this-&gt;thumbProperties = $properties;
    }
    
    public function getThumbProperties()
    {
    return $this-&gt;thumbProperties;
    }
    
    public function getThumbProperty($propName)
    {
    return $this-&gt;thumbProperties[$propName];
    }
    
    }</p></div>
    ";}
categories:
  - symfony
tags:
  - form
  - plugins
  - sfThumbnailPlugins
  - symfony
  - widget

---
В процессе разработки <a title="Portfolio" href="http://www.poli-klinika.com.ua/" target="_blank">одного веб-сайта</a> в админ-панели мне понадобилось реализовать возможность загрузки фотографии к создаваемой записи. Задача, само собой разумеется частая и востребованная. Так как разработку сайта на делал на основе фреймворка symfony, то решил первым делом порыскать среди готовых плагинов.

Поставленную задачу с успехом должен был решить плагин <a title="sfThumbnailPlugin" href="http://www.symfony-project.org/plugins/sfThumbnailPlugin" target="_blank">sfThumbnailPlugin.</a> В симфони (>=1.2), как известно, для загрузки файлов служит виджет sfWidgetFormInputFileEditable. Данный виджет представляет привычное поле выбора файла из файловой системы. За саму же загрузку файла на сервер отвечает валидатор для указанного виджета. Таким образом, задача для меня состояла в том, чтобы &#171;прикрутить&#187; плагин создания &#171;превьюшек&#187; к стандартному виджету.

После углубленного изучения жизненного пути файла в недрах виджетов и валидаторов symfony (от момента его выбора до загрузки на сервер) мне показалось самым логичным использовать функциональность sfThumbnailPlugin именно в валидаторе загружаемого файла. То-есть, после нажатия кнопки сохранения какой-либо записи загруженный файл передается на обработку собственноручно написаного валидатора. Свой файл валидатора я назвал **sfValidatorFileThumb** и поместил в папку lib/validators проекта.

Класс конфигурации формы выглядит следующим образом (_для примера_*):

<pre lang="PHP">//................................
public function configure()
{
  $this->widgetSchema['photo'] = new sfWidgetFormInputFileEditable(
    array(
      'file_src'  => '/uploads/doctors/thumb/' . $this->getObject()->getPhoto(),
      'is_image'  => true,
      'with_delete' => true,
      'delete_label'  => "Удалить фото"
    )
);</pre>

Валидатор под этот виджет:

<pre lang="PHP">$this->validatorSchema['photo'] = new sfValidatorFileThumb(
  array(
    'path'        => sfConfig::get('sf_upload_dir') . DIRECTORY_SEPARATOR . 'doctors',
    'required'    => false,
    'mime_types'  => 'web_images',
    // Part below concerning a thumbnail
    'with_thumb'  => true,
    'thumb_path'  => sfConfig::get('sf_upload_dir') . DIRECTORY_SEPARATOR . 'doctors/thumb',
    'thumb_scale' => true,
    'thumb_inflate' => true,
    'thumb_quality' => 80, // must be in a range [0-100]
    'thumb_dimensions'  => array('width' => 116, 'height' => 154)
)
);</pre>

Сам же файл валидатора имеет следующий код:

<pre lang="PHP">class sfValidatorFileThumb extends sfValidatorFile
/**
* Configures the current validator.
*
* @access protected
*
* @param array $options   An array of options
* @param array $messages  An array of error messages
*/
protected function configure($options = array(), $messages = array())
{
// First configure the parent object
parent::configure($options, $messages);

// Add options
$this->addOption('with_thumb', isset($options['with_thumb']) ? $options['with_thumb'] : false);
$this->addOption('thumb_path', isset($options['thumb_path']) ? $options['thumb_path'] : sfConfig::get('sf_upload_dir') . DIRECTORY_SEPARATOR . 'assets');
$this->addOption('thumb_dimensions', isset($options['thumb_dimensions']) ? $options['thumb_dimensions'] : null);
$this->addOption('thumb_scale', isset($options['thumb_scale']) ? $options['thumb_scale'] : false);
$this->addOption('thumb_inflate', isset($options['thumb_inflate']) ? $options['thumb_inflate'] : false);
$this->addOption('thumb_quality', isset($options['thumb_quality']) ? $options['thumb_quality'] : false);

// Add messages:
//    $this->addMessage('thumb_path', 'Path does not exists or directory is not writeble!');

// Add our custom class that will handle uploaded file
$this->addOption('validated_file_class', 'withThumbnailValidatedFile');
}

/**
* Make validation for a file
*
* @access protected
* @author Roman Dushko
*
* @see sfValidatorFile
*/
protected function doClean($value)
{
// Validated file object
$validatedFileObj = parent::doClean($value);

if ($this->getOption('with_thumb'))
{
// Check if plugin sfThumpnailPlugin exists
if (!class_exists('sfThumbnail')) // @todo: Could we not to check if plugin is enabled? Or should we check?
{
throw new Exception(sprintf('A class for making the thumbnails "%s" is not found', 'sfThumbnail'));
}

// Check if a path where thumbnail will be stored is provided
if(null === $this->getOption('thumb_path'))
{
throw new Exception('Path to thumbnails is not provided!');
}

// Set needed validated file properties
$validatedFileObj->setWithThumbnail(true);
$validatedFileObj->setThumbProperties(
array(
'thumb_path' => $this->getOption('thumb_path'),
'thumb_dimensions' => $this->getOption('thumb_dimensions'),
'thumb_scale' => $this->getOption('thumb_scale'),
'thumb_inflate' => $this->getOption('thumb_inflate'),
'thumb_quality' => $this->getOption('thumb_quality')
)
);
}

return $validatedFileObj;
}

}

class withThumbnailValidatedFile extends sfValidatedFile
{
protected $withTumbnail = false;
protected $thumbProperties = array(
'thumb_path' => null,
'thumb_dimensions' => null,
'thumb_scale' => false,
'thumb_inflate' => false,
'thumb_quality' => null
);

public function save($file = null, $fileMode = 0666, $create = true, $dirMode = 0777)
{
// Save original image
$savedFile = parent::save($file, $fileMode, $create, $dirMode);

// Check if we need to upload a thumbnail
if ($this->withTumbnail)
{
// Get dimension for thumbnail
$thumbDimensions = $this->getThumbProperty('thumb_dimensions');
if ($thumbDimensions)
{
$thumbWidth = isset($thumbDimensions['width']) ? $thumbDimensions['width'] : null;
$thumbHeight = isset($thumbDimensions['height']) ? $thumbDimensions['height'] : null;
}

// Create instance of thumbnailer
/**
* @todo: make it possible to define 'adapterClass' for sfThumbnail (and it's options) in factories.yml
*/
$thumnailer = new sfThumbnail(
$thumbWidth,
$thumbHeight,
$this->getThumbProperty('thumb_scale'),
$this->getThumbProperty('thumb_inflate'),
$this->getThumbProperty('thumb_quality')
);
// Load saved file
$thumnailer->loadFile($this->getSavedName());
// Save a thumbnail
$thumnailer->save($this->getThumbProperty('thumb_path') . DIRECTORY_SEPARATOR . basename($this->getSavedName()));
}

return $savedFile;
}

public function setWithThumbnail($with_thumb = false)
{
$this->withTumbnail = $with_thumb;
}

public function getWithThumbnail()
{
return $this->withTumbnail;
}

public function setThumbProperties($properties)
{
$this->thumbProperties = $properties;
}

public function getThumbProperties()
{
return $this->thumbProperties;
}

public function getThumbProperty($propName)
{
return $this->thumbProperties[$propName];
}

}
</pre>

Собственно, за создание &#171;превьюшки&#187; и загрузки файлов на сервер отвечает класс withThumbnailValidatedFile, расширяющий sfValidatedFile, а именно его метод save, переопределяющий родительский метод.

В самом классе валидатора файла-превьюшки мы указываем, кто будет отвечать за обработку провалидированного файла:

`$this->addOption('validated_file_class', 'withThumbnailValidatedFile');`

Вот и всё! Естественно возможны дальнейшие улучшения, но для меня данное решение оказалось подходящим. При выборе файла и сохранении записи мы делаем две операции:

  1. Сохраняем оригинальное изображение
  2. Создаем и сохраняем thumbnail с помощью &#171;допиленного&#187; валидатора.

<div id="_mcePaste" style="position: absolute; left: -10000px; top: 0px; width: 1px; height: 1px; overflow: hidden;">
  sfThumbnailPlugin
</div>