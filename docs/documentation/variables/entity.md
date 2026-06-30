# 👾entity

## Functions:

### get

`entity.get(idx: number[, by_userid: boolean]):` `entity`
NameTypeDescription
| **idx** | `number` | Index of the entity |
| **by_userid** | `boolean` | If `true` then **idx **will be perceived as a userid |

Returns a pointer to the specified entity.

### get_local_player

`entity.get_local_player():` `entity`

Returns a pointer to the local player.

### get_players

`entity.get_players([enemies_only: boolean, include_dormant: boolean, callback: function]):``table`
NameTypeDescription
| **enemies_only** | `boolean` | If `true` then only enemies will be included |
| **include_dormant** | `boolean` | If `true` then dormant players will be included |
| **callback** | `function` | A callback with an entity pointer as the argument |

If the callback is nil, it returns the table of pointers to player entities. Otherwise the callback will be called. Access the player pointer using the arguments of the specified callback.

### get_entities

`entity.get_entities([class: number/string, include_dormant: boolean, callback: function]):` `table`
NameTypeDescription
| **class** | `number/string` | Either a name or an ID of the needed class. Pass `nil` to get every entity. |
| **include_dormant** | `boolean` | If `true` then dormant players will be included |
| **callback** | `function` | A callback with an entity pointer as the argument |

If the callback is nil, it returns the table of pointers to entities. Otherwise the callback will be called. Access the entity pointer using the arguments of the specified callback.

### get_threat

`entity.get_threat([ hittable: boolean ]):` `entity`
NameTypeDescription
| **hittable** | `boolean` | If `true` then returns a pointer to the player that can hit you |

Returns a pointer to the current threat.

### get_game_rules

`entity.get_game_rules():` `entity`

Returns the pointer to the CCSGameRulesProxy instance, or nil if none exists.

### get_player_resource

`entity.get_player_resource():` `entity`

Returns the pointer to the CCSPlayerResource instance, or nil if none exists.

## Netprops

### Getting FFI pointer

`ent[0]` `:` `userdata`

Returns the `ffi` pointer to the entity.

### Getting netprop values

`ent.prop_name:` `any`

`ent.prop_name[index]:` `any`

`ent["prop_name"]:` `any`
NameTypeDescription
| **prop_name** | `string` | Name of the networked property |
| **index** | `number` | Optional. If `prop_name` is an array, the value at this array index will be returned |

### Setting netprop values

`ent.prop_name = value`

`ent.prop_name[index] = value`

`ent["prop_name"] = value`
NameTypeDescription
| **prop_name** | `string` | Name of the networked property |
| **value** | `any` | The property will be set to this value |
| **index** | `number` | Optional. If `prop_name` is an array, the value at this array index will be set |

## Common

### :is_player

`ent:is_player():` `boolean`

Returns `true` if the entity is a player entity.

### :is_weapon

`ent:is_weapon():` `boolean`

Returns `true` if the entity is a weapon entity.

### :is_dormant

`ent:is_dormant():` `boolean`

Returns `true` if the entity is dormant.

### :is_bot

`ent:is_bot():` `boolean`

Returns `true` if the entity is a bot.

### :is_alive

`ent:is_alive():` `boolean`

Returns `true` if the entity is alive.

### :is_enemy

`ent:is_enemy():` `boolean`

Returns `true` if the entity is an enemy.

### :is_visible

`ent:is_visible():` `boolean`

Returns `true` if the entity is visible.

### :is_occluded

`ent:is_occluded([ to_entity: entity ]):` `boolean`
NameTypeDescription
| **to_entity** | `entity` | Optional. The entity that will be checked for occlusion |

If the `to_entity` is nil, the local player is checked. Returns `true` if the entity is completely occluded for the current entity.

### :get_index

`ent:get_index():` `number`

Returns the index of the entity.

### :get_name

`ent:get_name():` `string`

Returns the player name, weapon name or class name if the entity is neither of those.

### :get_origin

`ent:get_origin():` `vector`

Returns the position vector of the entity.

### :get_angles

`ent:get_angles():` `vector`

Returns the absolute angles of the entity.

### :get_simulation_time

`ent:get_simulation_time():` `table`

Returns a table containing `current` and `old` simulation time values.

### :get_classname

