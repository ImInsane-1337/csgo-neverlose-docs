# ⚙️ESP

### Text Example

```
local low_health = 20

local text_example = esp.enemy:new_text("Text Example", "LOW HP", function(player)
	local health = player.m_iHealth
	if health > low_health then
		return
	end
	return "LOW HP"
end)

local group_ref = text_example:create()

local slider_ref = group_ref:slider("Low Health", 0, 50, low_health)

slider_ref:set_callback(function(slider_ref)
	low_health = slider_ref:get()
end, true)
```

### Bar Example

### Item Example
[PreviousVector](docs/useful_information/script_examples/vector.md)[NextConVars](docs/useful_information/script_examples/convars.md)
Last updated 3 years ago
