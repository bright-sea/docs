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
  
  

<h2 id="set-locale">setLocale</h2>

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
| message         | String         | no         |            |

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
|error             | `string`|`Object`      | no         |            |




<h2 id="set-wpt-from-data-array"> setWptFromDataArray </h2>  

```javascript
wpt.setWptFromDataArray(attrArray, dataArray, dataUrl, url, type);
```

| Param Name     | Param Type    | Optional   | Description                                                                                                                                                                                                                                                                                 |
|----------------|---------------|------------|----------------------------------------------------------------------------------------------------------------------------------------|
| attrArray      | Array         | no         | Array of attributes. example: `["department", "area", "cost", ...]`                                                                      |
| dataArray      | Array         | no         | Array of data rows, each row is also an array of values. example: `[["dep1", "area1", 1000, ...], ..., ["dep6", "area2", 2000,...]]`     |
| url            | String        | yes        | Url for track the source data, This is just for tracking, pass "" if not know or no need.                                              |
| type           | Object        | yes        | pre-saved wpt JSON object                                                                                                              |

Load source data from data array
  
Notes:  
- This is major API to load source data into WebPivotTable, it was
  used by `setWptFromCsvUrl` and `setWptFromExcelUrl` internally.  Actually, developers
  can load any kinds of data from any other resources, like SQL databases,
  and format them as attrArray and dataArray, then load them into WebPivotTable.


<h2 id="get-source-from-data-array"> getSourceFromDataArray </h2>  

```javascript
wpt.getSourceFromDataArray(attrArray, dataArray, dataUrl, url, type);
```

| Param Name     | Param Type    | Optional   | Description                                                                                                                                                                                                                                                                                 |
|----------------|---------------|------------|----------------------------------------------------------------------------------------------------------------------------------------|
| attrArray      | Array         | no         | Array of attributes. example: `["department", "area", "cost", ...]`                                                                      |
| dataArray      | Array         | no         | Array of data rows, each row is also an array of values. example: `[["dep1", "area1", 1000, ...], ..., ["dep6", "area2", 2000,...]]`     |
| url            | String        | yes        | Url for track the source data, This is just for tracking, pass "" if not know or no need.                                              |
| type           | Object        | yes        | pre-saved wpt JSON object                                                                                                              |


<h2 id="set-wpt-from-csv-url"> setWptFromCsvUrl </h2> 

```javascript
wpt.setWptFromCsvUrl(url, delimiter);
```
| Param Name       | Param Type    | Optional   | Description                                                                                                                                                                                                                                                                                 |
|------------------|---------------|------------|----------------------------------------------------------------------------------------------------------------------------------------|
| url              | String        | no         | URL String of CSV file           |
| delimiter        | String        | yes        | separator char for CSV file, default is `","`     |
  
Set wpt from CSV file URL
  

<h2 id="get-source-from-csv-url"> getSourceFromCsvUrl </h2> 

```javascript
wpt.getSourceFromCsvUrl(url, delimiter);
```
| Param Name       | Param Type    | Optional   | Description                                                                                                                                                                                                                                                                                 |
|------------------|---------------|------------|----------------------------------------------------------------------------------------------------------------------------------------|
| url              | String        | no         | URL String of CSV file           |
| delimiter        | String        | yes        | separator char for CSV file, default is `","`     |
  
Load source data from CSV file URL
  

<h2 id="set-wpt-from-excel-url"> setWptFromExcelUrl </h2> 

```javascript
wpt.setWptFromExcelUrl(url, delimiter);
```
| Param Name       | Param Type    | Optional   | Description                                                                                                                                                                                                                                                                                 |
|------------------|---------------|------------|----------------------------------------------------------------------------------------------------------------------------------------|
| url              | String        | no         | URL String of Excel file           |
| delimiter        | String        | yes        | separator char for Excel file, default is `","`     |
  
Set wpt from Excel file URL
  

<h2 id="get-source-from-excel-url"> getSourceFromExcelUrl </h2> 

```javascript
wpt.getSourceFromExcelUrl(url, delimiter);
```
| Param Name       | Param Type    | Optional   | Description                                                                                                                                                                                                                                                                                 |
|------------------|---------------|------------|----------------------------------------------------------------------------------------------------------------------------------------|
| url              | String        | no         | URL String of Excel file           |
| delimiter        | String        | yes        | separator char for Excel file, default is `","`     |
  
Load source data from Excel file URL
  


<h2 id="set-wpt-from-web-service"> setWptFromWebService </h2> 

```javascript
wpt.setWptFromWebService(url);
```
| Param Name     | Param Type    | Optional   | Description                                                                                                                                                                                                                                                                                 |
|----------------|---------------|------------|----------------------------------------------------------------------------------------------------------------------------------------|
| url            | String        | no         | URL String of Web Service           |
  
Set wpt from Web Service
  

<h2 id="get-source-from-web-service"> getSourceFromWebService </h2> 

```javascript
wpt.getSourceFromWebService(url);
```
| Param Name     | Param Type    | Optional   | Description                                                                                                                                                                                                                                                                                 |
|----------------|---------------|------------|----------------------------------------------------------------------------------------------------------------------------------------|
| url            | String        | no         | URL String of Web Service           |
  