`ent:get_classname():` `string`

Returns the name of the entity's class.

### :get_classid

`ent:get_classid():` `number`

Returns the ID of the entity's class.

### :get_materials

`ent:get_materials():` `table`

Returns a table containing all materials used by the entity.

### :get_model_name

`ent:get_model_name():` `string`

Returns the model name of the entity.

## Players

### :get_network_state

`ent:get_network_state():` `number`

Returns the network state of the player.
IDDescription
| **0** | The entity is `not dormant` |
| **1** | The entity is dormant but the cheat has 100% info where the player is |
| **2** | The entity is dormant (updated by `Shared ESP`) |
| **3** | The entity is dormant (updated by `Sounds`) |
| **4** | The entity is dormant (not updated) |
| **5** | The entity is dormant (data is `unavailable` or `too old`) |

### :get_bbox

`ent:get_bbox():` `table`

Returns a table containing `pos1`, `pos2`, and `alpha` values.

### :get_player_info

`ent:get_player_info():` `table`

Returns a table containing information from the `player_info_t` structure of the entity.

Table values: `is_hltv`, `is_fake_player`, `steamid`, `steamid64`, `userid`, and `files_downloaded`

### :get_player_weapon

`ent:get_player_weapon([all_weapons: boolean]):` `entity / table`
NameTypeDescription
| **all_weapons** | `boolean` | If `true` then all weapons will be included |

Returns a pointer to the player's weapon entity.

If `all_weapons` is `true`, returns a table containing pointers to every weapon entity the player is currently carrying.

### :get_anim_state

`ent:get_anim_state():` `table`

