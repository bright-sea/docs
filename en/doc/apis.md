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
  
  

<h2 id="set-locale"> setLocale </h2>

```javascript
wpt.setLocale(locale);
```
| Param Name     | Param Type  | Optional   | Description                 |
|----------------|-------------|------------|-----------------------------|
|locale          | String      | no         | locale code                 |


<h2 id="set-options"> setOptions </h2>

```javascript
wpt.setOptions(options);
```
| Param Name       | Param Type    | Optional   | Description                 |
|------------------|---------------|------------|-----------------------------|
|options           | Object        | no         |  customize options          |

> This `setOptions` API is a major way to customize WebPivotTable, see [Options](/doc/options) for more details.

<h2 id="get-options"> getOptions </h2>

```javascript
var options = wpt.getOptions();
```

<h2 id="show-control-panel"> showControlPanel </h2>

```javascript
wpt.showControlPanel();
```

<h2 id="hide-control-panel"> hideControlPanel </h2>

```javascript
wpt.hideControlPanel();
```

<h2 id="toggle-control-panel"> toggleControlPanel </h2>

```javascript
wpt.toggleControlPanel();
```

<h2 id="open-dialog"> openDialog </h2>

```javascript
wpt.openDialog({ type: "" , width: "", height: ""});
```

| Param Name      | Param Type    | Optional   | Description                 |
|-----------------|---------------|------------|-----------------------------|
| type            | String        | no         |            |
| width           | String        | yes         |            |
| height          | String        | yes         |            |
| payload         | Object        | yes         |            |


<h2 id="close-dialog"> closeDialog </h2>

```javascript
wpt.closeDialog();
```

<h2 id="reset"> reset </h2>

```javascript
wpt.reset();
```

<h2 id="refresh"> refresh </h2>

```javascript
wpt.refresh();
```

<h2 id="loading-message"> loadingMessage </h2>

```javascript
wpt.loadingMessage(message);
```
| Param Name       | Param Type    | Optional   | Description                 |
|------------------|---------------|------------|-----------------------------|
| message          | String        | no         |            |

<h2 id="clear-message"> clearMessage </h2>

```javascript
wpt.clearMessage();
```


<h2 id="error-message"> errorMessage </h2>

```javascript
wpt.errorMessage(error);
```
| Param Name       | Param Type             | Optional   | Description                 |
|------------------|------------------------|------------|-----------------------------|
|error             | String or Object       | no         |            |


