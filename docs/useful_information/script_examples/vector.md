# ⚙️Vector

### Closest Enemy To Crosshair

```
-- You can create your own vector objects
-- All vectors are 3D
local vec = vector(1, 2, 3)

-- There are 3 fields you can access: "x", "y", and "z"
print(string.format("x: %.2f, y: %.2f, z: %.2f", vec.x, vec.y, vec.z))

-- You can also set them
vec.x, vec.y, vec.z = 0, 0, 0

events.render:set(function()
	-- All vectors are 3D, even the ones you'd expect to be 2D
	local screen_center = render.screen_size() * 0.5

	local local_player = entity.get_local_player()
	if not local_player or not local_player:is_alive() then
		return
	end

	local camera_position = render.camera_position()

	-- Even angles are 3D vectors
	-- x is pitch, y is yaw, z is roll
	local camera_angles = render.camera_angles()

	-- Let's convert it to a forward vector though
	local direction = vector():angles(camera_angles)

	local closest_distance, closest_enemy = math.huge
	for _, enemy in ipairs(entity.get_players(true)) do
		local head_position = enemy:get_hitbox_position(1)

		local ray_distance = head_position:dist_to_ray(
			camera_position, direction
		)
		
		if ray_distance < closest_distance then
			closest_distance = ray_distance
			closest_enemy = enemy
		end
	end

	if not closest_enemy then
		return
	end

	render.text(
		1,
		vector(screen_center.x, screen_center.y + 20),
		color(),
		"cd",
		string.format(
			"Closest enemy to crosshair: %s", closest_enemy:get_name()
		)
	)
end)
```
Preview[PreviousColor](docs/useful_information/script_examples/color.md)[NextESP](docs/useful_information/script_examples/esp.md)
Last updated 3 years ago
