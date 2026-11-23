# SubFormButton

Button that opens a sub-form.

![SubFormButton control](assets/button.f0aea09a.png)

## Properties

**backColor - string** Background color (btnshadow, white).

**border - string** Changes the control outline style (solid, double, inset, outset, none).

**discardReadOnly - string** Prevents the propagation of the "read-only" property to the sub-form.

**font-size - integer** Changes the font size.

**img - string** Associated image.

**label - string** Label of the button.

**nolabel - string** Lets you align control on the label column.

**prebuildSubForm - string** Initializes the sub-form on control creation. This option is enabled by default, but it can be disabled to accelerate initial display.

**required - boolean** The field is mandatory.

## Remarks

Example:

```xml
      <input type="subformbutton" label="Advanced parameters...">
  <form label=" Advanced parameters">
    <input xpath="@stopIfTooManyRejects"/>
    <input xpath="@traceMode"/>
  </form>
</input>
```
