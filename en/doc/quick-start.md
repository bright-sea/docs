---
title: Quick Start
description: "WebPivotTable quick start"
---

<a href="https://webpivottable.com/releases/latest/demo.html" target="_blank">Try WebPivotTable online</a>

WebPivotTable looks great, I want to integrate it into my web page.
But I am not a professional developer, is it still possible for me to do it?

The answer is YES. Actually you don't need to download anything or even know how to program javascript.
With two simple steps, you can put WebPivotTable into your web page.

### STEP 1: import wpt.js in head

In the head of your web page html file, import wpt.js from our web site:

```html
<head>
  <script type="text/javascript" src="https://webpivottable.com/releases/latest/dist/wpt.js" ></script>
</head>
```
 

### STEP 2: add a <wpt-pivot-table> tag into the body:

```html
<body>
  <div style="width: 600px; height:480px;">
    <web-pivot-table />
  </div>
</body>
``` 
 
That's all. Now open your web page. A fully functional WebPivotTable has been embedded into your page.


You can watch this on [Quick Start Demo](/demo)

If you need deep integration, please see our [Integration Guide](/doc/integration-guide)

