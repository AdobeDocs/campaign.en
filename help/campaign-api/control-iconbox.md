# Iconbox

List of icons which enable multiple page selection.

![Iconbox control](assets/iconbox.05daa4bf.png)

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

Each container sub-element represents a page. Example:

```xml
<container name="iconbox" type="iconbox">
   <container colcount="3" label="Header">
     ...
   </container>
   <container img="ncm:ctprop.bmp" label="Intro">
     ...
   </container>
   <container img="ncm:subsection.bmp" label="Event">
     ...
   </container>
   <container img="ncm:book.bmp" label="Selection">
     ...
   </container>
   <container img="nms:contacts.bmp" label="Services">
     ...
   </container>
   <container img="nms:contacts.bmp" label="Mail footer ">
     ...
   </container>
 </container>
```
