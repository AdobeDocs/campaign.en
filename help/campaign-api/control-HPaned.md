# HPaned

Arranges several containers vertically.

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

Each sub-element must be a container. Each of its sub-containers can specify the percentage of the total height they want to use thanks to the height-percent property. Example:

```xml
<container type="hpaned">
  <container label="Group 1" height-percent="25"/>
    <input .../>
  </container>
  <container label="Group 2" height-percent="75"/>
    <input .../>
  </container>
</container>
```
