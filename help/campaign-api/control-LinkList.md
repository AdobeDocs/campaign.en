# LinkList

Control for editing collections.

![LinkList control](assets/linklist.8b71bb0e.png)

## Properties

**addButton - boolean** Displays the add button. This option is only effective if the hideEditButtons option is enabled.

**backColor - string** Background color (btnshadow, white).

**border - string** Changes the control outline style (solid, double, inset, outset, none).

**dblClickAction - string** Name of the form to open on the double-click.

**delButton - boolean** Displays the delete button. This option is only effective if the hideEditButtons button is enabled.

**enumImage - string** Name of the system enumeration used to display the image of each line.

**font-size - integer** Changes the font size.

**form - string** Form for link editing.

**hideEditButtons - boolean** Hides the add, delete and edit buttons.

**img - string** Image.

**label - string** Associated label.

**nolabel - boolean** No label in front of the control.

**noToolbar - boolean** Hides the toolbar.

**orderBy - element** List scheduling.

**readOnly - boolean** Forces the control to read only.

**sysFilter - element** List filtering.

**toobarAlign - string** horizontal \| vertical.

**toobarCaption - string** Label displayed in the toolbar.

**xpath-link - string** Link of the list (see example on groups).

**xpathIndex - string** The selection index will be stored in the location specified by this path.

**xpathLinkEdit - string** Link for editing (see example on groups).

**zoom - boolean** Authorizes link editing.

## Remarks

Examples:

```xml
      <input type="linkList" xpath="operator" enumImage="@type" nolabel="true">
  <input xpath="@name" label="Name" colSize="30"/>
  <input xpath="@login"/>
  <sysFilter>
    <condition expr="@type=1"/>
  </sysFilter>
</input>

<input type="linkList" xpath="operator" enumImage="@type" nolabel="true">
  <input xpath="@name" label="Name" colSize="30"/>
  <input xpath="@login"/>
  <form label="Add operators">
  <input xpath="." type="linkListChoice" xpath-link="recipient" img="nms:group.bmp">
  <input xpath="@lastName"/>
  <input xpath="@firstName"/>
  </input>
  </form>
</input>

<input type="linklist" xpath="rcpGrpRel" zoom="true" label="Recipients" form="nms:recipient"
       xpath-link="rcpGroup"
       xpathLinkEdit="recipient">
  <input xpath="recipient/@lastName"/>
  <input xpath="recipient/@firstName"/>
  <input xpath="recipient/@email"/>
  <input xpath="recipient/@phone"/>
</input>
```
