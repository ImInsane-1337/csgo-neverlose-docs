# General

General information that you should know

## How to include pui?

There are two ways of including this library
Recommended
```
local pui = require "neverlose/pui"
```
Fast transition
```
local ui = require "neverlose/pui"
```



## Perfect strings or pui.string(s)

While Neverlose supports multicolored text and icons, *pui* makes the use of them much more convenient.

You can use perfect string almost everywhere: names of elements, groups, sidebar, and even the values of a list (though, not recommended). If you want to force perfect string, use `pui.string(text)`. You don't need to use if it's already supported.
Control characterDescription
| `\v` | Accent color. Can be overridden via setting `pui.accent` |
| `\aFFFFFFFF` or `\a[name]` | Custom color. You can use macroses using `\a[name]` |
| `\r` | Shortened `\aDEFAULT` |
| `\f<icon>` | Icons. Example: `\f<cog>` |
| `\bFFFFFF...[text]` | Gradient text. Example: `\bFF0000\b00FF00[Happy new year!]`. You can set alpha too. |

Study these examples to learn more:

#### Accent color:

```
local group = group

group:label("\vHello world!\r I mean, wassup g?")

pui.accent = "\a24EE24FF"
group:label("\vUh, who changed the color?")
```



#### Color macros

```
pui.colors.red = color(255, 0, 0)
group:label("\a[red]Red color")
```

#### Gradients

```
group:label("\bFF0000\b00FF00[Happy new year!] Wish you all the best!")
group:label("\bFFFFFFFF\bFFFFFF00[Fadeeeeeeeeeee]")
```



#### Icons

If not found, will raise an error.

```
group:label("\f<cog>  Settings")
group:label("\f<palette>  Colors")
```



#### Combination of some of the features

```
pui.sidebar("\vPerfect example")

local rage = pui.create("\v\f<skull>\r  Rage")
local misc = pui.create("\v\f<cog>\r Misc")

pui.colors.attention = color("#DADE6B")

local enable = rage:switch("\a[attention]Master switch")
local combo = misc:combo("\f<cog>  Current tab")
local label = misc:label("\b24AA24\bFFFFFF[The Green Years]")
```



## pui.find(..., *children)

`pui.find` is not really different from `ui.find`. It just returns a `pui::element(s)` or a `pui::group`.

It also supports retrieving of multiple elements from a gear. See the example below:



## pui.create(tab, name, align) or pui.create(tab, groups)

`pui.create` works just as its built-in version `ui.create`. But there is also a feature that might come in handy for you.



## pui.translate(text, translations)

Since Neverlose supports strings localization, pui can make this much faster and more convenient:

The name of the switch will automatically change to the language selected in Neverlose.
