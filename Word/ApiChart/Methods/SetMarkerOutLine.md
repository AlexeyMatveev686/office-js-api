# SetMarkerOutLine

Sets the outline to the marker in the specified chart series.

## Syntax

expression.SetMarkerOutLine(oStroke, nSeries, nMarker, bAllMarkers?);

`expression` - A variable that represents a [ApiChart](../ApiChart.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Description** |
| ------------- | ------------- | ------------- | ------------- |
| oStroke | Required | [ApiStroke](../../ApiStroke/ApiStroke.md) | The stroke used to create the marker outline. |
| nSeries | Required | Number | The index of the chart series. |
| nMarker | Required | Number | The index of the marker in the specified chart series. |
| bAllMarkers | Optional | Boolean | Specifies if the outline will be applied to all markers in the specified chart series. Default value is "false". |

## Returns

Boolean

## Example

This example sets the outline to the marker in the specified chart series.

```javascript
builder.CreateFile("docx");
var oDocument = Api.GetDocument();
var oParagraph = oDocument.GetElement(0);
var oChart = Api.CreateChart("scatter", [
	[200, 240, 280],
	[250, 260, 280]
], ["Projected Revenue", "Estimated Costs"], [2014, 2015, 2016], 4051300, 2347595, 24);
oParagraph.AddDrawing(oChart);
var oFill = Api.CreateSolidFill(Api.CreateRGBColor(51, 51, 51));
oChart.SetSeriesFill(oFill, 0, false);
oFill = Api.CreateSolidFill(Api.CreateRGBColor(255, 111, 61));
oChart.SetSeriesFill(oFill, 1, false);
var oStroke = Api.CreateStroke(1 * 36000, Api.CreateSolidFill(Api.CreateRGBColor(51, 51, 51)));
oChart.SetMarkerOutLine(oStroke, 1, 0, true);
builder.SaveFile("docx", "SetMarkerOutLine.docx");
builder.CloseFile();
```