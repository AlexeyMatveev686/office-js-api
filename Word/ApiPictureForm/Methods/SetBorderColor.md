# SetBorderColor

Sets the border color to the current form.<br>Inherited From: [ApiFormBase#SetBorderColor](../../ApiFormBase/Methods/SetBorderColor.md)

## Syntax

expression.SetBorderColor(r, g, b, bNone);

`expression` - A variable that represents a [ApiPictureForm](../ApiPictureForm.md) class.

## Parameters

| **Name** | **Required/Optional** | **Data type** | **Description** |
| ------------- | ------------- | ------------- | ------------- |
| r | Required | [byte](../../../Enumerations/byte.md) | Red color component value. |
| g | Required | [byte](../../../Enumerations/byte.md) | Green color component value. |
| b | Required | [byte](../../../Enumerations/byte.md) | Blue color component value. |
| bNone | Required | Boolean | Defines that border color will not be set. |

## Returns

Boolean

## Example

This example sets the border color to the current form.

```javascript
builder.CreateFile("docx");
var oDocument = Api.GetDocument();
var oPictureForm = Api.CreatePictureForm({"key": "Personal information", "tip": "Upload your photo", "required": true, "placeholder": "Photo", "scaleFlag": "tooBig", "lockAspectRatio": true, "respectBorders": false, "shiftX": 50, "shiftY": 50});
oPictureForm.SetImage("https://api.onlyoffice.com/content/img/docbuilder/examples/user-profile.png");
var oParagraph = oDocument.GetElement(0);
oParagraph.AddElement(oPictureForm);
oPictureForm.SetBorderColor(255, 111, 61);
builder.SaveFile("docx", "SetBorderColor.docx");
builder.CloseFile();
```