---
title: Having error while trying use jqFileUpload with RequireJS?
author: admin
type: post
date: 2014-05-16T10:18:44+00:00
url: /2014/05/having-error-while-trying-use-jqfileupload-with-requirejs/
wp-syntax-cache-content:
  - |
    a:2:{i:1;s:9646:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="javascript" style="font-family:monospace;">require.<span style="color: #660066;">config</span><span style="color: #009900;">&#40;</span><span style="color: #009900;">&#123;</span>
      paths<span style="color: #339933;">:</span> <span style="color: #009900;">&#123;</span>
        <span style="color: #3366CC;">'semantic'</span><span style="color: #339933;">:</span> <span style="color: #3366CC;">'../../bower_components/semantic-ui/build/packaged/javascript/semantic.min'</span><span style="color: #339933;">,</span>
        <span style="color: #3366CC;">'jquery'</span><span style="color: #339933;">:</span> <span style="color: #3366CC;">'../../bower_components/jquery/dist/jquery.min'</span><span style="color: #339933;">,</span>
        <span style="color: #3366CC;">'domReady'</span><span style="color: #339933;">:</span> <span style="color: #3366CC;">'../../bower_components/requirejs-domready/domReady'</span><span style="color: #339933;">,</span>
        <span style="color: #3366CC;">'angular'</span><span style="color: #339933;">:</span> <span style="color: #3366CC;">'../../bower_components/angular/angular.min'</span><span style="color: #339933;">,</span>
        <span style="color: #3366CC;">'angular-route'</span><span style="color: #339933;">:</span> <span style="color: #3366CC;">'../../bower_components/angular-route/angular-route.min'</span><span style="color: #339933;">,</span>
        <span style="color: #3366CC;">'angular-resource'</span><span style="color: #339933;">:</span> <span style="color: #3366CC;">'../../bower_components/angular-resource/angular-resource.min'</span><span style="color: #339933;">,</span>
        <span style="color: #3366CC;">'jquery.fileupload'</span><span style="color: #339933;">:</span> <span style="color: #3366CC;">'../../bower_components/angular-jqfile-upload/js/jquery.fileupload'</span><span style="color: #339933;">,</span>
        <span style="color: #3366CC;">'jquery.fileupload-angular'</span><span style="color: #339933;">:</span> <span style="color: #3366CC;">'../../bower_components/angular-jqfile-upload/js/jquery.fileupload-angular'</span><span style="color: #339933;">,</span>
        <span style="color: #3366CC;">'jquery.ui.widget'</span><span style="color: #339933;">:</span> <span style="color: #3366CC;">'../../bower_components/angular-jqfile-upload/js/vendor/jquery.ui.widget'</span><span style="color: #339933;">,</span>
        <span style="color: #3366CC;">'jquery.fileupload-image'</span><span style="color: #339933;">:</span> <span style="color: #3366CC;">'../../bower_components/angular-jqfile-upload/js/jquery.fileupload-image'</span><span style="color: #339933;">,</span>
        <span style="color: #3366CC;">'jquery.fileupload-process'</span><span style="color: #339933;">:</span> <span style="color: #3366CC;">'../../bower_components/angular-jqfile-upload/js/jquery.fileupload-process'</span><span style="color: #339933;">,</span>
        <span style="color: #3366CC;">'jquery.fileupload-audio'</span><span style="color: #339933;">:</span> <span style="color: #3366CC;">'../../bower_components/angular-jqfile-upload/js/jquery.fileupload-audio'</span><span style="color: #339933;">,</span>
        <span style="color: #3366CC;">'jquery.fileupload-video'</span><span style="color: #339933;">:</span> <span style="color: #3366CC;">'../../bower_components/angular-jqfile-upload/js/jquery.fileupload-video'</span><span style="color: #339933;">,</span>
        <span style="color: #3366CC;">'jquery.fileupload-validate'</span><span style="color: #339933;">:</span> <span style="color: #3366CC;">'../../bower_components/angular-jqfile-upload/js/jquery.fileupload-validate'</span><span style="color: #339933;">,</span>
        <span style="color: #3366CC;">'jquery.fileupload-ui'</span><span style="color: #339933;">:</span> <span style="color: #3366CC;">'../../bower_components/angular-jqfile-upload/js/jquery.fileupload-ui'</span><span style="color: #339933;">,</span>
        <span style="color: #3366CC;">'jquery.iframe-transport'</span><span style="color: #339933;">:</span> <span style="color: #3366CC;">'../../bower_components/angular-jqfile-upload/js/jquery.iframe-transport'</span><span style="color: #339933;">,</span>
        <span style="color: #3366CC;">'canvas-to-blob'</span><span style="color: #339933;">:</span> <span style="color: #3366CC;">'../../bower_components/blueimp-canvas-to-blob/js/canvas-to-blob.min'</span><span style="color: #339933;">,</span>
        <span style="color: #3366CC;">'load-image'</span><span style="color: #339933;">:</span> <span style="color: #3366CC;">'../../bower_components/blueimp-load-image/js/load-image.min'</span><span style="color: #339933;">,</span>
        <span style="color: #3366CC;">'load-image-exif'</span><span style="color: #339933;">:</span> <span style="color: #3366CC;">'../../bower_components/blueimp-load-image/js/load-image-exif'</span><span style="color: #339933;">,</span>
        <span style="color: #3366CC;">'load-image-ios'</span><span style="color: #339933;">:</span> <span style="color: #3366CC;">'../../bower_components/blueimp-load-image/js/load-image-ios'</span><span style="color: #339933;">,</span>
        <span style="color: #3366CC;">'load-image-meta'</span><span style="color: #339933;">:</span> <span style="color: #3366CC;">'../../bower_components/blueimp-load-image/js/load-image-meta'</span><span style="color: #339933;">,</span>
        <span style="color: #3366CC;">'load-image-orientation'</span><span style="color: #339933;">:</span> <span style="color: #3366CC;">'../../bower_components/blueimp-load-image/js/load-image-orientation'</span>
      <span style="color: #009900;">&#125;</span><span style="color: #339933;">,</span>
    &nbsp;
      <span style="color: #006600; font-style: italic;">// angular does not support AMD out of the box, put it in shim</span>
      shim<span style="color: #339933;">:</span> <span style="color: #009900;">&#123;</span>
    	  <span style="color: #3366CC;">'semantic'</span><span style="color: #339933;">:</span> <span style="color: #009900;">&#123;</span>
    		  exports<span style="color: #339933;">:</span> <span style="color: #3366CC;">'semantic'</span><span style="color: #339933;">,</span>
    		  deps<span style="color: #339933;">:</span> <span style="color: #009900;">&#91;</span><span style="color: #3366CC;">'jquery'</span><span style="color: #009900;">&#93;</span>
    	  <span style="color: #009900;">&#125;</span><span style="color: #339933;">,</span>
        <span style="color: #3366CC;">'angular'</span><span style="color: #339933;">:</span> <span style="color: #009900;">&#123;</span>
          exports<span style="color: #339933;">:</span> <span style="color: #3366CC;">'angular'</span>
        <span style="color: #009900;">&#125;</span>
      <span style="color: #009900;">&#125;</span><span style="color: #339933;">,</span>
    &nbsp;
      <span style="color: #006600; font-style: italic;">// kick start application</span>
      deps<span style="color: #339933;">:</span> <span style="color: #009900;">&#91;</span><span style="color: #3366CC;">'./bootstrap'</span><span style="color: #009900;">&#93;</span>
    <span style="color: #009900;">&#125;</span><span style="color: #009900;">&#41;</span><span style="color: #339933;">;</span></pre></td></tr></table><p class="theCode" style="display:none;">require.config({
      paths: {
        'semantic': '../../bower_components/semantic-ui/build/packaged/javascript/semantic.min',
        'jquery': '../../bower_components/jquery/dist/jquery.min',
        'domReady': '../../bower_components/requirejs-domready/domReady',
        'angular': '../../bower_components/angular/angular.min',
        'angular-route': '../../bower_components/angular-route/angular-route.min',
        'angular-resource': '../../bower_components/angular-resource/angular-resource.min',
        'jquery.fileupload': '../../bower_components/angular-jqfile-upload/js/jquery.fileupload',
        'jquery.fileupload-angular': '../../bower_components/angular-jqfile-upload/js/jquery.fileupload-angular',
        'jquery.ui.widget': '../../bower_components/angular-jqfile-upload/js/vendor/jquery.ui.widget',
        'jquery.fileupload-image': '../../bower_components/angular-jqfile-upload/js/jquery.fileupload-image',
        'jquery.fileupload-process': '../../bower_components/angular-jqfile-upload/js/jquery.fileupload-process',
        'jquery.fileupload-audio': '../../bower_components/angular-jqfile-upload/js/jquery.fileupload-audio',
        'jquery.fileupload-video': '../../bower_components/angular-jqfile-upload/js/jquery.fileupload-video',
        'jquery.fileupload-validate': '../../bower_components/angular-jqfile-upload/js/jquery.fileupload-validate',
        'jquery.fileupload-ui': '../../bower_components/angular-jqfile-upload/js/jquery.fileupload-ui',
        'jquery.iframe-transport': '../../bower_components/angular-jqfile-upload/js/jquery.iframe-transport',
        'canvas-to-blob': '../../bower_components/blueimp-canvas-to-blob/js/canvas-to-blob.min',
        'load-image': '../../bower_components/blueimp-load-image/js/load-image.min',
        'load-image-exif': '../../bower_components/blueimp-load-image/js/load-image-exif',
        'load-image-ios': '../../bower_components/blueimp-load-image/js/load-image-ios',
        'load-image-meta': '../../bower_components/blueimp-load-image/js/load-image-meta',
        'load-image-orientation': '../../bower_components/blueimp-load-image/js/load-image-orientation'
      },
    
      // angular does not support AMD out of the box, put it in shim
      shim: {
    	  'semantic': {
    		  exports: 'semantic',
    		  deps: ['jquery']
    	  },
        'angular': {
          exports: 'angular'
        }
      },
    
      // kick start application
      deps: ['./bootstrap']
    });</p></div>
    ";i:2;s:708:"
    <div class="wp_syntax" style="position:relative;"><table><tr><td class="code"><pre class="javascript" style="font-family:monospace;">    .....
        <span style="color: #3366CC;">'load-image'</span><span style="color: #339933;">:</span> <span style="color: #3366CC;">'../../bower_components/blueimp-load-image/js/load-image&lt;span style=&quot;text-decoration: line-through;&quot;&gt;.min&lt;/span&gt;'</span><span style="color: #339933;">,</span>
        .....</pre></td></tr></table><p class="theCode" style="display:none;">    .....
        'load-image': '../../bower_components/blueimp-load-image/js/load-image&lt;span style=&quot;text-decoration: line-through;&quot;&gt;.min&lt;/span&gt;',
        .....</p></div>
    ";}
