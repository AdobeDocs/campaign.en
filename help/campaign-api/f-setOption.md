# setOption

Changes the value of an option in the options table.

```text
setOption (name, value, description )
```

## Parameters

**name** Name of the option.

**value** Value of the option.

**description** Value of the description (optional).

## Return value

None.

## Remarks

The different data type are:

* text,
* integer,
* floating point,
* Date + Time,
* longtext

Note that longText and integer type can not be created from the API.

For these two types, you first need to create the option from the console then you can manage the values via the setOption API.

**Example:**

```javascript
   			//create option of type Date+Time'
   			var ourDate = getCurrentDate();
   			setOption("testOptionDateTime",ourDate,"option of type Date+Time");
   			   			
   			//create option of type Floating point'
   			setOption("testOptionFloat",1,"option of type Floating point");
   			
   			//create option of type Text'
   			setOption("testOptionText","I am a text","option of type Text");   			
   		
```

If you want to delete the description, you need to call the API with an empty description (setOption(name,value,"")).

## Features

**Available in:**

* Content management
* Delivery properties
* Typology rule
* JSSP
* SOAP Method
* WebApp
* Workflow
