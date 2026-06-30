# 🧰utils

## Functions:

### console_exec

`utils.console_exec(cmd: string[, ...])`
NameTypeDescription
| **cmd** | `string` | The console command(s) to execute |
| **...** |  | Comma-separated arguments to concatenate with **cmd** |

Executes a console command. Multiple commands can be combined with ';'. Be careful when passing user input (including usernames) to it.

### execute_after

`utils.execute_after(delay: number, callback: function[, ...])`
NameTypeDescription
| **delay** | `number` | Time in seconds to wait before calling callback |
| **callback** | `function` | The Lua function that will be called after the delay |
| **...** |  | Arguments that will be passed to the callback |

Executes the callback after delay seconds, passing the arguments to it.

### net_channel

`utils.net_channel():` `NetChannel`

Returns the [NetChannel](docs/documentation/variables/utils#netchannel.md) struct.

### trace_line
[https://developer.valvesoftware.com/wiki/UTIL_TraceLinedeveloper.valvesoftware.com](https://developer.valvesoftware.com/wiki/UTIL_TraceLine)
`utils.trace_line(from: vector, to: vector[, skip: entity/table/function, mask: number, type: number]):` `trace`
NameTypeDescription
| **from** | `vector` | Vector to start tracing from |
| **to** | `vector` | Vector to trace to |
| **skip** | `entity`, `table`,** **`function` | Optional. Entity skipping options |
| **mask** | `number` | Optional. Trace mask |
| **type** | `number` | Optional. Trace type [0-3] `0`: Trace everything `[Default]` `1`: Trace world only `2`: Trace entities only `3`: Trace everything filter props |

> 📌 The `skip` argument can either be an `entity` object, a table with `entity` objects, or a function, like the ShouldHitEntity callback. If you use it as a callback, you can access the `entity` and `contents_mask` by adding them to the function arguments. Inside the callback, return true if tracing should not skip the entity, otherwise return false.

Returns a [trace](docs/documentation/variables/utils#struct_trace.md) struct containing all the information.

### trace_hull

`utils.trace_hull(from: vector, to: vector, mins: vector, maxs: vector[, skip: entity/table/function, mask: number, type: number]):` `trace`
NameTypeDescription
| **from** | `vector` | Vector to start tracing from |
| **to** | `vector` | Vector to trace to |
| **mins** | `vector` | Hull mins |
| **maxs** | `vector` | Hull maxs |
| **skip** | `entity`, `table`,** **`function` | Optional. Entity skipping options |
| **mask** | `number` | Optional. Trace mask |
| **type** | `number` | Optional. Trace type [0-3] `0`: Trace everything `[Default]` `1`: Trace world only `2`: Trace entities only `3`: Trace everything filter props |

> 📌 The `skip` argument can either be an `entity` object, a table with `entity` objects, or a function, like the ShouldHitEntity callback. If you use it as a callback, you can access the `entity` and `contents_mask` by adding them to the function arguments. Inside the callback, return true if tracing should not skip the entity, otherwise return false.

Returns a [trace](docs/documentation/variables/utils#struct_trace.md) struct containing all the information.

### trace_bullet

`utils.trace_bullet(from_entity: entity, from: vector, to: vector[, skip: entity/table/function]):` `number`, `trace`
NameTypeDescription
| **from_entity** | `entity` | Player whose weapon will be used for this trace |
| **from** | `vector` | Vector to start tracing from |
| **to** | `vector` | Vector to trace to |
| **skip** | `entity`, `table`,** **`function` | Optional. Entity skipping options. If not passed, the skip entity will be `from_entity` |

> 📌 The `skip` argument can either be an `entity` object, a table with `entity` objects, or a function, like the ShouldHitEntity callback. If you use it as a callback, you can access the `entity` and `contents_mask` by adding them to the function arguments. Inside the callback, return true if tracing should not skip the entity, otherwise return false.

Returns the `damage`, [trace](docs/documentation/variables/utils#struct_trace.md) arguments.

#### 🔗 struct trace
NameTypeDescription
| **start_pos** | `vector` | Start position |
| **end_pos** | `vector` | Final position |
| **plane** | `table` | Surface normal at impact. Contains `normal`, `dist`, `type`, and `signbits` values |
| **fraction** | `number` | Percentage in the range [0.0, 1.0]. How far the trace went before hitting something. `1.0` - didn't hit anything |
| **contents** | `number` | Contents on other side of surface hit |
| **disp_flags** | `number` | Displacement flags for marking surfaces with data |
| **all_solid** | `boolean` | Returns `true` if the plane is invalid |
| **start_solid** | `boolean` | Returns `true` if the initial point was in a solid area |
| **fraction_left_solid** | `number` | Percentage in the range [0.0, 1.0]. How far the trace went before leaving solid. Only valid if we started in solid |
| **surface** | `table` | Surface hit (impact surface). Contains `name`, `props`, and `flags` values |
| **hitgroup** | `number` | `0` - generic, non-zero is specific body part |
| **physics_bone** | `number` | Physics bone that was hit by the trace |
| **world_surface_index** | `number` | Index of the msurface2_t, if applicable |
| **entity** | `entity` | Entity that was hit by the trace |
| **hitbox** | `number` | Box that was hit by the trace |
| **did_hit** | `function` | Returns `true` if there was any kind of impact at all |
| **did_hit_world** | `function` | Returns `true` if the `entity` points at the world entity |
| **did_hit_non_world** | `function` | Returns `true` if the trace hit something and it wasn't the world |
| **is_visible** | `function` | Returns `true` if the final position is visible |

### opcode_scan

`utils.opcode_scan(module: string, signature: string[, offset: number]):` `userdata`
NameTypeDescription
| **module** | `string` | Module name, in which the signature will be scanned. |
| **signature** | `string` | IDA style signature, the wildcard is "`?`" |
| **offset** | `number` | Optional offset to apply to the pointer address. |

Returns a pointer to the specified pattern if it was found. Otherwise returns `nil`.

### create_interface

`utils.create_interface(module: string, interface: string):` `userdata`
NameTypeDescription
| **module** | `string` | Module name containing the interface. |
| **interface** | `string` | Interface name. |

Returns a pointer to the specified interface if it was found. Otherwise returns `nil`.

### get_netvar_offset

`utils.get_netvar_offset(table: string, prop: string):` `number`
NameTypeDescription
| **table** | `string` | Datatable name |
| **prop** | `string` | Prop name |

Returns the offset of the specified prop. Can be used to manually navigate to the net prop.

### get_vfunc

`utils.get_vfunc(index: number, ...):` `function`
NameTypeDescription
| **index** | `number` | Virtual table index of the function. |
| **...** |  | FFI C Type definition. |

Creates and returns a wrapper function that calls a virtual table function on the specified index.

### get_vfunc

`utils.get_vfunc(module: string, interface: string, index: number, ...):` `function`
NameTypeDescription
| **module** | `string` | Module name containing the interface. |
| **interface** | `string` | Interface name. |
| **index** | `number` | Virtual table index of the function. |
| **...** |  | FFI C Type definition. |

Creates and returns a wrapper function that calls a virtual table function from the specified interface on the specified index.

### random_int

`utils.random_int(min: number, max: number):` `number`
NameTypeDescription
| **min** | `number` | Minimum boundary for the random value, included |
| **max** | `number` | Maximum boundary for the random value, included |

Returns a random integer value.

### random_float

`utils.random_float(min: number, max: number):` `number`
NameTypeDescription
| **min** | `number` | Minimum boundary for the random value, included |
| **max** | `number` | Maximum boundary for the random value, included |

Returns a random float value.

### random_seed

`utils.random_seed(seed: number)`
NameTypeDescription
| **seed** | `number` | New random seed value |

Sets the new random seed.

## 🔗 NetChannel

Access the struct via [.net_channel](docs/documentation/variables/utils#net_channel.md)function

- `FLOW:``OUTGOING`` = 0`
- `FLOW:``INCOMING`` = 1`

### time

`net.time` `:` `number`

Current network time.

### time_connected

`net.time_connected` `:` `number`

Connection time in seconds.

### time_since_last_received

`net.time_since_last_received` `:` `number`

Time since last received packet in seconds.

### is_loopback

`net.is_loopback` `:` `boolean`

Returns `true` if server is a loopback (local server).

### is_playback

`net.is_playback` `:` `boolean`

Returns `true` if demo is being played.

### is_timing_out

`net.is_timing_out` `:` `boolean`

Returns `true` if client is timing out.

### sequence_nr[flow]

`net.sequence_nr[0]` `:` `number
``net.sequence_nr[1]` `:` `number`

Last sent sequence number.

### latency[flow]

`net.latency[0]` `:` `number
``net.latency[1]` `:` `number`

Current latency (RTT), more accurate but jittering.

### avg_latency[flow]

`net.avg_latency[0]` `:` `number
``net.avg_latency[1]` `:` `number`

Average latency in seconds.

### loss[flow]

`net.loss[0]` `:` `number
``net.loss[1]` `:` `number`

Percentage in the range [0.0, 1.0] of the current packet loss.

### choke[flow]

`net.choke[0]` `:` `number
``net.choke[1]` `:` `number`

Percentage in the range [0.0, 1.0] of the current packet choke.

### packets[flow]

`net.packets[0]` `:` `number
``net.packets[1]` `:` `number`

Average amount of packets/sec.

### data[flow]

`net.data[0]` `:` `number
``net.data[1]` `:` `number`

Data flow in bytes/sec.

### total_packets[flow]

`net.total_packets[0]` `:` `number
``net.total_packets[1]` `:` `number`

Total amount of packets/sec.

### total_data[flow]

`net.total_data[0]` `:` `number
``net.total_data[1]` `:` `number`

Total data flow in bytes/sec.

### :get_server_info

`net:get_server_info():` `table`

Returns a table containing `rate`, `name`, `address`, `frame_time`, and `deviation` (or nil on failure).

### :is_valid_packet

`net:is_valid_packet(flow: number, frame: number):` `number`
NameTypeDescription
| **flow** | `number` | Channel (Flow) |
| **frame** | `number` | Sequence number |

Returns `true` if the packet is valid.

### :get_packet_time

`net:get_packet_time(flow: number, frame: number):` `number`
NameTypeDescription
| **flow** | `number` | Channel (Flow) |
| **frame** | `number` | Sequence number |

Returns the time when the packet was sent.

### :get_packet_bytes

`net:get_packet_bytes(flow: number, frame: number, group: number):` `number`
NameTypeDescription
| **flow** | `number` | Channel (Flow) |
| **frame** | `number` | Sequence number |
| **group** | `number` | Group of this packet |

Returns the group size of this packet.

### :get_packet_response_latency

`net:get_packet_response_latency(flow: number, frame: number):` `number`, `number`
NameTypeDescription
| **flow** | `number` | Channel (Flow) |
| **frame** | `number` | Sequence number |

Returns `latency_msecs`, `choke` of this packet.


[Previousrender](docs/documentation/variables/render.md)[Nextvector](docs/documentation/variables/vector.md)
Last updated 3 years ago
