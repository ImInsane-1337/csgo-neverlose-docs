# 👩‍💻esp

## Example available!
[⚙️ESP](docs/useful_information/script_examples/esp.md)
## Class names

Available ESP classes: `enemy`, `team`, `self`

## Functions:

### :new_text

`esp.esp_class:new_text(name: string, preview: string, callback: function):` `ESPGroup`
NameTypeDescription
| **name** | `string` | ESP element picker text |
| **preview** | `string` | ESP preview text |
| **callback** | `function` | Function that will be called for each entity while drawing the ESP |

Registers ESP text to the specified class. The callback function is called every frame. It is passed an entity pointer. Return a string in order to manage the output.

### :new_bar

`esp.esp_class:new_bar(name: string, callback: function):` `ESPGroup`
NameTypeDescription
| **name** | `string` | ESP element picker text |
| **callback** | `function` | Function that will be called for each entity while drawing the ESP |

Registers an ESP bar to the specified class. The callback function is called every frame. Access the entity pointer using the arguments of the specified callback. Return a boolean followed by the number in the range [0.0, 1.0].

### :new_item

`esp.esp_class:new_item(name: string):` `ESPGroup`
NameTypeDescription
| **name** | `string` | ESP element picker text |

Registers an ESP item that is neither text nor a bar.

#### 🔗 struct ESPGroup
NameTypeDescription
| **get** | `function` | Returns the value of the item. |
| **set** | `function` | Sets the value of the item. |
| **name** | `function` | Returns the name of the item. If the argument is present, the name is set to the new value. |
| **create** | `function` | Attaches a [group](docs/documentation/variables/ui#menugroup.md) to the current item. |


[Previousentity](docs/documentation/variables/entity.md)[Nextevents](docs/documentation/variables/events.md)
Last updated 2 years ago
