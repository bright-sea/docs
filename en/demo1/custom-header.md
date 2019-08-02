---
title: Custom Header
type: live
description: Demo on how to custom whole header bar
livelink: ../livedemo/custom-header.html
documentation: /doc/installation#starting-from-scratch
---

This demo show you that you can custom whole WebPivotTable header when you integrate WebPivotTable into
your web page or web application. 

<div class="Alert Alert--orange">
Custom Buttons are available in Pro edition only.
</div>

## Source Code

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <meta http-equiv="Content-type" content="text/html;charset=UTF-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">
  <meta name="viewport" content="width=device-width,initial-scale=1">

  <title>WebPivotTable Component</title>

  <style type="text/css">
    html, body {width:100%;height:100%; padding:0; margin:0;}
  </style>

  <script type="text/javascript" src="./dist/vendor.js"></script>
  <script type="text/javascript" src="./dist/wpt.js"></script>

  <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
  <script>
    $(document).ready(function(){
      var wpt = $('web-pivot-table')[0];

      $(".showhide").change(function() {
        var options= { uiFlags: {} };
        options.uiFlags[this.id] = this.checked ? 1 : 0;
        wpt.$eventBus.$emit('setOptions', options);
      });

      var button1 = {
        position: "left",
        type: "button",
        label: "Button1",
        labelTranslation: 0,
        title: "Custom button 1",
        titleTranslation: 0,
        style: "color: #000; font-weight: 300;",
        eventName: "customButton1"
      };

      var button2 = {
        position: "center",
        type: "button",
        label: "Button2",
        labelTranslation: 0,
        title: "",
        titleTranslation: 0,
        style: "color: #000; font-weight: 300;",
        eventName: "customButton2"
      };

      var button3 = {
        position: "right",
        type: "select",
        label: "Please select",
        labelTranslation: 0,
        style: "width:200px; margin-top: 1px;",
        value: "",
        options: [{
          label: "label1", value: "value1"
        }, {
          label: "label2", value: "value2"
        }, {
          label: "label3", value: "value3"
        }],
        eventName: "customButton3"
      };

      wpt.$eventBus.$on('customButton1', function(payload){
        $("#eventMessage").text("custom Button 1 clicked: " + JSON.stringify(payload));
      });

      wpt.$eventBus.$on('customButton2', function(payload){
        $("#eventMessage").text("custom Button 2 clicked: " + JSON.stringify(payload));
      });

      wpt.$eventBus.$on('customButton3', function(payload){
        $("#eventMessage").text("custom Button 3 (select) changed: " + JSON.stringify(payload));
      });

      $("input[name=button1][value='left']").prop("checked",true);
      $("input[name=button2][value='center']").prop("checked",true);
      $("input[name=button3][value='right']").prop("checked",true);

      var refreshCustomButtons = function() {
        const customButtons = [];
        if ($("#customButton1").is(':checked')){
          customButtons.push(button1);
        }
        if ($("#customButton2").is(':checked')){
          customButtons.push(button2);
        }
        if ($("#customButton3").is(':checked')){
          customButtons.push(button3);
        }
        wpt.$eventBus.$emit('setOptions', {customButtons: customButtons});
      };


      $("#customButton1").change(function() {
        refreshCustomButtons();
      });

      $("#customButton2").change(function() {
        refreshCustomButtons();
      });

      $("#customButton3").change(function() {
        refreshCustomButtons();
      });


      $('input:radio[name=button1]').change(function () {
        button1.position = $('input:radio[name=button1]:checked').val();
        refreshCustomButtons();
      });

      $('input:radio[name=button2]').change(function () {
        button2.position = $('input:radio[name=button2]:checked').val();
        refreshCustomButtons();
      });

      $('input:radio[name=button3]').change(function () {
        button3.position = $('input:radio[name=button3]:checked').val();
        refreshCustomButtons();
      });

      $('.colorButton').click(function (event) {
        var options = {
          styles: {
            windowHeaderColor: this.value
          }
        };
        wpt.$eventBus.$emit('setOptions', options);
      });

    });
  </script>

</head>

