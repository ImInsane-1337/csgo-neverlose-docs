# 🗳️events

## Functions:

Available cheat events can be found [here](docs/documentation/events.md).

### :set

`events.event_name:set(callback: function)`
NameTypeDescription
| **callback** | `function` | Lua function to call |

Sets the callback for the specified event. The registered function will be called every time the specified event occurs.

### :unset

`events.event_name:unset(callback: function)`
NameTypeDescription
| **callback** | `function` | Lua function that was passed to the `:set` function |

Unsets the callback that was set via the `:set` function from the specified event.

### :call

`events.event_name:call(...)`
NameTypeDescription
| **...** |  | Arguments to be passed by the callback |

Fires the specified event.

### Alternative behavior:

### :__call

`events.event_name(callback: function[, state: boolean])`
NameTypeDescription
| **callback** | `function` | Lua function to call |
| **state** | `boolean` | Optional. Callback state. If not specified then toggles the callback state for the specified function. |

Sets / unsets the callback for the specified event.
[Previousesp](docs/documentation/variables/esp.md)[Nextfiles](docs/documentation/variables/files.md)
Last updated 3 years ago
