# LinkListChoice

Choice of one or more entities.

## Properties

**backColor - string** Background color (btnshadow, white).

**border - string** Changes the control outline style (solid, double, inset, outset, none).

**dblClickAction - string** Name of the form to open on the double-click.

**font-size - integer** Changes the font size.

**label - string** Associated label.

**multiSelection - boolean** Authorizes multiple selection

**nolabel - boolean** Hides the associated label.

**readOnly - boolean** Forces the control to read only.

**serialize - boolean** Saves the last selection in the user configuration.wu

**xpath-link - string** Link of the list.

## Remarks

Examples:

```xml
      <input xpath="." type="linkListChoice" xpath-link="operator">
  <input xpath="[/]"  label="Operator or named right "/>
  <input xpath="@type"/>
  <input xpath="comment"/>
  <sysFilter>
    <condition expr="@type <> 1"/>
  </sysFilter>
  <orderBy>
    <node expr="@type"/>
  </orderBy>
</input>
```
