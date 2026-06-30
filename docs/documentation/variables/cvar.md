# 🎲cvar

### Example

```
cvar.mp_teammates_are_enemies:int(1)
cvar.clear:call()
```

## Functions:

### :call

`cvar_object:call(...)`
NameTypeDescription
| ... |  | Arguments passed to the callback |

Executes a ConCommand or cvar callback, passing its arguments to it.

### :int

`cvar_object:int():` `number`

`cvar_object:int(value: number[, raw: boolean ])`
NameTypeDescription
| **value** | `number` | New int value |
| **raw** | `boolean` | Optional. If `true` then the `raw` value will be set |

Gets or sets the ConVar int value.

### :float

`cvar_object:float():` `number`

`cvar_object:float(value: number[, raw: boolean ])`
NameTypeDescription
| **value** | `number` | New float value |
| **raw** | `boolean` | Optional. If `true` then the `raw` value will be set |

Gets or sets the ConVar float value.

### :string

`cvar_object:string([ value: any ]):` `string`
NameTypeDescription
| **value** | `any` | New string value. If not specified then returns the string value of the ConVar |

Gets or sets the ConVar string value.

### :set_callback

You can access the `cvar_object`, `old_value` and `new_value` by adding them to the function arguments.

You can access the `cvar_object` and `args` by adding them to the function arguments. Inside the callback, return false to prevent the command from being executed.

`cvar_object:set_callback(callback: function)`
NameTypeDescription
| **callback** | `function` | Lua function to call |

Registers the callback to the specified ConVar/Command. The registered function will be called every time the specified convar value is updated.

### :unset_callback

`cvar_object:unset_callback(callback: function)`
NameTypeDescription
| **callback** | `function` | Lua function that was passed to the `:set_callback` function |

Unregisters the callback that was set via the `:set_callback` function from the specified ConVar/Command.
[Previouscommon](docs/documentation/variables/common.md)[Nextdb](docs/documentation/variables/db.md)
Last updated 3 years ago
