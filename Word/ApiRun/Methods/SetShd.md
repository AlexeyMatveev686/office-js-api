# SetShd

Specifies the shading applied to the contents of the current text run.

## Syntax

expression.SetShd(sType, r, g, b);

`expression` - A variable that represents a [ApiRun](../ApiRun.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Description** |
| ------------- | ------------- | ------------- | ------------- |
| sType | Required | [ShdType](../../../Enumerations/ShdType.md) | The shading type applied to the contents of the current text run. |
| r | Required | [byte](../../../Enumerations/byte.md) | Red color component value. |
| g | Required | [byte](../../../Enumerations/byte.md) | Green color component value. |
| b | Required | [byte](../../../Enumerations/byte.md) | Blue color component value. |

## Returns

[ApiTextPr](../../ApiTextPr/ApiTextPr.md)

## Example

This example specifies the shading applied to the contents of the current text run.

```javascript
builder.CreateFile("docx");
var oDocument = Api.GetDocument();
var oParagraph = oDocument.GetElement(0);
var oRun = Api.CreateRun();
oRun.AddText("This is just a sample text. ");
oParagraph.AddElement(oRun);
oRun = Api.CreateRun();
oRun.SetShd("clear", 255, 111, 61);
oRun.AddText("This is a text run with the text shading set to orange.");
oParagraph.AddElement(oRun);
builder.SaveFile("docx", "SetShd.docx");
builder.CloseFile();
```