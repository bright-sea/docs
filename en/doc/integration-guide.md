---
title: Integration Guide
description: "WebPivotTable integration guide"
---

WebPivotTable follows web component standard so that it can be easily integrated into any web pages or web applications.

## Download

In [Quick Start](/doc/quick-start) we import WebPivotTable javascript wpt.js from latest released WebPivotTable on this website,
this is not suggested for any production use as this release is only for test purpuse, the link may be broken and also no guratee of performance.
 
For production use, please go to [Download Page](/download) to get a WebPivotTable package.

There are two editions of WebPivotTable: Free edition and Pro edition.
Free edition has almost the same functionalities as Pro edition except that Free edition does not provide some [APIs](/doc/apis). 

## Installation

WebPivotTable is an javascript component, the installation is just like any other javascript component.
Put component javascript files to any public directory of web server so that your web page or web application can
import them is all you need to do.

When you get the packaged zip file, unzip it to any directory and you will see list below directory structure:

```
webpivotptable
       ├─-- public
       |       ├─-- dist
       |       |      └─-- wpt.js
       |       |--- lang  
       |       |      ├─-- de.json
       |       |      ├─-- en.json
       |       |      ├─-- es.json
       |       |      ├─-- it.json
       |       |      ├─-- pt.json
       |       |      ├─-- tr-TR.json
       |       |      └─-- zh-CN.json
       |       ├─-- index.html
       |       ├─-- jquery.html
       |       ├─-- ...
       |       └─-- react.html
       └─-- server
               ├─-- README.md
               ├─-- package.json
               ├─-- server.js
               └─-- wpt.json

```
 
__"public"__ directory is all you need to integrate WebPivotTable into your web page or web application.
Copy this directory into root public directory of your web server, and that's it, installation is done.  

  * __"lang"__ sub-directory includes all language files to support internationalization(i18n). 
 
    <div class="Alert Alert--orange">
    Please reference [Internationalization](/doc/internationalization) for more details. 
    </div>

  * Those html files under public directory are not necessary for WebPivotTable to work. They are just samples on how to
   integrate WebPivotTable into different environments, you can remove them anytime.


__"server"__ directory includes a NodeJs proxy server to support cross domain access. WebPivotTable has a default
 proxy server setting so that you do not need to run your own proxy server. But if run your own proxy server is necessary, 
 please follow README.md inside this directory to set it up. 
Please reference [Cross domain access](/doc/cross-domain-access) for more details. 
 
 
## Integration
 
To integrate WebPivotTable, we only need to import one javascript file into web page like:

```html
<script type="text/javascript" src="./dist/wpt.js"></script>
```

Then, we can put a "wpt-pivot-table" tag into page:
```html
<body>
  <div style="width: 600px; height:480px;">
    <web-pivot-table />
  </div>
</body>
``` 
 
That's all. Simple enough. Now we have a full functional WebPivotTable on our web page.       
 
List below is an example html file:
```html
<html>

<head>
  <script type="text/javascript" src="./dist/wpt.js"></script>
</head>

<body>
  <div style="width: 600px; height:480px;">
    <web-pivot-table />
  </div>
</body>

</html>
```  
  
  
## Customization

WebPivotTable provides lots of options for developer to customize its look and feel and behaviours
in web page or web application.

<div class="Alert Alert--orange">
Please reference [Options](/doc/options) for all possible options.
</div>


WebPivotTable also provides lots of APIs for developers to call from hosted web page or web application.
For example, developers can use these APIs to load source data from any kind of data resources,
or to save WebPivotTable into server side for future reload, etc.




