# ⚙️ConVars

### Execute

> ℹ️ Force full-update
> 
> ℹ️ Turn up player footstep volume

```
-- Initialize the cvar objects
local cl_fullupdate = cvar.cl_fullupdate
local snd_setmixer = cvar.snd_setmixer

-- Invoke the callback
cl_fullupdate:call()

-- Adjust players’ step volume by setting the mixer volume to 1.2
snd_setmixer:call('GlobalFootsteps', 'vol', 1.2)
```

### Getting / Setting values

> ℹ️ Override maximum fake-lag limit

```
-- Initialize the cvar objects
local process_ticks = cvar.sv_maxusrcmdprocessticks

-- [60]: New value | [true]: Sets the raw value
process_ticks:int(60, true)
```

### Callbacks

> ℹ️ Instantly crash the server if someones changes the `sv_cheats` cvar to 1
> 
> ℹ️ Refuse the connection to the server if the IP is blacklisted
[PreviousESP](docs/useful_information/script_examples/esp.md)[NextUI](docs/useful_information/script_examples/ui.md)
Last updated 3 years ago
