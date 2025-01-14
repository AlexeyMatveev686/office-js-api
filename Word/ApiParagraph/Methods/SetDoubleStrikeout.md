# SetDoubleStrikeout

Specifies that the contents of this paragraph are displayed with two horizontal lines through each character displayed on the line.

## Syntax

expression.SetDoubleStrikeout(isDoubleStrikeout);

`expression` - A variable that represents a [ApiParagraph](../ApiParagraph.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Description** |
| ------------- | ------------- | ------------- | ------------- |
| isDoubleStrikeout | Required | Boolean | Specifies that the contents of the current paragraph are displayed double struck through. |

## Returns

[ApiParagraph](../ApiParagraph.md)

## Example

This example specifies that the contents of this paragraph are displayed with two horizontal lines through each character displayed on the line.

```javascript
builder.CreateFile("docx");
var oDocument = Api.GetDocument();
var oParagraph = oDocument.GetElement(0);
oParagraph.AddText("This is a paragraph with the text struck out with two lines.");
oParagraph.SetDoubleStrikeout(true);
builder.SaveFile("docx", "SetDoubleStrikeout.docx");
builder.CloseFile();
```