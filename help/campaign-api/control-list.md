# List

Memory list.

## Properties

**backColor - string** Background color (btnshadow, white).

**border - string** Changes the control outline style (solid, double, inset, outset, none).

**editable - boolean** Authorizes list editing.

**font-size - integer** Changes the font size.

**form - string** The editing form.

**img - string** Image for each line.

**label - string** Associated label.

**nolabel - boolean** No label.

**notitle - boolean** Does not display column titles.

**noToolbar - boolean** Hides the toolbar.

**ordered - boolean** Authorizes list scheduling.

**readOnly - boolean** Forces the control to read only.

**toobarAlign - string** horizontal \| vertical.

**toobarCaption - string** Label displayed in the toolbar.

**zoom - boolean** Displays the editing form.

**zoomOnAdd - boolean** Opens a form when a line is added.

**xpathIndex - xpath** The index of the selection will be stored in the location specified by this path.

**xpathSelection - xpath** The node where the XPATH path will be stored to reach the selected element.

## Remarks

Example 1:

```xml
      <input type="list" xpath="dataTransferStep" nolabel="true" editable="false"
       zoom="true" form="xtk:exportSource" zoomOnAdd="true" img="xtk:script.bmp">
  <input xpath="@name" colSize="15"/>
  <input xpath="@active" editable="true" colSize="15"/>
</input>
```

Example 2:

```xml
<input type="list" xpath="operator" zoom="true">
  <input xpath="@name" colSize="15"/>
  <form>
    <input xpath="@name"/>
  </form>
</input>
```
