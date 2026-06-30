# Methods

Learn more about methods of a pui element

## :depend(...)

Sometimes you want to hide certain elements to not mess up the menu. It may look simple but actually it's rather difficult and complicated. But *pui* can make this as easy as pie.

`:depend(...)` is a method of a pui element, which creates a dependence on elements passed as arguments.

Its arguments can be either elements themselves (generally switches), or tables, which contain `ref, condition, invert`.

In most of the cases, it looks like this: `:depend( {ref, condition}, {ref2, condition2}, ... )`

Also, if you want to "disable" elements (lock them), you can do it with `:depend(true, ...)`

It's worth to note that `pui::group` supports `:depend()` as well.

#### Study these examples:

This is a common example of the use of `:depend(...)`. As you can see, there are two labels showing statuses of a switch.

```
local switch = group:switch("Master switch")
local status1 = group:label("...is enabled!")
local status2 = group:label("...is disabled!")

status1:depend( {switch, true} )  -- or simply :depend(switch)
status2:depend( {switch, false} )
```

If you want to show your elements when a certain value is selected in a combobox, this can be done as well.

```
local combo = group:combo("Author of Pride and Prejudice:", {"Leo Tolstoy", "Charles Dickens", "Jane Austen"})

local correct = group:label("Yes! Jane Austen is")
local wrong = group:label("No! Try again")

correct:depend( {combo, "Jane Austen"} )
wrong:depend( {combo, "Jane Austen", true} )
```

`true` in the third argument invert the condition. Basically, it will look like this:

`not "Jane Austen"`

You can define ranges for sliders like this:

```
local jitter = group:slider("Jitter degree", 0, 100)
local good = group:depend("Good choice")

good:depend( {jitter, 40, 60} ) -- range from 40 to 60
```

Sometimes the condition may be too complicated. In this case, you can use a function:

Yes, you can add more conditions calling `:depend(..)` multiple times. But you don't have to.

Study this example of a password puzzle:

There are a lot of ways to use `:depend()` that I can't even imagine.



## :set_event(event, func, condition*)

This methods is used to call functions in events when a certain condition is met. You can unset this behavior via `:unset_event(event, func)`. You can't unset *anonymous *functions.
