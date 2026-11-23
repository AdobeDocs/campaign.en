# Notebook

List of tabs to display several pages.

![Notebook control](assets/notebook.3b531a46.png)

## Properties

**backColor - string** Background color (btnshadow, white).

**name - string** Container ID.

**padding-left - integer** Space in pixel to the left of the container.

**padding-right - integer** Space in pixel to the right of the container.

**padding-top - integer** Space in pixel above the container.

**padding-bottom - integer** Space in pixel below the container.

**padding - integer** Space in pixel around the container.

**readOnly - boolean** Forces control and all its descendants to read only.

**style - string** flat \| down \| up (default).

## Remarks

Each sub-element represents a page. Examples:

```xml
      <container colspan="2" style="down" type="notebook">
   <container label="Products">
     ...
   </container>

   <container colcount="3" xpath="link">
     ...
   </container>

   <container xpath="linkCollection">
     ...
   </container>
 </container>
```
