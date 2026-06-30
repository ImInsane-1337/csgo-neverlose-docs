# ⚙️UI

### UI Pseudocode

```
-- Pseudocode that shows most of the ui functions and how to use them

-- If you want to get a reference to an existing group or item, call .find
local double_tap_ref = ui.find("aimbot", "ragebot", "main", "double tap")

-- "ui.create" creates a group
-- in which you can add items such as switches, sliders, combos, etc.
local group_ref = ui.create("Group")

-- Some arguments can be optional, like the 2nd one in this function,
-- it will make its default value true
local switch_ref = group_ref:switch("Switch", true)

-- You can change its value
switch_ref:set(false)

-- Or you can "override" its value
-- This will allow you to change the value of the item
-- without changing its value in the menu or in the cheat's configuration
switch_ref:override(true)

-- Reset the previous override
switch_ref:override()

-- You can register a function that will be executed
-- every time the value of the item changes

-- The reference can be accessed from the arguments of the callback
switch_ref:set_callback(function(ref)
    -- You can access the value of the item by calling :get
    -- To access the value it's overriden to with :override, call :get_override
    print(string.format("New value: %s", ref:get()))
end)

-- If you want to what type of object the item is, you can call :get_type
-- print(switch_ref:type()) --> switch

-- You can attach other items to some types of items by calling :create
-- This will create and return a reference to the item group,
-- to which you can add other items
local switch_group_ref = switch_ref:create()

-- Our API offers a lot of overloads, you can either just provide a bunch of strings
-- or you can provide a table of strings
local combo_ref = switch_group_ref:combo("Combo", "Option A", "Option B", "Option C")

-- You can update the contents of combos, selectables, list, and listables with :update
combo_ref:update({"Option A"})

-- You can attach color pickers to some types of items,
-- but keep in mind that you won't be able to attach a group at the same time
local combo_color_picker_ref = combo_ref:color_picker(color(255, 0, 0, 255))

-- If you want to see what group the item belongs to, call :parent
-- print(group_ref == switch_ref:parent()) --> true
-- print(switch_group_ref == combo_ref:parent()) --> true

-- If you want to describe an item, you can call :tooltip,
-- which will display a text when you move the cursor over the item
switch_ref:tooltip("Some useful information.")

-- Further reading:
-- https://lua.neverlose.cc/documentation/variables/ui
-- DM Serene#1337 for any documentation errors
```

### Multi-Color Picker
[PreviousConVars](docs/useful_information/script_examples/convars.md)[NextEvents](docs/documentation/events.md)
Last updated 3 years ago
