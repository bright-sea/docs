---
title: Constants
description: "Constants"
---

```
export default {
  edition: {
    FREE: "FREE",
  },

  wptFormat: {
    VERSION_3: "3.0",
    VERSION_4: "4.0",
  },

  screenSize: {
    SMALL: "SMALL",
    MEDIUM: "MEDIUM",
    LARGE: "LARGE",
  },

  modalType: {
    DATA_SOURCE: "DATA_SOURCE",
    DRILL_THROUGH: "DRILL_THROUGH",
  },

  dialogType: {
    EXPORT: "EXPORT",
    CONNECT_SOURCE: "CONNECT_SOURCE",
    OPEN_WPT: "OPEN_WPT",
    SAVE_WPT: "SAVE_WPT",
    ABOUT_ME: "ABOUT_ME",
    SETTING: "SETTING",
    SOURCE_FIELD_SETTING: "SOURCE_FIELD_SETTING",
    SHEET_FIELD_SETTING: "SHEET_FIELD_SETTING",
    SHEET_VALUE_FIELD_SETTING: "SHEET_VALUE_FIELD_SETTING",
    SHEET_CALCULATED_FIELD: "SHEET_CALCULATED_FIELD",
    SHEET_MDX_STATEMENT: "SHEET_MDX_STATEMENT",
  },

  eventType: {
    DRILL_THROUGH: "DRILL_THROUGH",
    OPEN_WPT: "OPEN_WPT",
    NEW_WPT: "NEW_WPT",
    SAVE_WPT: "SAVE_WPT",
    CONNECT_SOURCE: "CONNECT_SOURCE",
  },

  sourceMode: {
    MEMORY: "MEMORY",
    OLAP: "OLAP",
  },

  sourceType: {
    CSV: "CSV",
    EXCEL: "EXCEL",
    GSS: "GSS",
    WSDATA: "WSDATA",
    CUBE: "CUBE",
    WPT: "WPT",
  },

  fieldType: {
    NUMBER: "NUMBER",
    STRING: "STRING",
    DATE: "DATE",
    CALCULATED: "CALCULATED",
    CATEGORY: "CATEGORY",
    BOOLEAN: "BOOLEAN",

    MEASURE: "MEASURE",
    LEVEL: "LEVEL",
    MEASURES: "MEASURES",
    HIERARCHY: "HIERARCHY",
    DIMENSION: "DIMENSION",

    VALUES: "VALUES",
  },

  controlType: {
    ROWS: "rows",
    COLUMNS: "columns",
    FILTERS: "filters",
    VALUES: "values",
  },

  direction: {
    UP: "UP",
    DOWN: "DOWN",
    BEGINNING: "BEGINNING",
    END: "END",
  },

  sortBy: {
    LABEL: "LABEL",
    VALUE: "VALUE",
  },

  filterBy: {
    LABEL: "LABEL",
    VALUE: "VALUE",
    TOP: "TOP",
  },

  filterLabel: {
    FORMULA: "FORMULA",
    INCLUDES: "INCLUDES",
    EXCLUDES: "EXCLUDES",
  },

  compareOption: {
    EQUALS: "EQ",
    NOT_EQUALS: "NE",
    GREAT_THAN: "GT",
    GREAT_EQUAL: "GE",
    LESS_THAN: "LT",
    LESS_EQUAL: "LE",
    BEGIN_WITH: "BW",
    NOT_BEGIN_WITH: "NBW",
    END_WITH: "EW",
    NOT_END_WITH: "NEW",
    CONTAINS: "CO",
    NOT_CONTAINS: "NCO",
    BETWEEN: "BT",
    NOT_BETWEEN: "NB",
    TOP: "TOP",
    BOTTOM: "BOTTOM",
  },

  valueFormatCategory: {
    GENERAL: "GENERAL",
    NUMBER: "NUMBER",
    CURRENCY: "CURRENCY",
    ACCOUNTING: "ACCOUNTING",
    DATE: "DATE",
    TIME: "TIME",
    PERCENTAGE: "PERCENTAGE",
    FRACTION: "FRACTION",
    SCIENTIFIC: "SCIENTIFIC",
    TEXT: "TEXT",
    SPECIAL: "SPECIAL",
    CUSTOM: "CUSTOM",
  },

  statsOption: {
    SUM: "SUM",
    COUNT: "COUNT",
    DISTINCTCOUNT: "DISTINCTCOUNT",
    AVERAGE: "AVERAGE",
    MAX: "MAX",
    MIN: "MIN",
    MEDIAN: "MEDIAN",
    MODE: "MODE",
    STDDEV: "STDDEV",
    VARIANCE: "VARIANCE",
    PERCENTILEINC: "PERCENTILEINC",
    PERCENTILEEXC: "PERCENTILEEXC",
  },

  showAsOption: {
    NO_CALCULATION: "NO_CALCULATION",
    PERC_GRAND_TOTAL: "PERC_GRAND_TOTAL",
    PERC_COLUMN_TOTAL: "PERC_COLUMN_TOTAL",
    PERC_ROW_TOTAL: "PERC_ROW_TOTAL",
    PERC_PARENT_COLUMN: "PERC_PARENT_COLUMN",
    PERC_PARENT_ROW: "PERC_PARENT_ROW",
  },

  negativeValueFormat: {
    MINUS: "MINUS",
    PARENTHESES: "PARENTHESES",
    PARENTHESES_MINUS: "PARENTHESES_MINUS",
    RED: "RED",
    RED_MINUS: "RED_MINUS",
    RED_PARENTHESES: "RED_PARENTHESES",
    RED_PARENTHESES_MINUS: "RED_PARENTHESES_MINUS",
  },

  cellType: {
    CELL_COLHEADER: 0,
    CELL_ROWHEADER: 1,
    CELL_DATA: 2,
    CELL_SUBTOTAL: 3,
    CELL_TOTAL: 4,
  }

};

```
