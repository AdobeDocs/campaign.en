# SubFormLink

Link that opens a sub-form.

![SubFormLink control](assets/urlbutton.d1cf6f42.png)

## Properties

**backColor - string** Background color (btnshadow, white).

**border - string** Changes the control outline style (solid, double, inset, outset, none).

**discardReadOnly - string** Prevents the propagation of the "read-only" property to the sub-form.

**font-size - integer** Changes the font size.

**img - string** Associated image.

**label - string** Button label.

**nolabel - string** Lets you align the control with the label column.

**prebuildSubForm - string** Initializes the sub-form when creating the control. This option is enabled by default but it can be disabled to accelerate the initial display.

## Remarks

Example:

```xml
      <input type="subformlink" label="Advanced parameters...">
  <form label=" Advanced parameters">
    <input xpath="@stopIfTooManyRejects"/>
    <input xpath="@traceMode"/>
  </form>
</input>
```
