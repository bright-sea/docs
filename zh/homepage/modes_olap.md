---
title: OLAP Mode
content_title: OLAP Mode (Microsoft SSAS, Mondrian, icCube, OLAPY)
---
In OLAP mode, all source data are in OLAP server and all calculations are in OLAP engine on server as well. 
WebPivotTable translates user's pivot selections to a MDX query to OLAP cubes, then render responses as pivot grid or pivot charts.
There is no limitation of source data size. The data size and performance are all depends on OLAP server.

There are lots of OLAP engine on market, some are commercial, some are open sources. Microsoft SSAS is most popular one. Mondrain is most popular open source OLAP engine.
Others, like icCube and OLAPY.

WebPivotTable support all these OLAP engines.