categories:
  - Angular
  - JavaScript
  - RequireJS
tags:
  - angular
  - file
  - jqfileupload
  - plugin
  - require
  - requirejs
  - upload
format: aside

---
Once upon a time, I needed to use jqFileUPload plugin (actually modified version which provides Angular&#8217;s directive around native jqFileUpload plugin).
  
In the same time, my Angular-base project was configured to be used together with RequireJS.
  
I spend few ours trying to figure out what I was doing wrong &#8212; why I was getting errors in my browser&#8217;s console.
  
Those errors were about something weird&#8230; Something in \`load-image-exif\` and \`load-image\` files.

My require.js main config file looked like this:

<pre lang="javascript">require.config({
  paths: {
    'semantic': '../../bower_components/semantic-ui/build/packaged/javascript/semantic.min',
    'jquery': '../../bower_components/jquery/dist/jquery.min',
    'domReady': '../../bower_components/requirejs-domready/domReady',
    'angular': '../../bower_components/angular/angular.min',
    'angular-route': '../../bower_components/angular-route/angular-route.min',
    'angular-resource': '../../bower_components/angular-resource/angular-resource.min',
    'jquery.fileupload': '../../bower_components/angular-jqfile-upload/js/jquery.fileupload',
    'jquery.fileupload-angular': '../../bower_components/angular-jqfile-upload/js/jquery.fileupload-angular',
    'jquery.ui.widget': '../../bower_components/angular-jqfile-upload/js/vendor/jquery.ui.widget',
    'jquery.fileupload-image': '../../bower_components/angular-jqfile-upload/js/jquery.fileupload-image',
    'jquery.fileupload-process': '../../bower_components/angular-jqfile-upload/js/jquery.fileupload-process',
    'jquery.fileupload-audio': '../../bower_components/angular-jqfile-upload/js/jquery.fileupload-audio',
    'jquery.fileupload-video': '../../bower_components/angular-jqfile-upload/js/jquery.fileupload-video',
    'jquery.fileupload-validate': '../../bower_components/angular-jqfile-upload/js/jquery.fileupload-validate',
    'jquery.fileupload-ui': '../../bower_components/angular-jqfile-upload/js/jquery.fileupload-ui',
    'jquery.iframe-transport': '../../bower_components/angular-jqfile-upload/js/jquery.iframe-transport',
    'canvas-to-blob': '../../bower_components/blueimp-canvas-to-blob/js/canvas-to-blob.min',
    'load-image': '../../bower_components/blueimp-load-image/js/load-image.min',
    'load-image-exif': '../../bower_components/blueimp-load-image/js/load-image-exif',
    'load-image-ios': '../../bower_components/blueimp-load-image/js/load-image-ios',
    'load-image-meta': '../../bower_components/blueimp-load-image/js/load-image-meta',
    'load-image-orientation': '../../bower_components/blueimp-load-image/js/load-image-orientation'
  },

  // angular does not support AMD out of the box, put it in shim
  shim: {
	  'semantic': {
		  exports: 'semantic',
		  deps: ['jquery']
	  },
    'angular': {
      exports: 'angular'
    }
  },

  // kick start application
  deps: ['./bootstrap']
});</pre>

Those errors made me crazy so I even decided to get rid of using RequireJS with Angular app at all!
  
Next day, I decided Google for a bit and I was extremly lucky to get to this answer &#8212; <a href="http://stackoverflow.com/a/20734214" target="_blank">http://stackoverflow.com/a/20734214</a>.
  
No votes for it, but that is correct answer and helps resolve the issue.

To recall here, the reason is &#8212; I used minified version of \`load-image\` script, which includes all dependencies in it&#8230;
  
So, all I had to do is replace this line with a path to not minified version:

<pre lang="javascript">.....
    'load-image': '../../bower_components/blueimp-load-image/js/load-image<span style="text-decoration: line-through;">.min</span>',
    .....
</pre>

After had that done everything started up.