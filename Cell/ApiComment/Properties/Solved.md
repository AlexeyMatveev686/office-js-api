# Solved

Checks if a comment is solved or not or marks a comment as solved.

## Syntax

expression.Solved; &#124; expression.Solved = bSolved;

`expression` - A variable that represents a [ApiComment](../ApiComment.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Description** |
| ------------- | ------------- | ------------- | ------------- |
| bSolved | Required | Boolean | Specifies if a comment is solved or not. |

## Returns

Boolean

## Example

This example marks a comment as solved.

```javascript
builder.CreateFile("xlsx");
var oWorksheet = Api.GetActiveSheet();
oWorksheet.GetRange("A1").SetValue("1");
var oRange = oWorksheet.GetRange("A1");
var oComment = oRange.AddComment("This is just a number.", "John Smith");
oWorksheet.GetRange("A3").SetValue("Comment is solved: ");
oComment.Solved = true;
oWorksheet.GetRange("B3").SetValue(oComment.Solved);
builder.SaveFile("xlsx", "Solved.xlsx");
builder.CloseFile();
```