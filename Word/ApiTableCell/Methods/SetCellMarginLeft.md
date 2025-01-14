# SetCellMarginLeft

Specifies an amount of space which will be left between the left extent of the cell contents and the border of a specific table cell within a table.<br>Inherited From: [ApiTableCellPr#SetCellMarginLeft](../../ApiTableCellPr/Methods/SetCellMarginLeft.md)

## Syntax

expression.SetCellMarginLeft(nValue);

`expression` - A variable that represents a [ApiTableCell](../ApiTableCell.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Description** |
| ------------- | ------------- | ------------- | ------------- |
| nValue | Required | [twips](../../../Enumerations/twips.md) | The value for the amount of space to the left extent of the cell measured in twentieths of a point (1/1440 of an inch). If this value is null, then default table cell left margin will be used, otherwise the table cell left margin will be overridden with the specified value for the current cell. |

## Returns

This method doesn't return any data.

## Example

This example specifies an amount of space which will be left between the left extent of the cell contents and the border of a specific table cell within a table.

```javascript
builder.CreateFile("docx");
var oDocument = Api.GetDocument();
var oParagraph = oDocument.GetElement(0);
var oTableStyle = oDocument.CreateStyle("CustomTableStyle", "table");
oTableStyle.SetBasedOn(oDocument.GetStyle("Bordered"));
var oTable = Api.CreateTable(3, 3);
oTable.SetWidth("percent", 100);
var oCell = oTable.GetRow(0).GetCell(0);
oCell.SetCellMarginLeft(720);
oCell.GetContent().GetElement(0).AddText("This is just a sample text to show that the left cell margin is 36 points.");
oTable.SetStyle(oTableStyle);
oDocument.Push(oTable);
builder.SaveFile("docx", "SetCellMarginLeft.docx");
builder.CloseFile();
```