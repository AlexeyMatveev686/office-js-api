# RefersTo

Returns or sets a formula that the name is defined to refer to.

## Syntax

expression.RefersTo; &#124; expression.RefersTo = sRef;

`expression` - A variable that represents a [ApiName](../ApiName.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Description** |
| ------------- | ------------- | ------------- | ------------- |
| sRef | Required | String | The range reference which must contain the sheet name, followed by sign ! and a range of cells. Example: "Sheet1!$A$1:$B$2". |

## Returns

String

## Example

This example sets a formula that the name is defined to refer to.

```javascript
builder.CreateFile("xlsx");
var oWorksheet = Api.GetActiveSheet();
oWorksheet.GetRange("A1").SetValue("1");
oWorksheet.GetRange("B1").SetValue("2");
oWorksheet.GetRange("C1").SetValue("=SUM(A1:B1)");
Api.AddDefName("summa", "Sheet1!$A$1:$B$1");
var oDefName = Api.GetDefName("summa");
oDefName.RefersTo = "=SUM(A1:B1)";
oWorksheet.GetRange("A3").SetValue("The name 'summa' refers to the formula from the cell C1.");
builder.SaveFile("xlsx", "RefersTo.xlsx");
builder.CloseFile();
```