Load source data from Web Service URL
  


<h2 id="set-wpt-from-google-spread-sheet"> setWptFromGoogleSpreadSheet </h2> 

```javascript
wpt.setWptFromGoogleSpreadSheet(url);
```
| Param Name     | Param Type    | Optional   | Description                                                                                                                                                                                                                                                                                 |
|----------------|---------------|------------|----------------------------------------------------------------------------------------------------------------------------------------|
| url            | String        | no         | URL String of Google Spread Sheet           |

Set wpt from Google Spread Sheet
  

<h2 id="get-source-from-google-spread-sheet"> getSourceFromGoogleSpreadSheet </h2> 

```javascript
wpt.getSourceFromGoogleSpreadSheet(url);
```
| Param Name     | Param Type    | Optional   | Description                                                                                                                                                                                                                                                                                 |
|----------------|---------------|------------|----------------------------------------------------------------------------------------------------------------------------------------|
| url            | String        | no         | URL String of Google Spread Sheet           |
  
Load source data from Google Spread Sheet URL
  

<h2 id="set-wpt-from-wot-Url"> setWptFromWptUrl </h2> 

```javascript
wpt.setWptFromWptUrl(url);
```
| Param Name       | Param Type    | Optional   | Description                                                                                                                                                                                                                                                                                 |
|------------------|---------------|------------|----------------------------------------------------------------------------------------------------------------------------------------|
| url              | String      | no         | URL String of wpt file           |
  
Set wpt from wpt file
  


<h2 id="set-wpt-from-local-file"> setWptFromLocalFile </h2> 

```javascript
wpt.setWptFromLocalFile(file, type);
```
| Param Name       | Param Type    | Optional   | Description                                                                                                                                                                                                                                                                                 |
|------------------|---------------|------------|----------------------------------------------------------------------------------------------------------------------------------------|
| file             | Object      | no         | local file           |
| type             | String      | no         | file type           |
  
Set wpt from local file
  

<h2 id="set-wpt"> setWpt </h2> 

```javascript
wpt.setWpt(wpt);
```
| Param Name       | Param Type          | Optional   | Description                                                                                                                                                                                                                                                                                 |
|------------------|---------------------|------------|----------------------------------------------------------------------------------------------------------------------------------------|
| wpt              | `String` or `Object`| no         | wpt string or object          |
  
Set wpt from wpt string or object
  

<h2 id="set-wpt-from-olap-cube"> setWptFromOlapCube </h2> 

```javascript
wpt.setWptFromOlapCube(olapData);
```
| Param Name       | Param Type    | Optional   | Description                                                                                                                                                                                                                                                                                 |
|------------------|---------------|------------|----------------------------------------------------------------------------------------------------------------------------------------|
| olapData         | Object      | no         | Object of OLAP Cube Information           |
  
Load OLAP Cube
  
```
olapData: {
  xmlaUrl: "Xmla server url",
  dataSourceInfo: "Data source info",
  catalog: "Catalog name",
  cubeName: "Cube name"
}
```  

<h2 id="get-source-from-olap-cube"> getSourceFromOlapCube </h2> 

```javascript
wpt.getSourceFromOlapCube(olapData);
```
| Param Name       | Param Type    | Optional   | Description                                                                                                                                                                                                                                                                                 |
|------------------|---------------|------------|----------------------------------------------------------------------------------------------------------------------------------------|
| olapData         | Object      | no         | Object of OLAP Cube Information           |
  
```
olapData: {
  xmlaUrl: "Xmla server url",
  dataSourceInfo: "Data source info",
  catalog: "Catalog name",
  cubeName: "Cube name"
}
```  
Load source data from Olap Cube
  

<h2 id="generate-wpt-string"> generateWptString  </h2> 

```javascript
wpt.generateWptString(ignoreData);
```
| Param Name       | Param Type    | Optional   | Description                                                                                                                                                                                                                                                                                 |
|------------------|---------------|------------|----------------------------------------------------------------------------------------------------------------------------------------|
| ignoreData       | Boolean       | no         | if equal to true, ignore data and fields, only save options and controls           |
  
Generate WPT format string
  

<h2 id="generate-wpt-json"> generateWptJSON </h2> 

```javascript
wpt.generateWptJSON(ignoreData);
```
| Param Name       | Param Type    | Optional   | Description                                                                                                                                                                                                                                                                                 |
|------------------|---------------|------------|----------------------------------------------------------------------------------------------------------------------------------------|
| ignoreData       | Boolean       | no         | if equal to true, ignore data and fields, only save options and controls           |
  
Generate WPT format JSON object
  

<h2 id="get-source-object"> getSourceObject </h2> 

```javascript
wpt.getSourceObject();
```
Get source object


<h2 id=set-source-object"> setSourceObject </h2> 

```javascript
wpt.setSourceObject(source);
```
| Param Name       | Param Type    | Optional   | Description                                                                                                                                                                                                                                                                                 |
|------------------|---------------|------------|----------------------------------------------------------------------------------------------------------------------------------------|
| source           | Object      | no         |                           |
  
Set source object
