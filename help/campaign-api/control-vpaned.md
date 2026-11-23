# VPaned

Arranges several containers horizontally.

## Properties

**backColor - string** Background color (btnshadow, white).

**name - string** Container ID.

**padding-left - integer** Space in pixel to the left of the container.

**padding-right - integer** Space in pixel to the right of the container.

**padding-top - integer** Space in pixel above the container.

**padding-bottom - integer** Space in pixel below the container.

**padding - integer** Space in pixel around the container.

**readOnly - boolean** Forces control and all its descendants to read only.

## Remarks

Each sub-element has to be a container. Each sub-container can specify the percentage of the total width they want to use thanks to the width-percent property. Example:

```xml
<container type="vpaned">
  <container label="Group 1" width-percent="25"/>
    <input .../>
  </container>
  <container label="Group 2" width-percent="75"/>
    <input .../>
  </container>
</container>
```
