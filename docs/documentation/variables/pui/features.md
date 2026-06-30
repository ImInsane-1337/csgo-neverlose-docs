# Features

Some of the features that are the same for every version of pui.

## pui.traverse(t, func)

`pui.traverse()` iterates through the nested table and returns each pui_element it contains and a path to it. This function is not really related to UI, but it can come in handy when using the config system.

```
local menu = {
    enable = pui.switch("General", "Master")
    rage = {
        switch = pui.switch("Rage", "Enable"),
    },
    visuals = {
        color = pui.color_picker("Group", "Color"),
    },
    misc = {
        combo = pui.combo("Group", "Combo", {"A", "B", "C"}),
    }
}

-- will print path to each element and its name
pui.traverse(menu, function(element, path)
    local text_path = table.concat(path, ".")
    print(text_path, element.name)
end)
```
