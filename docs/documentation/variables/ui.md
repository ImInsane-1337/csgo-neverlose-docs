# 💻ui

## Example available!
[⚙️UI](docs/useful_information/script_examples/ui.md)
## Functions:

### get_alpha

`ui.get_alpha():` `number`

Returns the menu opacity as a unit interval (value in the range [0, 1]).

### get_size

`ui.get_size():` `vector`

Returns the current menu size.

### get_position

`ui.get_position():` `vector`

Returns the current menu position.

### get_mouse_position

`ui.get_mouse_position():` `vector`

Returns the current mouse position.

### get_binds

`ui.get_binds():` `table`

Returns a table of pointers to hotkeys.

#### struct Hotkey
NameTypeDescription
| **name** | `string` | Hotkey name |
| **mode** | `number` | Hotkey mode (`1`: Hold, `2`: Toggle) |
| **value** | `any` | Hotkey value |
| **active** | `boolean` | Hotkey state |
| **reference** | `MenuItem` | Pointer to the menu item |

### get_style

`ui.get_style([ name: string ]):` `color` / `table`

Returns the color of the Style Option. Pass `nil` to return a table with the style options.

### get_icon

`ui.get_icon(name: string):` `string`

Returns the unicode converted string corresponding the fontawesome icon.

### create

`ui.create(group: string):` `MenuGroup`
NameTypeDescription
| **group** | `string` | Group name |

Creates and returns a menu group object.

`ui.create(tab: string, group: string[, column: number]):` `MenuGroup`
NameTypeDescription
| **tab** | `string` | Tab name |
| **group** | `string` | Group name |
| **column** | `number` | Optional. Column ID (`1`: Left `2`: Right or `nil` for automatic alignment.) |

Creates and returns a menu group object.

### find

`ui.find(category: string, tab: string, group: string, item: string):` `MenuItem`
NameTypeDescription
| **category** | `string` | Category name, e.g. "Aimbot" or "Visuals". |
| **tab** | `string` | Tab name that belongs to the category. |
| **group** | `string` | Name of group with the item. |
| **item** | `string` | The needed item. |

Returns the `MenuItem` object that corresponds to the specified path.



`ui.find(category: string, tab: string, sub_tab: string, group: string, item: string):` `MenuItem`
NameTypeDescription
| **category** | `string` | Category name, e.g. "Aimbot" or "Visuals". |
| **tab** | `string` | Tab name that belongs to the category. |
| **sub_tab** | `string` | Sub-tab name. |
| **group** | `string` | Name of group with the item. |
| **item** | `string` | The needed item. |

Returns the `MenuItem` object that corresponds to the specified path.

`ui.find(category: string, tab: string, group: string, item: string, sub_item):` `MenuItem`
NameTypeDescription
| **category** | `string` | Category name, e.g. "Aimbot" or "Visuals". |
| **tab** | `string` | Tab name that belongs to the category. |
| **group** | `string` | Name of group with the item. |
| **item** | `string` | The item with a group (gear) attached. |
| **sub_item** | `string` | The sub-item in the item group. |

Returns the `MenuItem` object that corresponds to the specified path.



`ui.find(category: string, tab: string, sub_tab: string, group: string, item: string, sub_item):` `MenuItem`
NameTypeDescription
| **category** | `string` | Category name, e.g. "Aimbot" or "Visuals". |
| **tab** | `string` | Tab name that belongs to the category. |
| **sub_tab** | `string` | Sub-tab name. |
| **group** | `string` | Name of group with the item. |
| **item** | `string` | The item with a group (gear) attached. |
| **sub_item** | `string` | The sub-item in the item group. |

Returns the `MenuItem` object that corresponds to the specified path.

`ui.find(category: string, tab: string, group: string):` `MenuGroup`
NameTypeDescription
| **category** | `string` | Category name, e.g. "Aimbot" or "Visuals". |
| **tab** | `string` | Tab name that belongs to the category. |
| **group** | `string` | Name of the needed group. |

Returns the `MenuGroup` object that corresponds to the specified path.



`ui.find(category: string, tab: string, sub_tab_name: string, group: string):` `MenuGroup`
NameTypeDescription
| **category** | `string` | Category name, e.g. "Aimbot" or "Visuals". |
| **tab** | `string` | Tab name that belongs to the category. |
| **sub_tab** | `string` | Sub-tab name. |
| **group** | `string` | Name of the needed group. |

