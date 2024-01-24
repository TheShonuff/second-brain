---
tags:
  - sheets
---

# FillFormula



```JavaScript
function FillFormulas() { 
var spreadsheet = SpreadsheetApp.getActiveSpreadsheet().getSheetByName('Sheet1'); 

var lastRow = spreadsheet.getLastRow(); spreadsheet.getRange("C2").setFormula("=A2&\" \"&B2"); 

var fillDownRange = spreadsheet.getRange(2,3,(lastRow-1)); 

spreadsheet.getRange("C2").copyTo(fillDownRange); 
}
```
- Change `getSheetByName`
- Change `getRange` will reflect the range or column to affect.
- Change `SetFormula()` to the desired formula
- Change `FillDownRange` `getRange()` change the `3` to the number of the desired column

>[!tip] Set trigger to **on change**

