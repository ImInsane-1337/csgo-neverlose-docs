# 📎globals

## Variables:

### curtime

`globals.curtime` `:` `number`

Server time in seconds.

### realtime

`globals.realtime` `:` `number`

Local time in seconds.

### frametime

`globals.frametime` `:` `number`

Duration of the last game frame in seconds.

### framecount

`globals.framecount` `:` `number`

Amount of frames since the game started.

### absoluteframetime

`globals.absoluteframetime` `:` `number`

Duration of the last game frame in seconds.

### tickcount

`globals.tickcount` `:` `number`

Number of ticks elapsed on the server.

### tickinterval

`globals.tickinterval` `:` `number`

Duration of a tick in seconds.

### max_players

`globals.max_players` `:` `number`

Maximum number of players on the server.

### is_connected

`globals.is_connected` `:` `boolean`

Returns `true` if the player is connected, but not necessarily active in game (could still be loading).

### is_in_game

`globals.is_in_game` `:` `boolean`

Returns `true` if the player is currently connected to a game server.

### choked_commands

`globals.choked_commands` `:` `number`

Number of choked commands.

### commandack

`globals.commandack` `:` `number`

Current command number acknowledged by server.

### commandack_prev

`globals.commandack_prev` `:` `number`

Sequence number of last outgoing command.

### last_outgoing_command

`globals.last_outgoing_command` `:` `number`

Number of last command sequence number acknowledged by server.

### server_tick

`globals.server_tick` `:` `number`

Last-received tick from the server.

### client_tick

`globals.client_tick` `:` `number`

The client's own tick count.

### delta_tick

`globals.delta_tick` `:` `number`

Last-valid received snapshot (server) tick.

### clock_offset

`globals.clock_offset` `:` `number`

Difference between the server and client tick counts, used to predict the current server tick count.


[Previousfiles](docs/documentation/variables/files.md)[Nextjson](docs/documentation/variables/json.md)
Last updated 3 years ago
