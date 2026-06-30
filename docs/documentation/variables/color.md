# 🌈color

## Example available!
[⚙️Color](docs/useful_information/script_examples/color.md)
## Functions:

### :clone

`color_object:clone():` `color`

Creates and returns a copy of the color object.

### :init

`color_object:init(r: number, g: number, b: number, a: number):` `color`

> 📌 Available overloads (`RGBA`):
> color() -> `255`, `255`, `255`, `255`
> color(`200`) -> `200`, `200`, `200`, `255`
> color(`255`, `160`) -> `255`, `255`, `255`, `160`
> color(`255`, `195`, `25`) -> `255`, `195`, `25`, `255`
> color(`255`, `195`, `25`, `200`) -> `255`, `195`, `25`, `200`


NameTypeDescription
| **r** | `number` | New R color range |
| **g** | `number` | New G color range |
| **b** | `number` | New B color range |
| **a** | `number` | New A color range |

`color_object:init(value: string):` `color`

> 📌 Available overloads (`HEX` -> `RGBA`):
> color '`C8`' -> `200`, `200`, `200`, `255`
> color '`FF``A0`' -> `255`, `255`, `255`, `160`
> color '`FFC319`' -> `255`, `195`, `25`, `255`
> color '`AABBCCDD`' -> `170`, `187`, `204`, `221`


NameTypeDescription
| **value** | `string` | HEX string value (Format: `AABBCCDD` including all available overloads) |

Overwrites the color's ranges. Returns itself.

### :as_fraction

`color_object:as_fraction(r: number, g: number, b: number, a: number):` `color`
NameTypeDescription
| **r** | `number` | New R color range as a percentage in the range [0.0, 1.0] |
| **g** | `number` | New G color range as a percentage in the range [0.0, 1.0] |
| **b** | `number` | New B color range as a percentage in the range [0.0, 1.0] |
| **a** | `number` | New A color range as a percentage in the range [0.0, 1.0] |

Overwrites the color's ranges using the fraction values. Returns itself.

### :as_int32

`color_object:as_int32(value: number):` `color`
NameTypeDescription
| **value** | `number` | int32 color value |

Overwrites the color's ranges converting the int32 value to RGBA values. Returns itself.

### :as_hsv

`color_object:as_hsv(h: number, s: number, v: number, a: number):` `color`
NameTypeDescription
| **h** | `number` | Hue color range [0.0, 1.0] |
| **s** | `number` | Saturation color range [0.0, 1.0] |
| **v** | `number` | Value color range [0.0, 1.0] |
| **a** | `number` | Alpha color range [0.0, 1.0] |

Overwrites the color's ranges converting the HSV to RGBA values. Returns itself.

### :as_hsl

`color_object:as_hsl(h: number, s: number, l: number, a: number):` `color`
NameTypeDescription
| **h** | `number` | Hue color range [0.0, 1.0] |
| **s** | `number` | Saturation color range [0.0, 1.0] |
| **l** | `number` | Lightness color range [0.0, 1.0] |
| **a** | `number` | Alpha color range [0.0, 1.0] |

Overwrites the color's ranges converting the HSL to RGBA values. Returns itself.

### :to_fraction

`color_object:to_fraction():` `number`, `number`, `number`, `number`

Returns the r, g, b, and a ranges of the color as a percentage in the range of [0.0, 1.0].

### :to_hex

`color_object:to_hex():` `string`

Returns the HEX string representing the color.

### :to_int32

`color_object:to_int32():` `number`

Returns the int32 value representing the color.

### :to_hsv

`color_object:to_hsv():` `number`, `number`, `number`

Returns the HSV representation of the color.

### :to_hsl

`color_object:to_hsl():` `number`, `number`, `number`

Returns the HSL representation of the color.

### :lerp

`color_object:lerp(other: color, weight: number):` `color`
NameTypeDescription
| **other** | `color` | The color to interpolate to |
| **weight** | `number` | A value between 0 and 1 that indicates the weight of **other** |

Returns the linearly interpolated color between two colors by the specified weight.

### :grayscale

`color_object:grayscale([ weight: number ]):` `color`
NameTypeDescription
| **weight** | `number` | Optional. A value between 0 and 1 that indicates the weight of **grayscale** |

Returns the grayscaled color.

### :alpha_modulate

`color_object:alpha_modulate(alpha: number):` `color`
NameTypeDescription
| **alpha** | `number` | Alpha color range [0, 255] |

Returns the current color with an overridden Alpha color range.

### :unpack

`color_object:unpack():` `number`, `number`, `number`, `number`

Returns the r, g, b, and a values of the color. Note that these fields can be accessed by indexing r, g, b, and a.
[Previousbit](docs/documentation/variables/bit.md)[Nextcommon](docs/documentation/variables/common.md)
Last updated 3 years ago
