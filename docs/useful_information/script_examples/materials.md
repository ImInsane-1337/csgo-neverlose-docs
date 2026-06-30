# ⚙️Materials

```
local var_flags = {
    ["DEBUG"] = 0,
    ["NO_DEBUG_OVERRIDE"] = 1,
    ["NO_DRAW"] = 2,
    ["USE_IN_FILLRATE_MODE"] = 3,
    ["VERTEXCOLOR"] = 4,
    ["VERTEXALPHA"] = 5,
    ["SELFILLUM"] = 6,
    ["ADDITIVE"] = 7,
    ["ALPHATEST"] = 8,
    ["MULTIPASS"] = 9,
    ["ZNEARER"] = 10,
    ["MODEL"] = 11,
    ["FLAT"] = 12,
    ["NOCULL"] = 13,
    ["NOFOG"] = 14,
    ["IGNOREZ"] = 15,
    ["DECAL"] = 16,
    ["ENVMAPSPHERE"] = 17,
    ["NOALPHAMOD"] = 18,
    ["ENVMAPCAMERASPACE"] = 19,
    ["BASEALPHAENVMAPMASK"] = 20,
    ["TRANSLUCENT"] = 21,
    ["NORMALMAPALPHAENVMAPMASK"] = 22,
    ["NEEDS_SOFTWARE_SKINNING"] = 23,
    ["OPAQUETEXTURE"] = 24,
    ["ENVMAPMODE"] = 25,
    ["SUPPRESS_DECALS"] = 26,
    ["HALFLAMBERT"] = 27,
    ["WIREFRAME"] = 28,
    ["ALLOWALPHATOCOVERAGE"] = 29,
    ["IGNORE_ALPHA_MODULATION"] = 30,
    ["VERTEXFOG"] = 31
}

local var_flags_names = {}

for var_flag_name in pairs(var_flags) do
	var_flags_names[#var_flags_names + 1] = var_flag_name
end

table.sort(var_flags_names)

local group_ref = ui.find("Visuals", "Players", "Self", "Chams", "Weapon"):create()
local var_flags_ref = group_ref:listable("Var Flags", var_flags_names)

var_flags_ref:set_callback(function(var_flags_ref)
	local selected_var_flags = {}

	for _, selected_index in ipairs(var_flags_ref:get()) do
		local var_flag_name = var_flags_names[selected_index]
		local var_flag = var_flags[var_flag_name]

		selected_var_flags[#selected_var_flags + 1] = var_flag
	end

	for _, mat in ipairs(materials.get_materials("neverlose/self/weapon")) do
		for _, var_flag in pairs(var_flags) do
			mat:var_flag(var_flag, false)
		end

		for _, var_flag in ipairs(selected_var_flags) do
			mat:var_flag(var_flag, true)
		end
	end
end, true)

events.shutdown:set(function()
	for _, mat in ipairs(materials.get_materials("neverlose/self/weapon")) do
		mat:reset()
	end
end)
```
[PreviousExamples](docs/useful_information/script_examples.md)[NextColor](docs/useful_information/script_examples/color.md)
Last updated 3 years ago
