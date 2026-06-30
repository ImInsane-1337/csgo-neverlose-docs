# ⌚common

## Functions:

### get_date
[Date & time formats cheatsheetDevhints.io cheatsheets](https://devhints.io/datetime)
`common.get_date(format: string[, unix_time: number]):` `string`
NameTypeDescription
| **format** | `string` | Date format (`strftime`) |
| **unix_time** | `number` | Optional. Unix-format time |

Returns the formatted date.

### get_unixtime

`common.get_unixtime():` `number`

Returns the number of seconds that have elapsed since the unix epoch (1 January 1970 00:00:00)

### get_timestamp

`common.get_timestamp():` `number`

Returns high precision timestamp in milliseconds.

### get_system_time

`common.get_system_time():` `table`

Returns the windows time as a table containing the `year`, `month`, `day`, `hours`, `minutes`, and `seconds` values.

### get_product_version

`common.get_product_version():` `number`

Returns the product version of the game client.

### get_game_directory

`common.get_game_directory():` `string`

Returns the path to the game client folder.

### get_map_data

`common.get_map_data():` `table`

Returns a table containing the `name`, `shortname`, and `group` values.

### get_username

`common.get_username():` `string`

Returns your Neverlose username.

### get_config_name

`common.get_config_name():` `string`

Returns the name of the currently loaded config.

### get_active_scripts

`common.get_active_scripts():` `table`

Returns a table of strings containing the names of the loaded scripts.

### get_mouse_wheel_delta

`common.get_mouse_wheel_delta():` `number`

Returns a value that indicates the amount that the mouse wheel has changed.

### is_in_thirdperson

`common.is_in_thirdperson():` `boolean`

Returns `true` if the camera is in thirdperson.

### reload_script

`common.reload_script()`

Reloads current script.

### unload_script

`common.unload_script()`

Unloads current script.

### force_full_update

`common.force_full_update()`

Forces the server to send a full update packet.

### set_clan_tag

`common.set_clan_tag(text: string)`
NameTypeDescription
| **text** | `string` | New clan tag |

Sets your in-game clan tag.

### set_name

`common.set_name(text: string)`
NameTypeDescription
| **text** | `string` | New name |

Sets your in-game name.

### add_event

`common.add_event(text: string[, icon_name: string])`
NameTypeDescription
| **text** | `string` | Text to print to into the upper-left panel. |
| **icon_name** | `string` | Optional. Fontawesome icon name. |

Prints the text into the upper-left neverlose event panel.

### add_notify

`common.add_notify(title: string, text: string)`
NameTypeDescription
| **title** | `string` | Text to print to into the title. |
| **body** | `string` | Text to print to into the body of the notification. |

Draws the notification.

### is_button_down
[Virtual-Key Codes (Winuser.h) - Win32 appsMicrosoftLearn](https://docs.microsoft.com/en-us/windows/win32/inputdev/virtual-key-codes)
`common.is_button_down(key: number):` `boolean`
NameTypeDescription
| **key** | `number` | Key to check |

Returns `true` if the button is down, or nil on failure.

### is_button_released

`common.is_button_released(key: number):` `boolean`
NameTypeDescription
| **key** | `number` | Key to check |

Returns `true` if the button is released, or nil on failure.




[Previouscolor](docs/documentation/variables/color.md)[Nextcvar](docs/documentation/variables/cvar.md)
Last updated 2 years ago
