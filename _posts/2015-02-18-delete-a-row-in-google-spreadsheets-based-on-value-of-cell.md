---
title: Delete a row in google spreadsheets based on value of cell
date: 2015-02-18T15:44:49+00:00
author: MikeGrace
layout: post
permalink: /2015/02/delete-a-row-in-google-spreadsheets-based-on-value-of-cell/
categories:
  - Google
  - How to
  - JavaScript
---
I used the following google spreadsheet script to remove a bunch of rows that had a set value:

<pre>/**
 * Deletes rows in the active spreadsheet that contain 'Yes' in column A
 * For more information on using the Spreadsheet API, see
 * https://developers.google.com/apps-script/service_spreadsheet
 */
function readRows() {
 var sheet = SpreadsheetApp.getActiveSheet();
 var rows = sheet.getDataRange();
 var numRows = rows.getNumRows();
 var values = rows.getValues();

 var rowsDeleted = 0;
 for (var i = 0; i &lt;= numRows - 1; i++) {
 var row = values[i];
 if (row[0] == 'Yes') {
 sheet.deleteRow((parseInt(i)+1) - rowsDeleted);
 rowsDeleted++;
 }
 }
};

/**
 * Adds a custom menu to the active spreadsheet, containing a single menu item
 * for invoking the readRows() function specified above.
 * The onOpen() function, when defined, is automatically invoked whenever the
 * spreadsheet is opened.
 * For more information on using the Spreadsheet API, see
 * https://developers.google.com/apps-script/service_spreadsheet
 */
function onOpen() {
 var sheet = SpreadsheetApp.getActiveSpreadsheet();
 var entries = [{
 name : "Remove rows where column A is 'True'",
 functionName : "readRows"
 }];
 sheet.addMenu("Script Center Menu", entries);
};</pre>