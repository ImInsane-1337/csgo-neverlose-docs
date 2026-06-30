# ✨materials

## Example available!
[⚙️Materials](docs/useful_information/script_examples/materials.md)
## Functions:

### get

`materials.get(path: string[, force_load: boolean]):` `Material`
NameTypeDescription
| **path** | `string` | Directory to the specified material |
| **force_load** | `force_load` | Loads the material if not loaded |

Returns the material object in the specified path.

### get_materials

`materials.get_materials(partial_path: string[, force_load: boolean, callback: function]):` `table`
NameTypeDescription
| **partial_path** | `string` | Directory to the specified materials |
| **force_load** | `force_load` | Loads each material if not loaded |
| **callback** | `function` | A callback with a pointer to the material object as the argument |

If the callback is nil, it returns the table of material objects along the specified path. Otherwise the callback will be called. Access the material object using the arguments of the specified callback.

### create

`materials.create(name: strings, key_values: string):` `Material`
NameTypeDescription
| **name** | `string` | New material name |
| **key_values** | `string` | New material values |

Creates and returns a new material object

## 🔗 struct Material

### :get_name

`material:get_name():` `string`

Returns the name of the material.

### :get_texture_group_name()

`material:get_texture_group_name():` `string`

Returns the texture group name of the material.

### :var_flag

`material:var_flag(flag: number[, value: boolean]):` `boolean`
NameTypeDescription
| **flag** | `number` | Material var flag |
| **value** | `boolean` | New material var flag value |

Gets or sets the value of the material var flag.

### :shader_param

`material:shader_param(name: string[, value: any]):` `any`
NameTypeDescription
| **name** | `string` | Shader parameter name |
| **value** | `any` | New shader parameter value |

Gets or sets the value of the material shader parameter.

### :color_modulate

`material:color_modulate([color: color])`
NameTypeDescription
| **color** | `color` | New color modulation value |

Gets or sets the material color modulation value.

### :alpha_modulate

`material:alpha_modulate([alpha: number])`
NameTypeDescription
| **alpha** | `number` | New alpha modulation value |

Gets or sets the material alpha modulation value.

### :is_valid

`material:is_valid():` `boolean`

Returns `true` if the material is valid.

### :reset

`material:reset()`

Resets the material properties to its original values along with discarding the override.

### :override

`material:override(mat: Material)`
NameTypeDescription
| **mat** | `Material` | Material object with the needed properties |

Overrides material properties to properties from another material without setting them.


[Previousjson](docs/documentation/variables/json.md)[Nextmath](docs/documentation/variables/math.md)
Last updated 3 years ago
