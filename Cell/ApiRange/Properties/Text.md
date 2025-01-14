# Text

Returns the text from the first cell of the specified range or sets it to this cell.

## Syntax

expression.Text;

`expression` - A variable that represents a [ApiRange](../ApiRange.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Description** |
| ------------- | ------------- | ------------- | ------------- |
| data | Required | String &#124; Boolean &#124; Number &#124; Array<String &#124; Boolean &#124; Number> &#124; Array<Array<String &#124; Boolean &#124; Number>> | The general value for the cell or cell range. |

## Returns

String &#124; Array<Array<String>>

## Example

This example sets a text to cells.

```javascript
builder.CreateFile("xlsx");
var oWorksheet = Api.GetActiveSheet();
oWorksheet.GetRange("B1").Text = "2";
oWorksheet.GetRange("B2").Text = "2";
oWorksheet.GetRange("A3").Text = "2x2=";
oWorksheet.GetRange("B3").Text = "=B1*B2";
builder.SaveFile("xlsx", "Text.xlsx");
builder.CloseFile();
```