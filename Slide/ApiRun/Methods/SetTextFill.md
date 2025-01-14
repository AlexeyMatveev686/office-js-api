# SetTextFill

Sets the text fill to the current text run.
<br>Inherited From: [ApiTextPr#SetTextFill](../../ApiTextPr/Methods/SetTextFill.md)

## Syntax

expression.SetTextFill(oApiFill);

`expression` - A variable that represents a [ApiRun](../ApiRun.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Description** |
| ------------- | ------------- | ------------- | ------------- |
| oApiFill | Required | [ApiFill](../../ApiFill/ApiFill.md) | The color or pattern used to fill the text color. |

## Returns

[ApiTextPr](../../ApiTextPr/ApiTextPr.md)

## Example

This example sets the text fill to the current text run.

```javascript
builder.CreateFile("pptx");
var oPresentation = Api.GetPresentation();
var oSlide = oPresentation.GetSlideByIndex(0);
oSlide.RemoveAllObjects();
var oFill = Api.CreateSolidFill(Api.CreateRGBColor(255, 111, 61));
var oStroke = Api.CreateStroke(0, Api.CreateNoFill());
var oShape = Api.CreateShape("flowChartMagneticTape", 300 * 36000, 130 * 36000, oFill, oStroke);
oShape.SetPosition(608400, 1267200);
var oDocContent = oShape.GetDocContent();
var oParagraph = oDocContent.GetElement(0);
var oRun = Api.CreateRun();
oRun.AddText("This is just a sample text. ");
oParagraph.AddElement(oRun);
oRun = Api.CreateRun();
oFill = Api.CreateSolidFill(Api.CreateRGBColor(51, 51, 51));
oRun.SetTextFill(oFill);
oRun.AddText("This is a text run with the black text.");
oParagraph.AddElement(oRun);
oSlide.AddObject(oShape);
builder.SaveFile("pptx", "SetTextFill.pptx");
builder.CloseFile();
```