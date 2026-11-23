# LinkEdit

Control for editing links.

![LinkEdit control](assets/linkedit.7cb7bf14.png)

## Properties

**backColor - string** Background color (btnshadow, white).

**border - string** Changes the control outline style (solid, double, inset, outset, none).

**choiceButton - boolean** Hides or shows the choice button (hidden by default).

**computeStringExpr - string** Calculated field expression.

**computestringKey - string** Updates the calculated string rather than the foreign key.

**computeStringAlias - string** Calculated string alias.

**createMode - string** Creates the link if it doesn't exist (none, inline), with the default editing mode.

**externalKey - boolean** Uses the external key.

**font-size - integer** Changes the font size.

**form - string** Forces the link editing form.

**label - string** Associated label.

**loadEntityOnChange - boolean** Reloads the entity when the link changes.

**mandatory - boolean** Denies empty values.

**noAutoComplete - boolean** Disables the autocompletion mode.

**noEdition - boolean** The link cannot be modified.

**nolabel - boolean** Hides the associated label.

**notifyPathList - string** List of XPaths separated from the linked elements by commas, to load in the context.

**noTransaction - boolean** Disables the transactional mode.

**noZoom - boolean** No link editing form.

**orderBy - element** Scheduling of choices.

**readOnly - boolean** Forces the control to read only.

**required - boolean** The field is mandatory.

**schema - string** Schema of the link.

**serialize - boolean** Saves the last selection in the user configuration.

**sysFilter - element** Limitation of choices.

**xpathMandatory - string** Path to a boolean property which indicates whether or not the link can be empty.

## Remarks

Examples:

```xml
<input xpath="operator">
  <sysFilter>
    <condition expr="@type= 1/>
  </sysFilter>
  <orderBy>
    <node expr="@name"/>
  </orderBy>
</input>

<input xpath="/tmp/recipient" type="linkEdit" label="Recipient"
       schema="nms:recipient">
```
