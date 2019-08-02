---
title: Web Component Demo
type: live
description: Using WebPivotTable as a standard Web Component
livelink: ../livedemo/index.html
documentation: /doc/installation#starting-from-scratch
---

This is a showcase how we can easily integrate WebPivotTable into a web page as a custom element following new
[Web Component Standard](https://en.wikipedia.org/wiki/Web_Components)  

below is source code of this demo:

```html

<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="utf-8">
  <meta http-equiv="Content-type" content="text/html;charset=UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">
  <meta name="viewport" content="width=device-width,initial-scale=1">

  <title>WebPivotTable</title>

  <style type="text/css">
    html, body, #wpt-container {width:100%;height:100%; padding:0; margin:0;}
  </style>

  <script type="text/javascript" src="./dist/vendor.js"></script>
  <script type="text/javascript" src="./dist/wpt.js"></script>

</head>

<body>
  <div id="wpt-container">
    <web-pivot-table />
  </div>
</body>

</html>

```
And please reference document at here.
