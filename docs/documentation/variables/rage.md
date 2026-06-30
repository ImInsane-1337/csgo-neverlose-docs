# 💢rage

## Structs:

## 🔗 antiaim

### :get_max_desync

`rage.antiaim:get_max_desync():` `number`

Returns the maximum amount of desync.

### :get_rotation

`rage.antiaim:get_rotation([value: boolean]):` `number`
NameTypeDescription
| **value** | `boolean` | Optional. If `true`, fake rotation will be returned. |

Returns the current anti-aim rotation.

### :get_target

`rage.antiaim:get_target([return_fr: boolean]):` `number`
NameTypeDescription
| **return_fr** | `boolean` | Optional. If `true`, freestanding yaw will be returned. |

Returns the at target yaw rotation or nil if not available.

### :inverter

`rage.antiaim:inverter([value: boolean]):` `boolean`
NameTypeDescription
| **value** | `boolean` | Optional. Inverter state. |

Gets or sets the state of the anti-aim inverter.

### :override_hidden_pitch

`rage.antiaim:override_hidden_pitch(value: number):` `number`
NameTypeDescription
| **value** | `number` | Hidden pitch value. |

Overrides the hidden pitch to the desired value.

### :override_hidden_yaw_offset

`rage.antiaim:override_hidden_yaw_offset(value: number):` `number`
NameTypeDescription
| **value** | `number` | Hidden yaw offset value. |

Overrides the hidden yaw offset to the desired value.

## 🔗 exploit

### :get

`rage.exploit:get():` `number`

Returns the exploit charge as a unit interval (value in the range [0, 1]).

### :allow_charge

`rage.exploit:allow_charge([value: boolean])`
NameTypeDescription
| **value** | `boolean` | Optional. If `true`, allows exploit charge. If `false`, blocks exploit charge. Defaults to `true` |

Allows/blocks exploit charge.

### :allow_defensive

`rage.exploit:allow_defensive([value: boolean])`
NameTypeDescription
| **value** | `boolean` | Optional. If `true`, allows the cheat to discharge defensive exploit. If `false`, blocks defensive exploit discharge. Defaults to `true` |

Allows/blocks defensive exploit discharge.

### :force_teleport

`rage.exploit:force_teleport()`

### :force_charge

`rage.exploit:force_charge()`
[Previouspanorama](docs/documentation/variables/panorama.md)[Nextrender](docs/documentation/variables/render.md)
Last updated 2 years ago
