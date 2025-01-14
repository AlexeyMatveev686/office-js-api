# SetColumnBackgroundColor

Sets the background color to all cells in the column containing the current cell.

## Syntax

expression.SetColumnBackgroundColor(r, g, b, bNone);

`expression` - A variable that represents a [ApiTableCell](../ApiTableCell.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Description** |
| ------------- | ------------- | ------------- | ------------- |
| r | Required | [byte](../../../Enumerations/byte.md) | Red color component value. |
| g | Required | [byte](../../../Enumerations/byte.md) | Green color component value. |
| b | Required | [byte](../../../Enumerations/byte.md) | Blue color component value. |
| bNone | Required | Boolean | Defines that background color will not be set. |

## Returns

Boolean

## Example

This example sets the background color to all cells in the column containing the cell.

```javascript
builder.CreateFile("docx");
var oDocument = Api.GetDocument();
var oTableStyle = oDocument.CreateStyle("CustomTableStyle", "table");
oTableStyle.SetBasedOn(oDocument.GetStyle("Bordered"));
var oTable = Api.CreateTable(4, 2);
oTable.SetWidth("percent", 100);
oTable.SetStyle(oTableStyle);
var oCell = oTable.GetRow(0).GetCell(0);
oCell.SetColumnBackgroundColor(255, 111, 61, false);
oDocument.Push(oTable);
builder.SaveFile("docx", "SetColumnBackgroundColor.docx");
builder.CloseFile();
```