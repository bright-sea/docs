---
title: Server mode
content_title: Server mode
content_subtitle: (Developing ...)
---               
<p>
Memory mode has a limitation of data size as all data and calculations in browser's memory.
OLAP mode has no data size limitation but depends on an existing OLAP solution. 
Server mode is a developing new data source mode to deal with these limitations.
</p>

<p>
In server mode, both data format and calculation mechanism are the same as memory mode. 
But the difference is data are not loaded into browser's memory, instead data are loaded in a dedicated server.
And all calculations run on that server as well.
WebPivotTable serve as a client tool.
</p>
