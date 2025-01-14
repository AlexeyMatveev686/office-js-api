# SetTopBorder

Specifies the border which will be displayed above a set of paragraphs which have the same set of paragraph border settings.
<br>The paragraphs of the same style going one by one are considered as a single block, so the border is added to the whole block rather than to every paragraph in this block.<br><br>Inherited From: [ApiParaPr#SetTopBorder](../../ApiParaPr/Methods/SetTopBorder.md)

## Syntax

expression.SetTopBorder(sType, nSize, nSpace, r, g, b);

`expression` - A variable that represents a [ApiParagraph](../ApiParagraph.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Description** |
| ------------- | ------------- | ------------- | ------------- |
| sType | Required | [BorderType](../../../Enumerations/BorderType.md) | The border style. |
| nSize | Required | [pt_8](../../../Enumerations/pt_8.md) | The width of the current top border measured in eighths of a point. |
| nSpace | Required | [pt](../../../Enumerations/pt.md) | The spacing offset above the paragraph measured in points used to place this border. |
| r | Required | [byte](../../../Enumerations/byte.md) | Red color component value. |
| g | Required | [byte](../../../Enumerations/byte.md) | Green color component value. |
| b | Required | [byte](../../../Enumerations/byte.md) | Blue color component value. |

## Returns

This method doesn't return any data.

## Example

This example specifies the border which will be displayed above a set of paragraphs which have the same set of paragraph border settings.

```javascript
builder.CreateFile("docx");
var oDocument = Api.GetDocument();
var oParagraph = oDocument.GetElement(0);
oParagraph.AddText("This is the first paragraph. We will add a thick orange border above it.");
oParagraph.SetTopBorder("single", 24, 0, 255, 111, 61);
builder.SaveFile("docx", "SetTopBorder.docx");
builder.CloseFile();
```