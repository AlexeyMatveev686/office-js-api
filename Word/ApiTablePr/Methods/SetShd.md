# SetShd

Specifies the shading which shall be applied to the extents of the current table.

## Syntax

expression.SetShd(sType, r, g, b, isAuto?);

`expression` - A variable that represents a [ApiTablePr](../ApiTablePr.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Description** |
| ------------- | ------------- | ------------- | ------------- |
| sType | Required | [ShdType](../../../Enumerations/ShdType.md) &#124; [ApiFill](../../ApiFill/ApiFill.md) | The shading type applied to the extents of the current table. |
| r | Required | [byte](../../../Enumerations/byte.md) | Red color component value. |
| g | Required | [byte](../../../Enumerations/byte.md) | Green color component value. |
| b | Required | [byte](../../../Enumerations/byte.md) | Blue color component value. |
| isAuto | Optional | Boolean | The true value disables the SetShd method use. Default value is "false". |


## Returns

This method doesn't return any data.

## Example

This example specifies the shading which shall be applied to the extents of the table.

```javascript
builder.CreateFile("docx");
var oDocument = Api.GetDocument();
var oParagraph = oDocument.GetElement(0);
oParagraph.AddText("We added an orange shading to the table:");
var oTableStyle = oDocument.CreateStyle("CustomTableStyle", "table");
oTableStyle.SetBasedOn(oDocument.GetStyle("Bordered"));
var oTablePr = oTableStyle.GetTablePr();
var oTable = Api.CreateTable(3, 3);
oTablePr.SetShd("clear", 255, 111, 61, false);
oTable.SetTableLook(true, true, true, true, false, false);
oTable.SetStyle(oTableStyle);
oDocument.Push(oTable);
builder.SaveFile("docx", "SetShd.docx");
builder.CloseFile();
```