<body>

  <h3 style="text-align: center;margin-top:10px;">Custom WebPivotTable Header</h3>

  <div style="display:flex; flex-direction: row; justify-content: space-evenly;" >
    <div style="display:flex; flex-direction: column; border: 1px solid #888; width: 48%; ">
      <h4 style="text-align: center; margin: 5px;"> Show/Hide </h4>
      <div style="display:flex; flex-direction: row; flex-wrap: wrap;">
        <div style="margin: 3px 5px;"><input type="checkbox" class="showhide" id="header" checked> Header</div>
        <div style="margin: 3px 5px;"><input type="checkbox" class="showhide" id="source" checked> Source</div>
        <div style="margin: 3px 5px;"><input type="checkbox" class="showhide" id="sheet" checked>  Sheet</div>
        <div style="margin: 3px 5px;"><input type="checkbox" class="showhide" id="report" checked> Report</div>
        <div style="margin: 3px 5px;"><input type="checkbox" class="showhide" id="newWpt" checked> New Button</div>
        <div style="margin: 3px 5px;"><input type="checkbox" class="showhide" id="openWpt" checked> Open Button</div>
        <div style="margin: 3px 5px;"><input type="checkbox" class="showhide" id="saveWpt" checked> Save Button</div>
        <div style="margin: 3px 5px;"><input type="checkbox" class="showhide" id="message" checked> Message </div>
        <div style="margin: 3px 5px;"><input type="checkbox" class="showhide" id="fullScreen" checked> FullScreen</div>
        <div style="margin: 3px 5px;"><input type="checkbox" class="showhide" id="localeSwitch" checked> Language Switch</div>
        <div style="margin: 3px 5px;"><input type="checkbox" class="showhide" id="menuBar" checked> Right Menu</div>
        <div style="margin: 3px 5px;"><input type="checkbox" class="showhide" id="setting" checked> Setting MenuItem</div>
        <div style="margin: 3px 5px;"><input type="checkbox" class="showhide" id="help" checked> Help MenuItem</div>
        <div style="margin: 3px 5px;"><input type="checkbox" class="showhide" id="about" checked> About MenuItem</div>
      </div>
    </div>
    <div style="display:flex; flex-direction: column; border: 1px solid #888; width: 48%; ">
      <h4 style="text-align: center; margin: 5px;"> Custom Buttons <span style="color: orangered"> (Pro Edition Only)</span></h4>
      <div style="display:flex; flex-direction: column;">
        <div style="margin: 3px 5px; display: flex; flex-direction: row;">
          <div><input type="checkbox" id="customButton1">Show Button1<span style="margin-left: 10px;">Position:</span> </div>
          <div><input type="radio" name="button1" value="left" /> Left</div>
          <div><input type="radio" name="button1" value="center" /> Center</div>
          <div><input type="radio" name="button1" value="right" /> Right</div>
        </div>
        <div style="margin: 3px 5px; display: flex; flex-direction: row;">
          <div><input type="checkbox" id="customButton2">Show Button2<span style="margin-left: 10px;">Position:</span> </div>
          <div><input type="radio" name="button2" value="left" /> Left</div>
          <div><input type="radio" name="button2" value="center" /> Center</div>
          <div><input type="radio" name="button2" value="right" /> Right</div>
        </div>
        <div style="margin: 3px 5px; display: flex; flex-direction: row;">
          <div><input type="checkbox" id="customButton3">Show Select<span style="margin-left: 10px;">Position:</span> </div>
          <div><input type="radio" name="button3" value="left" /> Left</div>
          <div><input type="radio" name="button3" value="center" /> Center</div>
          <div><input type="radio" name="button3" value="right" /> Right</div>
        </div>
      </div>
      <div style="margin: 5px;">Event : <span id="eventMessage" style="color: red;"></span> </div>
    </div>
  </div>

  <div style="display:flex; flex-direction: row; margin-bottom: 10px; " >
    <div style="margin: 10px;"> Change Header Color:</div>
    <input type="button" class="colorButton" value="pink" style="margin: 5px; height:25px; background-color: pink;" />
    <input type="button" class="colorButton" value="grey" style="margin: 5px; height:25px; background-color: grey;" />
    <input type="button" class="colorButton" value="lightblue" style="margin: 5px; height:25px; background-color: lightblue;" />
    <input type="button" class="colorButton" value="lightgreen" style="margin: 5px; height:25px; background-color: lightgreen;" />
  </div>

  <div style="width:98%; height:300px; margin: auto;">
    <web-pivot-table
        options='{"leavePageWarning": 0}'>
    </web-pivot-table>
  </div>
</body>

</html>

```
