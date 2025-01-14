# GetClassType

Returns a type of the ApiTableCellPr class.

## Syntax

expression.GetClassType();

`expression` - A variable that represents a [ApiTableCellPr](../ApiTableCellPr.md) class.

## Parameters

This method doesn't have any parameters.

## Returns

String

## Example

This example gets a class type and pastes it into the presentation.

```javascript
builder.CreateFile("docx");
var oDocument = Api.GetDocument();
var oTableStyle = oDocument.CreateStyle("CustomTableStyle", "table");
oTableStyle.SetBasedOn(oDocument.GetStyle("Bordered"));
var oTable = Api.CreateTable(3, 3);
oTable.SetWidth("percent", 100);
var oTableCellPr = oTableStyle.GetTableCellPr();
oTable.SetStyle(oTableStyle);
oDocument.Push(oTable);
var sClassType = oTableCellPr.GetClassType();
var oParagraph = oDocument.GetElement(0);
oParagraph.AddText("Class Type = " + sClassType);
builder.SaveFile("docx", "GetClassType.docx");
builder.CloseFile();
```