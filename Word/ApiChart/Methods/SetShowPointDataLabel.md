# SetShowPointDataLabel

Specifies the show options for the chart data labels.

## Syntax

expression.SetShowPointDataLabel(nSeriesIndex, nPointIndex, bShowSerName, bShowCatName, bShowVal, bShowPercent);

`expression` - A variable that represents a [ApiChart](../ApiChart.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Description** |
| ------------- | ------------- | ------------- | ------------- |
| nSeriesIndex | Required | Number | The series index from the array of the data used to build the chart from. |
| nPointIndex | Required | Number | The point index from this series. |
| bShowSerName | Required | Boolean | Whether to show or hide the source table column names used for the data which the chart will be build from. |
| bShowCatName | Required | Boolean | Whether to show or hide the source table row names used for the data which the chart will be build from. |
| bShowVal | Required | Boolean | Whether to show or hide the chart data values. |
| bShowPercent | Required | Boolean | Whether to show or hide the percent for the data values (works with stacked chart types). |

## Returns

This method doesn't return any data.

## Example

This example specifies the show options for the chart data labels.

```javascript
builder.CreateFile("docx");
var oDocument = Api.GetDocument();
var oParagraph = oDocument.GetElement(0);
var oChart = Api.CreateChart("bar3D", [
	[200, 240, 280],
	[250, 260, 280]
], ["Projected Revenue", "Estimated Costs"], [2014, 2015, 2016], 4051300, 2347595, 24);
var oFill = Api.CreateSolidFill(Api.CreateRGBColor(51, 51, 51));
oChart.SetSeriesFill(oFill, 0, false);
oFill = Api.CreateSolidFill(Api.CreateRGBColor(255, 111, 61));
oChart.SetSeriesFill(oFill, 1, false);
oChart.SetVerAxisTitle("USD In Hundred Thousands", 10);
oChart.SetHorAxisTitle("Year", 11);
oChart.SetShowPointDataLabel(1, 0, false, false, true, false);
oChart.SetTitle("Financial Overview", 13);
oParagraph.AddDrawing(oChart);
builder.SaveFile("docx", "SetShowPointDataLabel.docx");
builder.CloseFile();
```