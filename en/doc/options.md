---
title: Options
description: ""
---

WebPivotTable use options internally to control its look and feels and behaviours.
Change any of these options will trigger WebPivotTable to refresh and the changes
will take effect immediately. 

Setting these options is the major mechanism to customize WebPivotTable.

<h2 id="how-to-set-options"> How To Set Options? </h2>

There are two ways to set options:

*  ### Passing options as attribute of `web-pivot-table` tag
  ```html
    <web-pivot-table
      options='{"localeFilePath": "./lang/", "locale":"en", "leavePageWarning": 0}'>
    </web-pivot-table>
  ```
  Since attribute of HTML tag or custom element can only be a string, we need stringify options when we
  passing it this way. WebPivotTable will convert this string to javascript object and **deeply merge** it into
  default options.
   
  It is quite easy to make mistake when write options like this, so it might not a good idea to set complicate options this way.
  But if we are using WebPivotTable together with some javascript framework, like React and Vue, we can pass javascript object as props
  and in that case, passing complicate options this way is not an issue.
  
* ### Calling `setOptions` API 
  Instead of passing options as attribute of web-pivot-tab tag, we can also set options by calling [setOptions API](/doc/apis/setoptions)
  after WebPivotTable was created on page.   

  ```javascript
    var wpt = document.getElementsByTagName('web-pivot-table')[0];
  
    wpt.setOptions({
      localeFilePath: "./lang/",
      locale: "en",
      leavePageWarning: 0
    });
  ```
  Since we can pass javascript object as parameters of `setOptions` API and it will be **deeply merged** into
  default options, this is a better way to set complicate options.


<h2 id="leave-page-warning"> `leavePageWarning` </h2>

| Option             | Type      | Default  | Description                 |
|--------------------|-----------|----------|-----------------------------|
| `leavePageWarning` | `bool`    | 0        | When user navigate away from the web page which integrated WebPivotTable, whether we popup a warning dialog or not?       |

If we set it to `true`, it will give end users a chance to save their operations before they leave. 

<img src="../resources/doc/images/leave-page-warning.png" height="200" />

This dialog is a system dialog of browsers, different browsers may have different style of dialogs. The prompt message
comes from language file `Msg_LeavingPage`. 



<h2 id="locale"> `locale` </h2>

