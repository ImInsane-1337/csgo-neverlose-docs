# 🎨render

## Functions:

### screen_size

`render.screen_size():` `vector`

### camera_position

`render.camera_position():` `vector`

Returns the camera position vector.

### camera_angles

`render.camera_angles([angles: vector]):` `vector`
NameTypeDescription
| **angles** | `vector` | New camera angles |

Returns or sets the camera angles.

### world_to_screen

`render.world_to_screen(position: vector):` `vector`
NameTypeDescription
| **position** | `vector` | Position in world space |

📌 Note that there is a cleaner alternative, the [:to_screen](docs/documentation/variables/vector#render.line_22.md) vector function.

Returns the screen position vector, or nil if the world position is not visible on your screen. This can only be called from the render callback.

### get_offscreen

`render.get_offscreen(position: vector, radius: number[, accurate: boolean]):` `vector`, `number`, `boolean`
NameTypeDescription
| **position** | `vector` | Position in world space |
| **radius** | `number` | Distance from the center of the screen as a percentage in the range [0.0, ∞] |
| **accurate** | `boolean` | Optional. If `true` then accurate calculations will be used |

Returns the `position`, `rotation`, and `is_out_of_fov` arguments or nil on failure.

`position`: Screen coordinates (Returns ellipse-based position if the world position is out of FOV)
`rotation`: Yaw axis that can be used to rotate drawing stuff
`is_out_of_fov`: Returns `true` if the world position is out of FOV.

### get_pixel

`render.get_pixel(position: vector)`

Getting the color of the pixel is a heavy process. Do not do it inside callbacks that are called a lot of times per second.
NameTypeDescription
| **position** | `vector` | Screen position |

Returns the color of the specified pixel on the screen.

### load_font

📌 Render any text via the [draw:text](docs/documentation/variables/render#text.md) function.

`render.load_font(name: string, size: number[, flags: string]):` `FontObject`
NameTypeDescription
| **name** | `string` | Font that will be initialized |
| **size** | `number` | Size of the font |
| **flags** | `string` | `a` for anti-aliasing,  `i` for cursive text, and `b` for bold text, `o` for outlined text, `d` for the drop shadow effect. |

`render.load_font(name: string, size: vector[, flags: string]):` `FontObject`
NameTypeDescription
| **name** | `string` | Font that will be initialized |
| **size** | `vector` | A vector object containing `width`, `height`, and `spacing`. |
| **flags** | `string` | `a` for anti-aliasing,  `i` for cursive text, and `b` for bold text, `o` for outlined text, `d` for the drop shadow effect, `u` to enable extra symbol support. |

Returns the `FontObject` struct or nil on failure.

### load_image

📌 Render any image via the [:texture](docs/documentation/variables/render#texture.md) function.

`render.load_image(contents: string, size: vector):` `ImgObject`
NameTypeDescription
| **contents** | `string` | Raw image file contents |
| **size** | `vector` | Size of the image |

Returns the `ImgObject` struct or nil on failure. Supports JPG, PNG, BMP, SVG, and GIF formats.

### load_image_rgba

📌 Render any image via the [:texture](docs/documentation/variables/render#texture.md) function.

`render.load_image_rgba(contents: string, size: vector):` `ImgObject`
NameTypeDescription
| **contents** | `string` | `RGBA` buffer (`HEX` encoded) |
| **size** | `vector` | Size of the image |

Returns the `ImgObject` struct or nil on failure.

### load_image_from_file

📌 Render any image via the [:texture](docs/documentation/variables/render#texture.md) function.

`render.load_image_from_file(path: string, size: vector):` `ImgObject`
NameTypeDescription
| **path** | `string` | Path to the image |
| **size** | `vector` | Size of the image |

> ℹ️ Loading images from game resources is supported.
> 
> Example: `render.load_image_from_file 'materials/panorama/images/icons/ui/warning.svg'`

Returns the `ImgObject` struct or nil on failure. Supports JPG, PNG, BMP, SVG, and GIF formats.

### measure_text

`render.measure_text(font: FontObject[, flags: string], text: string):` `vector`
NameTypeDescription
| **font** | `FontObject` | Font object or `1` for `Default` font,  `2` for `Small` font, or `3` for `Console` font |
| **flags** | `string` | Optional. `s` for DPI scaled text |
| **text** | `string` | Text that will be measured |

Returns the measured size of the text.

### highlight_hitbox

`render.highlight_hitbox(entity: entity, hitbox: number, color: color)`
NameTypeDescription
| **entity** | `entity` | The player whose hitbox(es) are to be highlighted. |
| **hitbox** | `number` | Hitbox index (an integer between 0 and 18). A table with hitbox indices can also be used to highlight multiple hitboxes. Pass 19 to highlight every hitbox. |
| **color** | `color` | The color with which you want to highlight the hitbox(es). |

Highlights the specified hitbox / hitboxes.

### get_scale

`render.get_scale(type: number):` `number`
NameTypeDescription
| **type** | `number` | The type of DPI scale to return.  `1` - Menu Scale, `2` - ESP Scale. |

Returns the DPI scale value.

## Structs

### 🔗 ImgObject

#### width

`img.width` `:` `number`

#### height

`img.height` `:` `number`

#### resolution

`img.resolution` `:` `number`

### 🔗 FontObject

#### width

`font.width` `:` `number`

#### height

`font.height` `:` `number`

#### spacing

`font.spacing` `:` `number`

#### :set_size

`font:set_size(size: number)`
NameTypeDescription
| **size** | `number` | New size of the font |

`font:set_size(size: vector)`


NameTypeDescription
| **size** | `vector` | A vector object containing `width`, `height`, and `spacing`. |

Sets the new font size.

## Draw functions

### blur

`render.blur(position_a: vector, position_b: vector, strength: number, alpha: number[, rounding: number])`
NameTypeDescription
| **position_a** | `vector` | Start position |
| **position_b** | `vector` | End position |
| **strength** | `number` | Blur strength |
| **alpha** | `number` | Alpha percentage in the range [0.0, 1.0] |
| **rounding** | `number` | Optional. Rounding of the blur rectangle in pixels |

### line

`render.line(position_a: vector, position_b: vector, color: color)`
NameTypeDescription
| **position_a** | `vector` | Start position |
| **position_b** | `vector` | End position |
| **color** | `color` | Color of the line |

### poly

`render.poly(color: color, positions: vector[, ...])`
NameTypeDescription
| **color** | `color` | Color of the polyline |
| **positions** | `vector` | Screen positions |
| **...** |  | Comma-separated vectors to concatenate with `positions` |

### poly_blur

`render.poly_blur(opacity: number, strength: number, positions: vector[, ...])`
NameTypeDescription
| **opacity** | `number` | Opacity percentage in the range [0.0, 1.0] |
| **strength** | `number` | Blur strength |
| **positions** | `vector` | Screen positions |
| **...** |  | Comma-separated vectors to concatenate with `positions` |

### poly_line

`render.poly_line(color: color, positions: vector[, ...])`
NameTypeDescription
| **color** | `color` | Color of the polyline |
| **positions** | `vector` | Screen positions |
| **...** |  | Comma-separated vectors to concatenate with `positions` |

### rect

`render.rect(position_a: vector, position_b: vector, color: color[, rounding: number, no_clamp: boolean])`
NameTypeDescription
| **position_a** | `vector` | Start position |
| **position_b** | `vector` | End position |
| **color** | `color` | Color of the rectangle |
| **rounding** | `number` | Optional. Rounding of the rectangle in pixels |
| **no_clamp** | `boolean` | Optional. If `true`, negative sizes will be allowed |

### rect_outline

`render.rect_outline(position_a: vector, position_b: vector, color: color[, thickness: number, rounding: number, no_clamp: boolean])`
NameTypeDescription
| **position_a** | `vector` | Start position |
| **position_b** | `vector` | End position |
| **color** | `color` | Color of the rectangle |
| **thickness** | `number` | Optional. Thickness of the rectangle in pixels |
| **rounding** | `number` | Optional. Rounding of the rectangle in pixels |
| **no_clamp** | `boolean` | Optional. If `true`, `position_a < position_b` will be allowed |

### gradient

`render.gradient(position_a: vector, position_b: vector, top_left: color, top_right: color, bottom_left: color, bottom_right: color[, rounding: number])`
NameTypeDescription
| **position_a** | `vector` | Start position |
| **position_b** | `vector` | End position |
| **top_left** | `color` | Color of the top left rectangle position |
| **top_right** | `color` | Color of the top right rectangle position |
| **bottom_left** | `color` | Color of the bottom left rectangle position |
| **bottom_right** | `color` | Color of the bottom right rectangle position |
| **rounding** | `number` | Optional. Rounding of the gradient in pixels |

### circle

`render.circle(position: vector, color: color, radius: number, start_deg: number, pct: number)`
NameTypeDescription
| **position** | `type` | Screen position |
| **color** | `color` | Color of the circle |
| **radius** | `number` | Radius of the circle in pixels |
| **start_deg** | `number` | `0` is the right side, `90` is the bottom, `180` is the left, `270` is the top |
| **pct** | `number` | Percentage in the range [0.0-1.0] determining how full the circle is |

### circle_outline

`render.circle_outline(position: vector, color: color, radius: number, start_deg: number, pct: number[, thickness: number])`
NameTypeDescription
| **position** | `vector` | Screen position |
| **color** | `color` | Color of the circle |
| **radius** | `number` | Radius of the circle in pixels |
| **start_deg** | `number` | `0` is the right side, `90` is the bottom, `180` is the left, `270` is the top |
| **pct** | `number` | Percentage in the range [0.0-1.0] determining how full the circle is |
| **thickness** | `number` | Optional. Thickness of the outline in pixels |

### circle_gradient

`render.circle_gradient(position: vector, color_outer: color, color_inner: color, radius: number, start_deg: number, pct: number)`
NameTypeDescription
| **position** | `vector` | Screen position |
| **color_outer** | `color` | Outer color of the circle |
| **color_inner** | `color` | Inner color of the circle |
| **radius** | `number` | Radius of the circle in pixels |
| **start_deg** | `number` | `0` is the right side, `90` is the bottom, `180` is the left, `270` is the top |
| **pct** | `number` | Percentage in the range [0.0-1.0] determining how full the circle is |

### circle_3d

`render.circle_3d(position: vector, color: color, radius: number, start_deg: number, pct: number[, outline: boolean])`
NameTypeDescription
| **position** | `vector` | Screen position |
| **color** | `color` | Color of the circle |
| **radius** | `number` | Radius of the circle in pixels |
| **start_deg** | `number` | `0` is the right side, `90` is the bottom, `180` is the left, `270` is the top |
| **pct** | `number` | Percentage in the range [0.0-1.0] determining how full the circle is |
| **outline** | `boolean` | Optional. Render the circle outline |

### circle_3d_outline

`render.circle_3d_outline(position: vector, color: color, radius: number, start_deg: number, pct: number[, thickness: number])`
NameTypeDescription
| **position** | `vector` | Screen position |
| **color** | `color` | Color of the circle |
| **radius** | `number` | Radius of the circle in pixels |
| **start_deg** | `number` | `0` is the right side, `90` is the bottom, `180` is the left, `270` is the top |
| **pct** | `number` | Percentage in the range [0.0-1.0] determining how full the circle is |
| **thickness** | `number` | Thickness of the outline in pixels |

### circle_3d_gradient

`render.circle_3d_gradient(position: vector, color_outer: color, color_inner: color, radius: number, start_deg: number, pct: number)`
NameTypeDescription
| **position** | `vector` | Screen position |
| **color_outer** | `color` | Outer color of the circle |
| **color_inner** | `color` | Inner color of the circle |
| **radius** | `number` | Radius of the circle in pixels |
| **start_deg** | `number` | `0` is the right side, `90` is the bottom, `180` is the left, `270` is the top |
| **pct** | `number` | Percentage in the range [0.0-1.0] determining how full the circle is |

### text

📌 Render any text via the [:load_font](docs/documentation/variables/render#load_font.md) function.

`render.text(font: FontObject, position: vector, color: color, flags: string, text:any[, ...])`
NameTypeDescription
| **font** | `FontObject` | Font object or `1` for `Default` font,  `2` for `Small` font, `3` for `Console` font, or `4` for `Bold` font |
| **position** | `vector` | Screen position |
| **color** | `color` | Color of the text |
| **flags** | `string` | `c` for centered text, `r` for right-aligned text, `s` for DPI scaled text.  `nil` can be specified for normal uncentered text. |
| **text** | `any` | Text that will be drawn |
| **...** |  | Comma-separated vectors to concatenate with `text` |

Draws the specified text.

### texture

📌 Create the texture via the [:load_image](docs/documentation/variables/render#load_image.md) function.

`render.texture(texture: ImgObject, position: vector[, size: vector, color: color, mode: string, rounding: number])`
NameTypeDescription
| **texture** | `ImgObject` | Image object |
| **position** | `vector` | Screen position |
| **size** | `vector` | Optional. Size of the texture |
| **color** | `color` | Optional. Color of the texture |
| **mode** | `string` | Optional. `f` for fill, `r` for repeat |
| **rounding** | `number` | Optional. Roundness of the texture |

### push_rotation

`render.push_rotation(degrees: number)`
NameTypeDescription
| **degrees** | `number` | Rotation degrees (0 - 360) |

Applies the rotation for all subsequent elements.

### pop_rotation

`render.pop_rotation()`

Discards an early set rotation.

### push_clip_rect

`render.push_clip_rect(pos_a: vector, pos_b: vector[, intersect: boolean])`
NameTypeDescription
| **pos_a** | `vector` | Screen position of point A |
| **pos_b** | `vector` | Screen position of point B |
| **intersect** | `boolean` | Optional. Allow intersections with other clip regions |

Applies the clip region to the given rectangle for all subsequent elements.

### pop_clip_rect

`render.pop_clip_rect()`

Discards an early set rectangle clipping region.

### shadow

`render.shadow(pos_a: vector, pos_b: vector, clr: color[, thickness: number, offset: number, rounding: number])`
NameTypeDescription
| **pos_a** | `vector` | Screen position of point A |
| **pos_b** | `vector` | Screen position of point B |
| **clr** | `color` | The color of the shadow |
| **thickness** | `number` | The thickness of the shadow |
| **offset** | `number` | Shadow offset |
| **rounding** | `number` | The rounding of the shadow rectangle |

Draws a shadow rectangle.
[Previousrage](docs/documentation/variables/rage.md)[Nextutils](docs/documentation/variables/utils.md)
Last updated 2 years ago
