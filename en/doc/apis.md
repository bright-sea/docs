---
title: APIs
description: "Application Program Interface"
---

WebPivotTable provides lots of APIs for developers to call them from hosted web page or web application.
For example, developers can use these APIs to load source data from any kind of
resources, or save reports to local files or server then reload them in future, etc.

<h2 id="how-to-call-apis"> How to call APIs? </h2>

*WebPivotTable follow web component standard. We can put WebPivotTable on any web page just like it is a HTML tag.
When web page loaded, there is a corresponding element created on DOM. Then we can call `document.getElementsByTagName`
to get an javascript object of the element. Each API of WebPivotTable is a method of this javascript object.*

Below is standard syntax to call APIs:  

```javascript
var wpt = document.getElementsByTagName('web-pivot-table')[0];

wpt.apiName(params1, params2, ..., paramsn);
```

Most of WebPivotTable APIs are asynchronous, it will return a Promise.  
  