| Option             | Type      | Default  | Description                 |
|--------------------|-----------|----------|-----------------------------|
| `locale`           | `string`  | 'en'     | Current language locale, it should be set to one of [availableLocales](#available-locales)       |

[setLocale API](/doc/apis/set-locale) will change this option as well.


<h2 id="locale-file-path"> `localeFilePath` </h2>

| Option             | Type      | Default    | Description                 |
|--------------------|-----------|------------|-----------------------------|
| `localeFilePath`   | `string`  | './lang'   | locale file path. This is a relative path from your `lang` directory to web page html file.       |

  
<h2 id="available-locales"> `availableLocales` </h2>

| Option             | Type      | Default              | Description                 |
|--------------------|-----------|----------------------|-----------------------------|
| `availableLocales` | `array`   | see below            | Selectable language locales for users to switch languages.       |

Default `availableLocales`:
```
  availableLocales: [{
    value: 'en', abbr: 'EN', label:'Lbl_English', attach:" ( english ) "
  },{
    value: 'zh-CN', abbr: 'CN', label:'Lbl_Chinese', attach:" ( 中文 ) "
  },{
    value: 'de', abbr: 'DE', label:'Lbl_German', attach:" ( deutsch ) "
  },{
    value: 'tr-TR', abbr: 'TR', label:'Lbl_Turkish', attach:" ( türk ) "
  },{
    value: 'es', abbr: 'ES', label:'Lbl_Spanish', attach:" ( español ) "
  },{
    value: 'pt', abbr: 'PT', label:'Lbl_Portuguese', attach:" ( português ) "
  },{
    value: 'it', abbr: 'IT', label:'Lbl_Italian', attach:" ( italiano ) "
  // },{
  //   value: 'fr', abbr: 'FR', label:'Lbl_French', attach:" ( français ) "
  // },{
  //   value: 'ar', abbr: 'AR', label:'Lbl_Arabic', attach:" ( العربية ) "
  // },{
  //   value: 'ru-RU', abbr: 'RU', label:'Lbl_Russian', attach:" ( русский ) "
  // },{
  //   value: 'nl', abbr: 'NL', label:'Lbl_Dutch', attach:" ( Nederlands ) "
  // },{
  //   value: 'el', abbr: 'EL', label:'Lbl_Greek', attach:" ( Ελληνικά ) "
  // },{
  //   value: 'he', abbr: 'HE', label:'Lbl_Hebrew', attach:" ( עִבְרִית ) "
  // },{
  //   value: 'hi', abbr: 'HI', label:'Lbl_Hindi', attach:" ( हिन्दीة ) "
  // },{
  //   value: 'hu', abbr: 'HU', label:'Lbl_Hungarian', attach:" ( magyar ) "
  // },{
  //   value: 'sv', abbr: 'SV', label:'Lbl_Swedish', attach:" ( svenska ) "
  // },{
  //   value: 'ko', abbr: 'KO', label:'Lbl_Korean', attach:" ( 한국어 ) "
  // },{
  //   value: 'ja', abbr: 'JA', label:'Lbl_Japanese', attach:" ( 日本語 ) "
  // },{
  //   value: 'vn', abbr: 'VN', label:'Lbl_Vietnamese', attach:" ( Tiếng Việt ) "
  }]
```
| Property   | Type      |  Description                                          |
|------------|-----------|-------------------------------------------------------|
| value      | `string`  | locale code                                           |
| abbr       | `string`  | abbreiation to display on header                      |
| label      | `string`  | message name in language files to show as label       |
| attach     | `string`  | attach to label use original language translation     |


<img src="../resources/doc/images/language-switch.png" width="200" />


Please reference [Internationalization](/doc/internationalization) for more details.
 



<h2 id="server"> `server` </h2>

| Option                     | Type      | Default                                        | Description                 |
|----------------------------|-----------|------------------------------------------------|-----------------------------|
| `server.fileProxyEnabled`  | `bool`    | 1                                              | enable/disable file Proxy       |
| `server.fileProxy`         | `string`  | 'https://demo.webpivottable.com/wpt/fileProxy' |  file Proxy       |
| `server.fileTimeout`       | `number`  | 30000                                          |  file Proxy Timeout       |
| `server.xmlaProxyEnabled`  | `bool`    | 1                                              | enable/disable xmla Proxy               |
| `server.xmlaProxy`         | `string`  | 'https://demo.webpivottable.com/wpt/xmlaProxy' |  xmla Proxy       |
| `server.xmlaTimeout`       | `number`  | 30000                                          |  xmla Proxy Timeout       |
| `server.basicAuthEnabled`  | `bool`    | 0                                              | enable/disable Basic Authentication       |
| `server.username`          | `string`  | 'username'                                     |  Basic Authentication username       |
| `server.password`          | `string`  | 'password'                                     |  Basic Authentication password       |
| `server.rolesEnabled`      | `bool`    | 0                                              | enable/disable roles control       |
| `server.roles`             | `string`  | 'test'                                         |  comma separate roles list       |


<h2 id="limit"> `limit` </h2>

| Option                         | Type      | Default   | Description                 |
|--------------------------------|-----------|-----------|-----------------------------|
| `limit.sourceDataMaxRows`      | `number`  | 100000    | maximum supported rows of source data      |
| `limit.sourceDataMaxColumns`   | `number`  | 1000      | maximum supported columns of source data      |
| `limit.sourceDataMaxDataCells` | `number`  | 10000000  | maximum supported cells of source data      |
| `limit.sheetLayoutMaxRows`     | `number`  | 1000      | sheet layout maximum rows      |
| `limit.sheetLayoutMaxColumns`  | `number`  | 1000      | pivot layout maximum columns      |
| `limit.sheetLayoutMaxDataCells`| `number`  | 10000     | sheet layout maximum data cells      |
| `limit.olapDrillThroughMaxRows`| `number`  | 1000      | Max return rows for each Olap drill through call      |

<h2 id="small-screen-breakpoint"> `smallScreenBreakpoint` </h2>

| Option                    | Type      | Default   | Description                 |
|---------------------------|-----------|-----------|-----------------------------|
| `smallScreenBreakpoint`   | `number`  |  768      | with < 768     Small Screen device (phone)       |


<h2 id="medium-screen-breakpoint"> `mediumScreenBreakpoint` </h2>

| Option                     | Type      | Default  | Description                 |
|----------------------------|-----------|----------|-----------------------------|
| `mediumScreenBreakpoint`   | `number`  |  1080    |  768 <= width <= 1080  (tablet)       |


<h2 id="decimal-point"> `decimalPoint` </h2>

| Option           | Type      | Default  | Description                 |
|------------------|-----------|----------|-----------------------------|
| `decimalPoint`   | `string`  |  '.'     |  decimal point charactor: '.', ','       |

<h2 id="thousands-sep"> `thousandsSep` </h2>

| Option             | Type      | Default | Description                 |
|--------------------|-----------|---------|-----------------------------|
| `thousandsSep`     | `string`  |  ','    |  thousands separator: ',' '.', ' '       |

<h2 id="default-to-distinct-count"> `defaultToDistinctCount` </h2>

| Option                     | Type      | Default  | Description                 |
|----------------------------|-----------|----------|-----------------------------|
| `defaultToDistinctCount`   | `bool`    |  0       |  Default statistic function of String field to distinct count   |


<h2 id="drill-through-by-single-click"> `drillThroughBySingleClick` </h2>

| Option                     | Type      | Default  | Description                 |
|----------------------------|-----------|----------|-----------------------------|
| `drillThroughBySingleClick`| `bool`    |  0       |  dblclick/click to drill through pivot grid or pivot charts   |

<h2 id="defer-layout-exclude-filter"> `deferLayoutExcludeFilter` </h2>

| Option                     | Type      | Default  | Description                 |
|----------------------------|-----------|----------|-----------------------------|
| `deferLayoutExcludeFilter` | `bool`    |  0       |  exclude field sort/filter from defer layout update   |


<h2 id="default-value-format"> `defaultValueFormat` </h2>

| Option                        | Type      | Default  | Description                 |
|-------------------------------|-----------|----------|-----------------------------|
| `defaultValueFormat.category` | `string`  |  WptConstants.VALUE_FORMAT_CATEGORY_NUMBER   |  Default format for negative number   |
| `defaultValueFormat.negative` | `string`  |  WptConstants.VALUE_NEGATIVE_RED_MINUS       |  Default format for negative number   |


<h2 id="ui-flags"> `uiFlags` </h2>

| Option                        | Type      | Default | Description                 |
|-------------------------------|-----------|---------|-----------------------------|
| `uiFlags.dropPrompt`          | `bool`    | 1       | show/hide prompt text for drop file      |
| `uiFlags.pivotPrompt`         | `bool`    | 1       | show/hide prompt text for select fields      |
| `uiFlags.connectSource`       | `bool`    | 1       | show/hide Connect to source button      |
| `uiFlags.open`                | `bool`    | 1       | show/hide Open wpt file button      |
| `uiFlags.save`                | `bool`    | 1       | show/hide Save button      |
| `uiFlags.reset`               | `bool`    | 1       | show/hide Reset button      |
| `uiFlags.source`              | `bool`    | 1       | show/hide Data source button      |
| `uiFlags.export`              | `bool`    | 1       | show/hide Export button      |
| `uiFlags.fullScreen`          | `bool`    | 1       | enable/disable "Full Screen" mode      |
| `uiFlags.localeSwitch`        | `bool`    | 1       | show/hide header locale switch      |
| `uiFlags.setting`             | `bool`    | 1       | show/hide header Setting button/menu     |
| `uiFlags.about`               | `bool`    | 1       | show/hide header About button/menu  Pro Edition only     |
| `uiFlags.loadFromCsv`         | `bool`    | 1       | show/hide Load data from csv file      |
| `uiFlags.loadFromExcel`       | `bool`    | 1       | show/hide Load data from excel file      |
| `uiFlags.loadFromGss`         | `bool`    | 1       | show/hide Load data from "Google Spreadsheet"      |
| `uiFlags.loadFromWs`          | `bool`    | 1       | show/hide Load data or wpt from "Web Service"      |
| `uiFlags.loadFromOlap`        | `bool`    | 1       | show/hide Load data or wpt from OLAP cube      |
| `uiFlags.saveToLocal`         | `bool`    | 1       | show/hide Save WPT dialog "Save to local" Tab      |
| `uiFlags.saveToServer`        | `bool`    | 1       | show/hide Save WPT dialog "Save to Server" Tab      |


<h2 id="styles"> `styles` </h2>

| Option                        | Type      | Default             | Description                 |
|-------------------------------|-----------|---------------------|-----------------------------|
| `styles.fontSize`             | `string`  | '14px'              | font size      |
| `styles.windowHeaderColor`    | `string`  | 'lightblue'         | header/ dialog header background color      |
| `styles.toolBarColor`         | `string`  | 'aliceblue'         | toolbar background color      |
| `styles.highLightColor`       | `string`  | 'rgb(250, 224, 177)'| highlight background color      |
| `styles.messageColor`         | `string`  | 'orangered'         | message text color      |


<h2 id="file-links"> `fileLinks` </h2>

| Option        | Type     | Default  | Description                 |
|---------------|----------|----------|-----------------------------|
| `fileLinks`   | `array`  | []       | Samples link      |


```
  [
    {
      type: Constants.sourceType.WPT,
      url: "https://webpivottable.com/testfiles/file9.wpt",
      label: "Test file 9 (olap mode)"
    },{
      type: Constants.sourceType.WPT,
      url: "https://webpivottable.com/testfiles/file8.wpt",
      label: "Test file 8 (memory mode)"
    },{
      type: Constants.sourceType.CSV,
      url: "https://webpivottable.com/testfiles/example.csv",
      label: "USA Selection Poll Data (Total 4,000 records)"
    },{
      type: Constants.sourceType.CSV,
      url: "https://webpivottable.com/testfiles/sales.csv",
      label: "Sales Sample Data (Total 2,823 records)"
    },{
      type: Constants.sourceType.CSV,
      url: "https://webpivottable.com/testfiles/FL_insurance.csv",
      label: "Florida Insurance Data (Total 36,634 records)"
    },{
      type: Constants.sourceType.EXCEL,
      url: "https://webpivottable.com/testfiles/example.xls",
      label: "USA Selection Poll Data (Total 4,000 records)"
    },{
      type: Constants.sourceType.EXCEL,
      url: "https://webpivottable.com/testfiles/sales.xls",
      label: "Sales Sample Data (Total 2,823 records)"
    },{
      type: Constants.sourceType.EXCEL,
      url: "https://webpivottable.com/testfiles/FL_insurance.xls",
      label: "Florida Insurance Data (Total 36,634 records)"
    },{
      type: Constants.sourceType.EXCEL,
      url: "https://webpivottable.com/testfiles/example.xlsx",
      label: "USA Selection Poll Data (Total 4,000 records)"
    },{
      type: Constants.sourceType.EXCEL,
      url: "https://webpivottable.com/testfiles/sales.xlsx",
      label: "Sales Sample Data (Total 2,823 records)"
    },{
      type: Constants.sourceType.EXCEL,
      url: "https://webpivottable.com/testfiles/FL_insurance.xlsx",
      label: "Florida Insurance Data (Total 36,634 records)"
    },{
      type: Constants.sourceType.WSWPT,
      url: "https://webpivottable.com/testfiles/sample91.wpt",
      label: "Predefined small CSV WebPivotTable file"
    },{
      type: Constants.sourceType.WSDATA,
      url: "https://demo.webpivottable.com/wpt/wsSample",
      label: "Simple Sample Web Service"
    },{
      type: Constants.sourceType.GSS,
      url: "https://docs.google.com/spreadsheet/pub?key=0Alkl5EEsxBwBdDFLV2Q4a1NWMmw1TXZBRlFMZ1Rxd0E&output=html",
      label: "USA Selection Poll Data (Total 4,000 records)"
    },{
      type: Constants.sourceType.GSS,
      url: "https://docs.google.com/spreadsheet/pub?key=0Alkl5EEsxBwBdHJMOTh4Sm1BSFlDYXRwVW5lc0xuMVE&output=html",
      label: "Sales Sample Data (Total 2,823 records)"
    },{
      type: Constants.sourceType.OLAP,
      url: "http://olap.flexmonster.com/olap/msmdpump.dll",
      label: "Sample Microsoft Analysis Service"
    },{
      type: Constants.sourceType.OLAP,
      url: "http://sampledata.infragistics.com/data/msmdpump.dll",
      label: "Sample Microsoft Analysis Service 1"
    },{
      type: Constants.sourceType.OLAP,
      url: "http://52.4.22.157:8080/mondrian/xmla",
      label: "Sample Mondrian OLAP Server"
    },{
      type: Constants.sourceType.OLAP,
      url: "http://52.4.22.157:8282/icCube/xmla",
      label: "Sample icCube OLAP Server"
    }
  ]
```

<h2 id="custom-handlers"> `customHandlers`  <span class="Alert Alert--orange"> Pro edition only.</span> </h2>

| Option                         | Type        | Default | Description                 |
|--------------------------------|-------------|---------|-----------------------------|
| `customHandlers.connectSource` | `bool`      | 0       | enable/disable custom "Connect to source" handler      |
| `customHandlers.openWpt`       | `bool`      | 0       | enable/disable custom "Open wpt" handler      |
| `customHandlers.saveWpt`       | `bool`      | 0       | enable/disable custom "Save wpt" handler      |
| `customHandlers.drillThrough`  | `bool`      | 0       | enable/disable custom "drill Through" handler      |

This custom Handlers only available in Pro Edition.

These options only enable/disable custom handlers, the real custom handler should be passing in event listener.
Please see [How to listen To Events](/doc/events#how-to-listen-to-events) for more details.


<h2 id="filestack"> `filestack` </h2>

| Option                | Type        | Default                     | Description                 |
|-----------------------|-------------|-----------------------------|-----------------------------|
| `filestack.enabled`   | `bool`      | 1                           | enable to use filestack to load data      |
| `filestack.key`       | `string`    | ''                          | filestack application key       |


key: "A4bieoUsyR4yBrNPkFIvrz"  //demo.webpivottable.com

<h2 id="sheet"> `sheet` </h2>

```
{
  showGrid: 1,
  expandRows: 1, // Expand/collapse All rows
  expandCols: 1, // Expand/Collapse All columns
  showRowTotals: 1,
  showColTotals: 1,
  showRowSubtotals: 1,
  showColSubtotals: 1,

  grid: {
    showSigns: 1,
    showEmptyAsZero: 0,
    compactForm: 1,
    rowHeaderWidth: 200,
    cellWidth: 100,
    cellHeight: 20,
    theme: "wpt-default",
    noFixedColumns: 0,
    cellStyle: {
      columnHeader: {
        textAlign: "center",
        backgroundColor: "#bfd6eb",
        fontWeight: "bold"
      },
      compoundColumn: {
        verticalAlign: "top",
        textAlign: "left",
        backgroundColor: "#bfd6eb",
        fontWeight: "bold"
      },
      rowHeader: {
        textAlign: "left",
        backgroundColor: "#bfd6eb",
        fontWeight: "bold"
      },
      compoundRow: {
        verticalAlign: "top",
        textAlign: "left",
        backgroundColor: "#bfd6eb",
        fontWeight: "bold"
      },
      totalCell: {
        textAlign: "right",
        backgroundColor: "#72d2df"
      },
      subtotalCell: {
        textAlign: "right",
        backgroundColor: "#d2e9e9"
      },
      dataCell: {
        textAlign: "right",
        backgroundColor: "#eee"
      },
      noDataCell: {
        backgroundColor: "#ddd"
      }
    }
  },

  chart: {
    width: 600,
    height: 500,
    combined: true,

    high: {
      theme: "default", //default, grid, gray, skies, drak-blue, drak-green
      chart: {
        type: "column", //column, bar, line, spline, area, areaspline, pie
        options3d: {
          enabled: false,
          alpha: 15,
          beta: 15,
          depth: 50,
          viewDistance: 25
        }
      },
      credits: {
        enabled: false
      },
      exporting: {
        enabled: false
      },
      navigation: {
        buttonOptions: {
          align: "right", // left, center, right
          verticalAlign: "top" // top, middle, bottom
        }
      },
      legend: {
        enabled: true,
        floating: false,
        layout: "vertical", //horizontal, vertical
        align: "right", // left, center, right
        verticalAlign: "middle", // top, middle, bottom
        reversed: false
      },
      tooltip: {
        enabled: true,
        shadow: true
      },
      plotOptions: {
        series: {
          stacking: null, //null, 'normal', 'percent'
          dataLabels: {
            enabled: false,
            align: "center", // left, center, right
            rotation: 0 // 0 -- 360
          }
        }
      },
      xAxis: {
        labels: {
          enabled: true,
          align: "left", // left, center, right
          rotation: 45 // 0 -- 360
        }
      }
    }
  }
}
 
```