Returns a table containing information about the animation state of the player.
🧷 Animation state keys[](#animation-state-keys)
- [number] abs_yaw
- [number] abs_yaw_last
- [vector] acceleration
- [number] acceleration_weight
- [number] action_weight_bias_remainder
- [boolean] adjust_started
- [number] aim_matrix_transition
- [number] aim_matrix_transition_delay
- [number] aim_pitch_max
- [number] aim_pitch_min
- [number] aim_yaw_max
- [number] aim_yaw_min
- [number] anim_duck_amount
- [number] animstate_model_version
- [number] cached_model_index
- [number] camera_smooth_height
- [userdata] crouch_walk_aim
- [boolean] defuse_started
- [number] duck_additional
- [number] duration_in_air
- [number] duration_move_weight_is_too_high
- [number] duration_moving
- [number] duration_still
- [number] duration_strafing
- [number] eye_pitch
- [number] eye_position_smooth_lerp
- [number] eye_yaw
- [boolean] feet_crossed
- [boolean] first_foot_plant_since_init
- [boolean] first_run_since_init
- [boolean] flashed
- [userdata] foot_left
- [number] foot_lerp
- [userdata] foot_right
- [number] in_air_smooth_value
- [number] jump_to_fall
- [number] ladder_speed
- [number] ladder_weight
- [number] land_anim_multiplier
- [boolean] landed_on_ground_this_frame
- [boolean] landing
- [number] last_foot_plant_update
- [number] last_rendered_eye_z
- [number] last_time_velocity_over_ten
- [number] last_update_frame
- [number] last_update_increment
- [number] last_update_time
- [number] last_velocity_test_time
- [userdata] layer_order_preset
- [number] left_ground_height
- [boolean] left_the_ground_this_frame
- [number] move_weight
- [number] move_weight_smoothed
- [number] move_yaw
- [number] move_yaw_current_to_ideal
- [number] move_yaw_ideal
- [number] next_twitch_time
- [boolean] on_ground
- [boolean] on_ladder
- [boolean] plant_anim_started
- [entity] player
- [boolean] player_is_accelerating
- [userdata] pose_param_mappings
- [vector] position_current
- [vector] position_last
- [number] previous_move_state
- [number] primary_cycle
- [number] recrouch_weight
- [boolean] smooth_height_valid
- [number] speed_as_portion_of_crouch_top_speed
- [number] speed_as_portion_of_run_top_speed
- [number] speed_as_portion_of_walk_top_speed
- [userdata] stand_run_aim
- [userdata] stand_walk_aim
- [number] static_approach_speed
- [number] step_height_left
- [number] step_height_right
- [number] strafe_change_cycle
- [number] strafe_change_target_weight
- [number] strafe_change_weight
- [number] strafe_change_weight_smooth_fall_off
- [boolean] strafe_changing
- [number] strafe_sequence
- [number] stutter_step
- [vector] target_acceleration
- [number] time_of_last_known_injury
- [number] time_to_align_lower_body
- [boolean] twitch_anim_started
- [vector] velocity
- [vector] velocity_last
- [number] velocity_length_xy
- [number] velocity_length_z
- [vector] velocity_normalized
- [vector] velocity_normalized_non_zero
- [number] walk_run_transition
- [boolean] walk_to_run_transition_state
- [entity] weapon
- [entity] weapon_last
- [entity] weapon_last_bone_setup

### :get_anim_overlay

`ent:get_anim_overlay([idx: number]):` `table`
NameTypeDescription
| **idx** | `number` | Index of the animation layer |

Returns a table containing information about the specified animation layer. Pass `nil` to get every animation layer.
🧷 Animation overlay keys[](#animation-overlay-keys)
- [number] activity
- [number] cycle
- [number] dispatched_dst
- [number] dispatched_src
- [userdata] dispatched_studio_hdr
- [number] invalidate_physics_bits
- [number] layer_animtime
- [number] layer_fade_outtime
- [number] order
- [entity] owner
- [number] playback_rate
- [number] prev_cycle
- [number] sequence
- [number] weight
- [number] weight_delta_rate

### :get_eye_position

`ent:get_eye_position():` `vector`

Returns the eye position of the player.

### :get_bone_position

`ent:get_bone_position(idx: number):` `vector`
NameTypeDescription
| **idx** | `number` | Index of the bone |

Returns the position of the specified bone.

### :get_hitbox_position

`ent:get_hitbox_position(idx: number):` `vector`
NameTypeDescription
| **idx** | `number` | Index of the hitbox |

Returns the position of the specified hitbox.

### :get_steam_avatar

`ent:get_steam_avatar():` `ImgObject`

Returns a pointer to the Steam avatar image object of the specified entity.

### :get_xuid

`ent:get_xuid():` `string`

Returns the Steam ID of the player.

### :get_resource

`ent:get_resource():` `entity`

Returns the pointer to the CCSPlayerResource instance attached to the player, or nil if none exists.

### :get_spectators

`ent:get_spectators():` `table`

Returns a table of pointers to the players that are currently spectating the specified player.

### :set_icon

`ent:set_icon([icon: string])`
NameTypeDescription
| **icon** | `string` | Optional. URL to the icon or a panorama path. |

Sets an icon in the scoreboard next to the specified player's avatar. The icon will be removed if no icon was provided.

### :simulate_movement

`ent:simulate_movement([origin: vector, velocity: vector, flags: number]):` `sim_ctx`
NameTypeDescription
| **origin** | `vector` | Specifies the origin from which the movement should be simulated. If not provided, it uses the player's current origin. |
| **velocity** | `vector` | Specifies the velocity vector for the simulated movement. If not provided, the function will use the player's current velocity as the default for the simulation. |
| **flags** | `number` | Specifies the m_fFlags 32-bit mask for prediction. If not provided, it uses the player's current `m_fFlags` value. |

This function allows you to simulate players' movement by optionally providing an origin, velocity, and flags. Returns an instance of the `sim_ctx` class containing details and tools for the movement simulation.

## Simulation Context

This class encapsulates the context and results of a movement simulation initiated by `:simmulate_movement`.

### :think

`sim:think([ticks: number])`

Simulates the player's movement for a specified number of ticks. If not specified, it defaults to simulating for 1 tick.
NameTypeDescription
| **origin** | `vector` | Position of the player after simulation. |
| **velocity** | `vector` | Velocity of the player after simulation. |
| **view_offset** | `number` | Z axis view offset. Used to calculate the eye position. |
| **duck_amount** | `number` | `m_flDuckAmount` value of the player after simulation. |
| **did_hit_collision** | `boolean` | Flags whether the player hit a collision during the simulation. |
| **obb_mins** | `vector` | Player's bounding box's minimum points. |
| **obb_maxs** | `vector` | Player's bounding box's maximum points. |
| **move** | `vector` |  |
| **simulation_ticks** | `number` | The number of ticks over which the simulation was conducted. |
| **gravity_per_apply** | `number` | Indicates the applied gravitational force during the simulation. |
| **original_max_speed** | `number` | The player's maximum speed before the simulation. |
| **max_speed** | `number` | The maximum speed achieved by the player during the simulation. |
| **is_speed_cropped** | `boolean` |  |
| **velocity_modifier** | `number` | `m_flVelocityModifier` value of the player after simulation. |
| **duck_speed** | `number` | The simulated speed at which the player can be crouching. |
| **stamina** | `number` | `m_flStamina`value of the player after simulation. |
| **surface_friction** | `number` | `m_surfaceFriction` value of the player after simulation. |
| **trace** | `trace` | Post-simulation trace object. |

## Weapons

Access functions listed below via [:get_player_weapon](docs/documentation/variables/entity#get_player_weapon.md) function

### :get_weapon_index

`ent:get_weapon_index():` `number`

Returns the index of the weapon.

### :get_weapon_icon

`ent:get_weapon_icon():` `ImgObject`

Returns the icon of the weapon.

### :get_weapon_info

`ent:get_weapon_info():` `userdata`

Returns a pointer to the `CCSWeaponInfo` struct of the weapon.
🧷 Weapon Info keys[](#weapon-info-keys)
- [number] max_player_speed
- [number] max_player_speed_alt
- [number] attack_move_speed_factor
- [number] spread
- [number] spread_alt
- [number] inaccuracy_crouch
- [number] inaccuracy_crouch_alt
- [number] inaccuracy_stand
- [number] inaccuracy_stand_alt
- [number] inaccuracy_jump_initial
- [number] inaccuracy_jump_apex
- [number] inaccuracy_jump
- [number] inaccuracy_jump_alt
- [number] inaccuracy_land
- [number] inaccuracy_land_alt
- [number] inaccuracy_ladder
- [number] inaccuracy_ladder_alt
- [number] inaccuracy_fire
- [number] inaccuracy_fire_alt
- [number] inaccuracy_move
- [number] inaccuracy_move_alt
- [number] inaccuracy_reload
- [number] recoil_seed
- [number] recoil_angle
- [number] recoil_angle_alt
- [number] recoil_angle_variance
- [number] recoil_angle_variance_alt
- [number] recoil_magnitude
- [number] recoil_magnitude_alt
- [number] recoil_magnitude_variance_alt
- [number] spread_seed
- [number] recovery_time_crouch
- [number] recovery_time_stand
- [number] recovery_time_crouch_final
- [number] recovery_time_stand_final
- [number] recovery_transition_start_bullet
- [number] recovery_transition_end_bullet
- [boolean] unzoom_after_shot
- [boolean] hide_view_model_zoomed
- [number] zoom_level
- [userdata] zoom_fov
- [userdata] zoom_time
- [string] weapon_class
- [boolean] has_burst_mode
- [boolean] is_revolver
- [number] recoil_magnitude_variance
- [string] weapon_name
- [number] weapon_type
- [number] weapon_price
- [string] console_name
- [number] max_clip1
- [number] max_clip2
- [string] world_model
- [string] view_model
- [string] dropped_model
- [string] hud_name
- [number] kill_award
- [number] cycle_time
- [number] cycle_time_alt
- [number] time_to_idle
- [boolean] full_auto
- [number] damage
- [number] headshot_multiplier
- [number] armor_ratio
- [number] bullets
- [number] penetration
- [number] range
- [number] range_modifier
- [number] throw_velocity
- [boolean] has_silencer

### :get_weapon_owner

`ent:get_weapon_owner():` `entity`

Returns a pointer to the weapon owner's entity.

### :get_weapon_reload

`ent:get_weapon_reload():` `number`

Returns the weapon reload percentage (0.0-1.0), -1 if not reloading.

### :get_max_speed

`ent:get_max_speed():` `number`

Returns the maximum speed the player can move with the weapon.

### :get_spread

`ent:get_spread():` `number`

Returns the spread of the weapon in radians.

### :get_inaccuracy

`ent:get_inaccuracy():` `number`

Returns the inaccuracy of the weapon in radians.
[Previousdb](docs/documentation/variables/db.md)[Nextesp](docs/documentation/variables/esp.md)
Last updated 2 years ago
