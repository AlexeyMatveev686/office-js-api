# SetStyleRowBandSize

Specifies a number of rows which will comprise each table row band for this table style.

## Syntax

expression.SetStyleRowBandSize(nCount);

`expression` - A variable that represents a [ApiTablePr](../ApiTablePr.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Description** |
| ------------- | ------------- | ------------- | ------------- |
| nCount | Required | Number | The number of rows measured in positive integers. |

## Returns

This method doesn't return any data.

## Example

This example specifies a number of rows which will comprise each table row band for this table style.

```javascript
builder.CreateFile("docx");
var oDocument = Api.GetDocument();
oDocument.RemoveAllElements();
var oTableStyle = oDocument.CreateStyle("CustomTableStyle", "table");
oTableStyle.SetBasedOn(oDocument.GetStyle("Bordered"));
var oTable = Api.CreateTable(2, 4);
oTable.SetWidth("percent", 100);
oTable.SetStyle(oTableStyle);
var oTablePr = oTableStyle.GetTablePr();
oTable.SetTableLook(true, true, true, true, true, true);
oTablePr.SetStyleRowBandSize(2);
oTableStyle.GetConditionalTableStyle("bandedRow").GetTextPr().SetBold(true);
oTable.GetRow(0).GetCell(0).GetContent().GetElement(0).AddText("Normal");
oTable.GetRow(0).GetCell(1).GetContent().GetElement(0).AddText("Normal");
oTable.GetRow(1).GetCell(0).GetContent().GetElement(0).AddText("Bold");
oTable.GetRow(1).GetCell(1).GetContent().GetElement(0).AddText("Bold");
oTable.GetRow(2).GetCell(0).GetContent().GetElement(0).AddText("Bold");
oTable.GetRow(2).GetCell(1).GetContent().GetElement(0).AddText("Bold");
oTable.GetRow(3).GetCell(0).GetContent().GetElement(0).AddText("Normal");
oTable.GetRow(3).GetCell(1).GetContent().GetElement(0).AddText("Normal");
oDocument.Push(oTable);
builder.SaveFile("docx", "SetStyleRowBandSize.docx");
builder.CloseFile();
```