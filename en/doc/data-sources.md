---
title: Data Sources
description: "Data Sources"
---

Each WebPivotTable should connect to a data source.

## Memory Mode 
<p>
In memory mode, data is loaded into the browser's memory and all computations are performed in browser.
WebPivotTable can parse data from a variety of sources and run completely on its own without back-end support.
</p>
<p>
Data can come from a data file or a data file link (Csv or Excel format),
a google spread sheet or a web service which can be connected to any back end data sources, like SQL or NoSQL databases.
</p>


## OLAP Mode

<p>
OLAP (online analytical processing) infrastructures enable users to analyze multidimensional data interactively.
In OLAP mode, WebPivotTable can connect to an OLAP server that handles data and computation. WebPivotTable then acts as an interface
for pivotting and displaying the data.
</p>

<p>
There are a lot of OLAP server implementations. Microsoft SSAS is a widely used commercial solution while
open source solutions such as Mondrian, icCube and OLAPY are also supported by WebPivotTable.
</p>


