# ⚙️Color

### Color Pseudocode

```
-- Colors have a flexible constructor
local foo = color(255, 0, 0, 255)
local bar = color("#00FF00FF")

-- There are 4 fields you can access: "r", "g", "b", and "a"
print(string.format("r: %d, g: %d, b: %d, a: %d", foo.r, foo.g, foo.b, foo.a))

-- You can also set them by manually indexing them like so
foo.r, foo.g, foo.b, foo.a = 0, 0, 255, 200

-- or by initializing it with several functions that our API has to offer
foo:as_fraction(1, 0, 1, 1)

-- There are a lot of built-in ways to interpret colors
print(bar) --> color(0, 255, 0, 255)
print(foo:to_hex()) --> FF0000FF
print(string.format("r: %d, g: %d, b: %d, a: %d", foo:unpack()))

-- Learn more at Variables -> color
```
[PreviousMaterials](docs/useful_information/script_examples/materials.md)[NextVector](docs/useful_information/script_examples/vector.md)
Last updated 3 years ago
