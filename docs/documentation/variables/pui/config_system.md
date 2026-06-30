# Config system

Yes, you can do that too

## Basic config system

This type of config system is *NOT *present in the *gamesense *version of pui. See **packages** if you are working on a gamesense script.

To use *pui *config system, you must keep all your elements in a table or tables, not in local variables.

The table(s) passed to `pui.setup(t)` can have any level of elevation. *pui* will interpret the table to a config system

You need to set up your elements after the creation of all elements. You can't update the config system.

Simple solution: `pui.setup()` in the end of the script.

This is probably the easiest way to set up a config system.

```
local menu = {
    enable = pui.switch("General", "Master")
    rage = {
        switch = pui.switch("Rage", "Enable"),
    },
    visuals = {
        color = pui.color_picker("Group", "Color"),
    },
    misc = {
        combo = pui.combo("Group", "Combo", {"A", "B", "C"}),
    }
}

pui.setup(menu)
```

Good way if you don't want to add any elements after the setup.

```
local menu = pui.setup({
    enable = pui.switch("General", "Master")
    rage = {
        switch = pui.switch("Rage", "Enable"),
    },
    visuals = {
        color = pui.color_picker("Group", "Color"),
    },
    misc = {
        combo = pui.combo("Group", "Combo", {"A", "B", "C"}),
    }
})
```

In this case you can separately add elements to setup, but the way of accessing certain regions will change.

Everything's ready. Now you can save and load your configs.

Keep in mind that any changes to your table may affect the config system and, therefore, old configs will lose some of the information (or even lose it all)

*pui* ignores non-existing regions of configs.



### Saving and loading

When you have set the config system up, you can use it easily.

#### pui.save(...) : table

As you can see, this function will return a table of values. This table is identical to the original table of elements.

Done.

You may also want to serialize and encrypt it:

`...` is a path to a certain region of your table. For example, you want to only save `rage` region of your elements. In this case, it will look like this:



It also supports nested tables. For example:

#### pui.load(config, ...)

There is nothing complicated as well.

Don't forget to decrypt and parse the data. `pui.load()` only accepts a table created with `pui.save()`.

`...` is a path to a certain region of your table. For example, you want to only load `rage` region of your elements. In this case, it will look like this:

It also supports nested tables. Just like `pui.save()`



## Packages - Isolated config system

This is a much better way to use the config system in pui, as it won't be affected by other scripts and can be created multiple times.

You can create several config systems, but that is superfluous, since you can just define regions to save and load.

### Creating



### Saving and loading

#### config:save(...) : table

As you can see, this method will return a table of values. This table is identical to the original table of elements.

Done.

You may also want to serialize and encrypt it:

`...` is a path to a certain region of your table. For example, you want to only save `rage` region of your elements. In this case, it will look like this:

It also supports nested tables. For example:

#### config:load(data, ...)

There is nothing complicated as well.

Don't forget to decrypt and parse the data. `:load()` only accepts a table created with `:save()`.

`...` is a path to a certain region of your table. For example, you want to only load `rage` region of your elements. In this case, it will look like this:

It also supports nested tables. Just like `:save()`
