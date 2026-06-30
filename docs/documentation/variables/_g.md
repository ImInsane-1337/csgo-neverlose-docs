# 🌎_G

### assert

`assert(expression: any[, text: string, ...]): any`
NameTypeDescription
| **expression** | `any` | The expression to assert. |
| **text** | `text` | The error message to throw when assertion fails. This is only type-checked if the assertion fails. |
| **...** | `any` | Any arguments past the error message will be returned by a successful assert. |

If the result of the first argument is false or nil, an error is thrown with the second argument as the message.

### error

`error(text: any[, level: number])`
NameTypeDescription
| **text** | `string` | The error message to throw. |
| **level** | `number` | The level to throw the error at. |

Throws a Lua error and breaks out of the current call stack.

### getmetatable

`getmetatable(object: any): any`
NameTypeDescription
| **object** | `any` | The value to return the metatable of. |

Returns the metatable of an object. This function obeys the metatable's __metatable field, and will return that field if the metatable has it set.

### ipairs

`ipairs(tbl: table): function, table, number`
NameTypeDescription
| **tbl** | `table` | The table to iterate over. |

Returns an iterator function for a for loop, to return ordered key-value pairs from a table.

### print

`print(text: string[, ...])`
NameTypeDescription
| **text** | `string` | Text to print into the console. |
| **...** | `any` | Optional arguments to concatenate with `text`. |

Prints the text to the console.

### print_error

`print_error(text: string[, ...])`
NameTypeDescription
| **text** | `string` | Text to print into the console. |
| **...** | `any` | Optional arguments to concatenate with `text`. |

Prints an error to the console and plays a sound.

### print_chat

`print_chat(text: string[, ...])`
NameTypeDescription
| **text** | `string` | Text to print into the in-game chat. |
| **...** | `any` | Optional arguments to concatenate with `text`. |

Prints the text to the in-game chat.

### print_raw

`print_raw(text: string[, ...])`
NameTypeDescription
| **text** | `string` | Text to print into the console. |
| **...** | `any` | Optional arguments to concatenate with `text`. |

Prints the text that can be changed in color by prepending it with `"\a"` followed by the color in the hexadecimal "RRGGBB" format. For example, `"\aFF0000Hi"` will print `"Hi"` in red.

### print_dev

`print_dev(text: string[, ...])`
NameTypeDescription
| **text** | `string` | Text to print to into the upper-left console panel. |
| **...** | `any` | Optional arguments to concatenate with `text`. |

Prints the text into the upper-left console panel.

### tonumber

`tonumber(value: any[, base: number]):` `number`
NameTypeDescription
| **value** | `any` | The value to convert. Can be a number or string. |
| **base** | `number` | Optional. The base used in the string. Can be any integer between 2 and 36, inclusive. |

Returns the numeric representation of the value with the given base, or `nil` if the conversion failed.

### tostring

`tostring(var: any):` `string`
NameTypeDescription
| **var** | `any` | The object to be converted to a string. |

Returns the string representation of the value.

### type

`type(var: any):` `string`
NameTypeDescription
| **var** | `any` | The object to get the type of. |

Returns the name of the object's type.

### unpack

`unpack(tbl: table, start_index: number, end_index: number):` `...`
NameTypeDescription
| **tbl** | `table` | The table to generate the vararg from. |
| **start_index** | `number` | Which index to start from. Optional. |
| **end_index** | `number` | Which index to end at. Optional, even if you set `start_index`. |

### xpcall

`xpcall(func: function, err_callback: function[, ...]):` `boolean`, `...`
NameTypeDescription
| **func** | `function` | The function to call initially. |
| **err_callback** | `function` | The function to be called if execution of the first fails. The error message is passed as a string. |
| **...** | `any` | Arguments to pass to the initial function. |

Attempts to call the first function. If the execution succeeds, this returns `true` followed by the returns of the function. If execution fails, this returns `false` and the second function is called with the error message.

### to_ticks

`to_ticks(time: number):` `number`
NameTypeDescription
| **time** | `number` | The seconds to convert to ticks. |

Converts time (seconds) to ticks.

### to_time

`to_time(ticks: number):` `number`
NameTypeDescription
| **ticks** | `number` | The number of ticks to convert to time. |

Converts ticks to time (seconds).

### new_class

> ℹ️ This class system makes it easier to structure code in complex projects.

`new_class():` `metatable`

Creates the new class.

> You can also create multiple structs and access one from another.
[PreviousVariables](docs/documentation/variables.md)[Nextbit](docs/documentation/variables/bit.md)
Last updated 2 years ago
