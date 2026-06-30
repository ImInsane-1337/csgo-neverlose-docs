# Main

How to create an element? There are a ton of ways, and you'll know all of them

## Creating a group

`pui.group(tab, name*, align*)` : `pui_group`

```
local group = pui.create("Visuals", "Indicators")
local switch = group:switch("Name")
```

```
-- Name only
local switch = pui.switch("Indicators", "Name")

-- Tab and name
local switch = pui.switch({"Visuals", "Indicators"}, "Name")
```



## Creating an element

`pui.element(group, ..., arg1, arg2, argn)` : `pui_element`

`group:element(..., arg1, arg2, argn)` : `pui_element`

You can use elements just like in neverlose. All arguments will be saved, and you will also be able to add more *(but there are some exceptions)*
Common example
```
local group = pui.create("Visuals", "Indicators")
local switch = group:switch("Name", true, function(gear)
    return {
        value = gear:slider("Value", 0, 10, 5)
    }
end, "Tooltip")
```

#### Exceptions for elements with list (combo, selectable, list, listable)

Due to their arguments style, you will have to modify them a bit in order to use pui features. You can still use them like they are if you don't need additional features.



## What does a pui_element contain?

`pui::element` is a table of variables that you can use in some cases.

For example: `switch.value` returns the current switch value
VariableDescription
| `.value` | Current value. Includes overridden one too. |
| `.ref` | Original neverlose reference. |
| `.color` | This table is a pui::element of your color picker. For example:  `.color.value`, `.color:set()` d |



## Children elements

Children elements are those gears or color pickers near the main elements.

If you want to add a gear elements, see this:



Definition of `children`:



Let's see.
VariableDescription
| `gear` | The gear created when you want to add children |
| `self` | The table of a main element. Be careful when using it. |
| `elements` | A table of *pui* elements you want to pass to `gear`. |
| `condition` | A global condition, that will make your children visible or invisible depending on if it's met or not. See `:depend` method for more info. |



#### Example

This example shows a switch. It contains children elements: `bar` and `button`. Also you can see, that you may operate them just like regular *pui *elements. These elements will be shown only if the main switch is enabled (`true`).



#### Accesing children elements

If you want to add a color picker, the second pui argument should be a color (it will be used as a default color)



#### Example:



#### Accessing color
