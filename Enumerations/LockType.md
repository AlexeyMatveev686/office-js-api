# LockType

The lock type applied to the inline text content control.

## Type

String

## Properties

- "contentLocked" - content cannot be edited.
- "sdtContentLocked" - content cannot be edited and the container cannot be deleted.
- "sdtLocked" - the container cannot be deleted.

## Example

This example sets lock type "sdtContentLocked" for inline content control.

```javascript
oInlineLvlSdt.SetLock("sdtContentLocked");
```