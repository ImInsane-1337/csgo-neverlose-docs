# 📓Events

List of cheat events that you can listen to using :set

## List of game events:

In order to reference an event, index the `events` namespace with an event name
[Counter-Strike: Global Offensive Events - AlliedModders Wikiwiki.alliedmods.net](https://wiki.alliedmods.net/Counter-Strike:_Global_Offensive_Events)Official CS:GO events
## List of events:

### render

Fired every frame. Most functions from the [render](docs/documentation/variables/render.md) namespace can only be used here.

### render_glow

Fired every time the game prepares glow object manager. This event gives you the ability to render glow lines. Access the function by adding an argument to the callback.

`ctx:render(from: vector, to: vector, thickness: number, flags: string, color: color)`
NameTypeDescription
| **from** | `vector` | Start position in world space |
| **to** | `vector` | Final position in world space |
| **thickness** | `number` | Line thickness as a number in the range [0.0, ∞] |
| **flags** | `string` | Glow flags. `l` to draw line, `g` to draw `glow` outline, or `w` to make it fully visible behind walls |
| **color** | `color` | Color of the line |
🧷 Anti-aim direction glow lines[](#anti-aim-direction-glow-lines)


### override_view

Fired every time the game prepares camera view.
NameTypeDescription
| **fov** | `number` | Field of View |
| **view** | `vector` | Camera view angles |
| **camera** | `vector` | World position of the camera |

### createmove

Fired every time the game prepares a move command. Use this to modify something before the aimbot or movement features. Use the parameter passed by the callback to access the [UserCmd](docs/documentation/events#struct_usercmd.md).

#### 🔗 struct UserCmd
NameTypeDescription
| **block_movement** | `number` | Set to `1` to make the cheat slowdown you to the weapon's minimal speed or set to `2` to fully stop you. Defaults to `0` |
| **no_choke** | `boolean` | Set to `true` to force the cheat to not choke the current command |
| **send_packet** | `boolean` | Set to `false` to force the cheat to choke the current command |
| **force_defensive** | `boolean` | Set to `true` to trigger `'defensive'` exploit (Double tap is required to be fully charged) |
| **jitter_move** | `boolean` | Set to `false` to disable jitter move |
| **choked_commands** | `number` | Amount of choked commands |
| **command_number** | `number` | Current command number |
| **tickcount** | `number` | Current command tickcount |
| **random_seed** | `number` | Current command random seed |
| **view_angles** | `vector` | Player view angles |
| **move_yaw** | `number` | Movement yaw angle |
| **forwardmove** | `number` | Forward / backward speed |
| **sidemove** | `number` | Left / right speed |
| **upmove** | `number` | Up / down speed |
🧷 Available cmd buttons[](#available-cmd-buttons)
### createmove_run

Fired every time the game runs a move command. Use the parameter passed by the callback to access the [RunCommand](docs/documentation/events#struct_usercmd_1.md).

#### 🔗 struct RunCommand
NameTypeDescription
| **choked_commands** | `number` | Amount of choked commands |
| **command_number** | `number` | Current command number |
| **tick_count** | `number` | Current command tick count |
| **move_yaw** | `number` | Movement yaw angle |
| **forwardmove** | `number` | Forward / backward speed |
| **sidemove** | `number` | Left / right speed |
| **upmove** | `number` | Up / down speed |

### aim_fire

Fired every time the aimbot shoots at a player.
NameTypeDescription
| **id** | `number` | Shot ID |
| **target** | `entity` | Target entity |
| **damage** | `number` | Estimated damage |
| **hitchance** | `number` | Estimated hit chance |
| **hitgroup** | `number` | Targeted hitgroup |
| **backtrack** | `number` | Amount of ticks the player was backtracked |
| **aim** | `vector` | World position of the aim point |
| **angle** | `vector` | Aimbot shoot angles |

### aim_ack
NameTypeDescription
| **id** | `number` | Shot ID |
| **target** | `entity` | Target entity |
| **damage** | `number` | Actual shot damage |
| **spread** | `number` | Bullet spread angle if available |
| **hitchance** | `number` | Actual shot hit chance |
| **hitgroup** | `number` | Hitgroup that was hit |
| **backtrack** | `number` | Amount of ticks the player was backtracked |
| **aim** | `vector` | World position of the aim point |
| **wanted_damage** | `number` | Targeted damage |
| **wanted_hitgroup** | `number` | Targeted hitgroup |
| **state** | `string` | Reason the shot was missed or nil if the shot was hit. Available miss reasons: `spread`, `correction`, `misprediction`, `prediction error`, `backtrack failure`, `damage rejection`, `unregistered shot`, `player death`, `death`. |

### bullet_fire

Fired every time someone fires a bullet.
NameTypeDescription
| **entity** | `entity` | Entity that did the shot |
| **origin** | `vector` | Entity world position |
| **angles** | `vector` | Aim angle based on entity rotation |
| **sound** | `number` | Sound type |
| **spread** | `number` | Weapon spread |
| **inaccuracy** | `number` | Weapon inaccuracy |
| **recoil_index** | `number` | Weapon recoil index |
| **random_seed** | `number` | Spread seed of the shot |
| **weapon_id** | `number` | Weapon definition index |
| **weapon_mode** | `number` | Weapon fire mode |

### console_input

Fired every time the user runs a console command. Use the parameter passed by the callback to access the input string.

This can be used to implement custom console commands. Return `false` to prevent the game from processing the command.

### draw_model

Fired before a model is rendered. Use the parameter passed by the callback to access the model context. Return `false` to prevent the game from rendering the original model.
NameTypeDescription
| **name** | `string` | Name of the model. (e.g: `weapons\v_knife_cord.mdl`) |
| **entity** | `entity` | Entity that belongs to the model. |
| **draw** | `function` | Draws the model with the specified material. Pass nil to the first argument to draw the model with the default material. |
🧷 Draw model example[](#draw-model-example)
### level_init

Fired after fully connected to the server (first non-delta packet received). (`SIGNONSTATE:FULL`)

### pre_render

Fired before a frame is rendered. (`FrameStageNotify:FRAME_RENDER_START`)

### post_render

Fired after a frame is rendered. (`FrameStageNotify:FRAME_RENDER_END`)

### net_update_start

Fired before the game processes entity updates from the server. (`FrameStageNotify:FRAME_NET_UPDATE_START`)

### net_update_end

Fired after an entity update packet is received from the server. (`FrameStageNotify:FRAME_NET_UPDATE_END`)

### config_state

Fired every time config state is updated. The current state is accessible from the callback arguments as one of these strings: `pre_save`, `post_save`, `pre_load`, `post_load`.

### mouse_input

Fired every time the mouse input occurs. Return `false` to lock the mouse input.

### shutdown

Fired when the script is about to unload.

### pre_update_clientside_animation

Fired before C_CSPlayer::UpdateClientSideAnimation is called.
NameTypeDescription
| **player** | `entity` | ... |

### post_update_clientside_animation

Fired after C_CSPlayer::UpdateClientSideAnimation is called.
NameTypeDescription
| **player** | `entity` | ... |

### grenade_override_view

Invoked to override the input values for the grenade prediction. Contains detailed view parameters associated with the grenade trajectory prediction.
NameTypeDescription
| **angles** | `vector` | Input view angles |
| **src** | `vector` | Input starting position or origin |
| **velocity** | `vector` | Input velocity |
| **view_offset** | `vector` | Input view offset |

### grenade_warning

Fired when the "Grenade Proximity Warning" is being rendered. Return `false` to it from being rendered.
NameTypeDescription
| **entity** | `entity` | The game entity representing the grenade in proximity. |
| **origin** | `vector` | The current position of the grenade. |
| **closest_point** | `vector` | Represents the nearest point to the player where the grenade will cause damage. For example, in the case of a molotov, this point indicates where the flames would be most harmful. |
| **type** | `string` | Specifies the type of the grenade, "Frag" or "Molly". |
| **damage** | `number` | Predicts the potential damage that would be inflicted upon the local player if they remain at their current position when the grenade detonates. |
| **expire_time** | `number` | Specifies the time when the grenade detonates or is no longer a threat. |
| **icon** | `ImgObject` | A reference to the texture used in the warning. |
| **path** | `table` | Table of 3D vectors representing the complete trajectory path of the grenade. |

### grenade_prediction

Fired when the cheat is drawing the predicted grenade trajectory. Contains detailed information about the grenade's trajectory and impact.
NameTypeDescription
| **type** | `string` | Identifies the type of the grenade, e.g., "Smoke", "Flash", "Frag". |
| **damage** | `number` | Represents the amount of damage inflicted upon the `target` due to the grenade's effect. |
| **fatal** | `boolean` | Indicates whether the grenade's effect resulted in a lethal outcome for the `target`. |
| **path** | `table` | Table of 3D vectors representing the complete trajectory path of the grenade. |
| **collisions** | `table` | Table of 3D vectors containing all the collision points where the grenade interacts with an obstacle or wall. |
| **target** | `entity` | The game entity that the grenade directly impacts or affects. |

### localplayer_transparency

Invoked to override the opacity of the local player's model. You can override it by returning a custom alpha value.
NameTypeDescription
| **current_alpha** | `number` | The current alpha. Ranges from 0 (completely transparent) to 255 (completely opaque). |

## List of complicated events:

### voice_message

Fired every time the game receives a voice packet.
NameTypeDescription
| **entity** | `entity` | Entity that belongs to the voice packet. |
| **audible_mask** | `number` | Audible mask |
| **xuid** | `number` | Xuid |
| **proximity** | `number` | Proximity |
| **format** | `number` | Format |
| **sequence_bytes** | `number` | Sequence bytes |
| **section_number** | `number` | Section number |
| **uncompressed_sample_offset** | `number` | Uncompressed sample offset |
| **buffer** | `bf_read` | Voice packet buffer |
| **is_nl** | `boolean` | Packet was sent by the Neverlose |

#### 🔗 struct bf_read
NameTypeDescription
| **read_bits** | `function` | Reads a number value from the buffer `:read_bits(num_bits)` |
| **read_coord** | `function` | Reads a floating number value from the buffer `:read_coord()` (4 bytes) |
| **reset** | `function` | Resets the pointer of the buffer to its original offset |
| **crypt** | `function` | Encrypts/decrypts buffer `:crypt(key)` |

#### 🔗 struct bf_write
NameTypeDescription
| **write_bits** | `function` | Writes a number value to the buffer `:write_bits(value, num_bits)` |
| **write_coord** | `function` | Writes a floating number value to the buffer `:write_coord(value)` (4 bytes) |
| **is_overflowed** | `function` | Returns `true` if the buffer is overflowed |
| **crypt** | `function` | Encrypts/decrypts buffer `:crypt(key)` |

> 📌 Firing this event from the Lua will send a voice packet
> 
> `events.voice_message(function: buffer)`

> `[neverlose] received voice packet from Salvatore | pct_tickcount: 1200`
[PreviousUI](docs/useful_information/script_examples/ui.md)[NextVariables](docs/documentation/variables.md)
Last updated 2 years ago