`ui.find(group_name: string, item_name: string):` `MenuItem`
NameTypeDescription
| **group_name** | `string` | Global group name, e.g. "Settings". |
| **item_name** | `string` | Item name, e.g. "Dpi Scale". |

Returns the `MenuItem` object that corresponds to the specified path.

`ui.find(category: string, tab: string, sub_tab: string, group: string, item_category: string, item: string):` `ESPGroup`
NameTypeDescription
| **category** | `string` |  |
| **tab** | `string` |  |
| **sub_tab** | `string` |  |
| **group** | `string` |  |
| **item_category** | `string` |  |
| **item** | `string` |  |

Returns the `ESPGroup` object that corresponds to the specified path.

This can return multiple items or `nil` on failure.

### sidebar
[Search Icons & Find the Perfect Design | Font Awesomefontawesome](https://fontawesome.com/v6/search)
`ui.sidebar([name: string, icon_name: string]):` `string`, `string`
NameTypeDescription
| **name** | `string` | Optional. Sidebar tab name |
| **icon_name** | `string` | Optional. Icon name (Brand icons are currently not supported) |

Gets or sets the sidebar tab name and an icon.

### localize

`ui.localize(lang: string, str: string[, localized: string]):` `string` / `nil`
NameTypeDescription
| **lang** | `string` | Language code. |
| **str** | `string` | String to localize or to get the localized string from. |
| **localized** | `string` | Optional. The localized variant. |

Returns the localized string for the specified language code. If `localized` is present, the `str` will be localized accordingly.

## 🔗 MenuGroup

### :switch

`group:switch(name: string[, init: boolean]):` `MenuItem`
NameTypeDescription
| **name** | `string` | Item name |
| **init** | `boolean` | Default value |

Creates and returns a menu item object, or throws an error on failure.

### :slider

`group:slider(name: string, min: number, max: number[, init: number, scale: number, tooltip: function]):` `MenuItem`
NameTypeDescription
| **name** | `string` | Item name |
| **min** | `number` | Minimum allowed value |
| **max** | `number` | Maximum allowed value |
| **init** | `number` | Default value |
| **scale** | `number` | Display value multiplier. Can be used for decimal places. |
| **tooltip** | `string / function` | A string appends itself to the display value. A function allows you to access the raw display value and displays anything it returns. |

Creates and returns a menu item object, or throws an error on failure.

### :combo

`group:combo(name: string, items: any[, ...]):` `MenuItem`
NameTypeDescription
| **name** | `string` | Item name |
| **items** | `any` | One or more comma separated values that will be added to the combo. Alternatively, a table of strings that will be added |
| **...** |  |  |

Creates and returns a menu item object, or throws an error on failure.

### :selectable

`group:selectable(name: string, items: any[, ...]):` `MenuItem`
NameTypeDescription
| **name** | `string` | Item name |
| **items** | `any` | One or more comma separated values that will be added to the combo. Alternatively, a table of strings that will be added |
| **...** |  |  |

Creates and returns a menu item object, or throws an error on failure.

### :color_picker

`group:color_picker(name: string[, color: color]):` `MenuItem`
NameTypeDescription
| **name** | `string` | Item name |
| **color** | `color` | Optional. Initial color value |

`group:color_picker(name: string, colors: table):` `MenuItem`
NameTypeDescription
| **name** | `string` | Item name |
| **colors** | `table` | Table containing tables with a string index, and those tables should contain one or multiple color objects. Check UI examples. |

Creates and returns a menu item object, or throws an error on failure.

### :button

`group:button(name: string[, callback: function, alt_style: boolean]):` `MenuItem`
NameTypeDescription
| **name** | `string` | Item name |
| **callback** | `function` | Optional. Function that will be called when the button is clicked |
| **alt_style** | `boolean` | Optional. Pass `true` to enable the alternative style for the specified button |

Creates and returns a menu item object, or throws an error on failure.

### :hotkey
[Virtual-Key Codes (Winuser.h) - Win32 appsMicrosoftLearn](https://docs.microsoft.com/en-us/windows/win32/inputdev/virtual-key-codes)
`group:hotkey(name: string[, default_key: number):` `MenuItem`
NameTypeDescription
| **name** | `string` | Item name |
| **default_key** | `number` | Optional. Default key |

Creates and returns a menu item object, or throws an error on failure.

### :input

`group:input(name: string[, text: string]):` `MenuItem`
NameTypeDescription
| **name** | `string` | Item name |
| **text** | `string` | Optional. Default value |

Creates and returns a menu item object, or throws an error on failure.

### :list

`group:list(name: string, items: any[, ...]):` `MenuItem`
NameTypeDescription
| **name** | `string` | Item name |
| **items** | `any` | One or more comma separated values that will be added to the combo. Alternatively, a table of strings that will be added |
| **...** |  |  |

Creates and returns a menu item object, or throws an error on failure.

### :listable

`group:listable(name: string, items: any[, ...]):` `MenuItem`
NameTypeDescription
| **name** | `string` | Item name |
| **items** | `any` | One or more comma separated values that will be added to the combo. Alternatively, a table of strings that will be added |
| **...** |  |  |

Creates and returns a menu item object, or throws an error on failure.

### :label

`group:label(text: string):` `MenuItem`
NameTypeDescription
| **text** | `string` | Label text |

Creates and returns a menu item object, or throws an error on failure.

### :texture

📌 Create the texture via the [:load_image](docs/documentation/variables/render#render.line_7.md) function.

`group:texture(texture: ImgObject[, size: vector, color: color, mode: string, rounding: number]):` `MenuItem`
NameTypeDescription
| **texture** | `ImgObject` | Image object |
| **size** | `vector` | Optional. Size of the image |
| **color** | `color` | Optional. Color of the texture |
| **mode** | `string` | Optional. `f` for fill, `r` for repeat |
| **rounding** | `number` | Optional. Image border rounding |

Creates and returns a menu item object, or throws an error on failure.

## 🔗 MenuItem

### :get

`item:get():` `any`

Returns the value of the menu item.

### :id

`item:id():` `number`

Returns the unique id of the menu item.

### :list

`item:list():` `table`

Returns the list of items. `combo` / `selectable` menu item objects only.

### :type

`item:type():` `string`

Returns the type of the menu item.

### :override

`item:override(value: any[, ...])`
NameTypeDescription
| **value** | `any` | The value to which the menu item will be set |
| **...** |  |  |

Overrides the item value without changing the menu / config values. If the `value` argument is `nil` or missing, the override is undone.

### :get_override

`item:get_override():` `any`

Returns the value of the menu item it's overriden to.

### :update

`item:update(...)`
NameTypeDescription
| **...** | `any` |  |

Updates the values of the menu item.

### :reset

`item:reset()`

Resets the menu item to it's original value.

### :set

`item:set(value: any[, ...])`
NameTypeDescription
| **value** | `any` | The value to which the menu item will be set |
| **...** |  |  |

Sets the value of the menu item.

### :name

`item:name([value: any])`
NameTypeDescription
| **value** | `any` | New name |

Gets or sets the name of the menu item.

### :tooltip

`item:tooltip([value: any])`
NameTypeDescription
| **value** | `any` | New tooltip text |

Gets or sets the tooltip of the menu item (depending on the presence of the `value` parameter).

### :visibility

`item:visibility([state: boolean])`
NameTypeDescription
| **state** | `boolean` | New visibility state |

Gets or sets the menu item visibility depending on the value of `state`.

### :disabled

`item:disabled([state: boolean])`
NameTypeDescription
| **state** | `boolean` | New disabled state |

Gets or sets the menu item disabled state depending on the value of `state`.

### :set_callback

`item:set_callback(callback: function[, force_call: boolean])`
NameTypeDescription
| **callback** | `function` | Function that will be called when the menu item is interacted with |
| **force_call** | `boolean` | Pass `true` to call the callback function after setup |

Sets the callback to the specified menu item.

### :unset_callback

`item:unset_callback(callback: function)`
NameTypeDescription
| **callback** | `function` | Lua function that was passed to the `:set_callback` function |

Unsets the callback that was set via the `:set_callback` function.

### :color_picker

`item:color_picker([color: color]):` `MenuItem`
NameTypeDescription
| **color** | `color` | Optional. Initial color value |

`item:color_picker([colors: table]):` `MenuItem`
NameTypeDescription
| **colors** | `table` | Table containing tables with a string index, and those tables should contain one or multiple color objects. Check UI examples. |

Attaches a color picker to the current menu item object.

### :create

`item:create():` `MenuGroup`

Attaches a group (gear) to the current menu item object.

### :parent

`item:parent():` `MenuItem` / `MenuGroup`

Returns the parent object of the menu item.
[Previousmath](docs/documentation/variables/math.md)[Nextnetwork](docs/documentation/variables/network.md)
Last updated 3 years ago
