# 💾db

### Utilizing database

`db.key_name:` `any`

`db.key_name = value`
NameTypeDescription
| **key_name** | `any` | Name of the key |
| **value** | `any` | Value the key should be set to. This can be anything that can be sanitized (no functions, userdata) |

Indexing database keys is a heavy process. Do not do it inside callbacks that are called a lot of times per second.

```
-- look up for database key named "test"
-- returns the new table if database returned nil
local data = db.test or { }

data.name = 'Salvatore'
data.project = 'Spirthack Innovations LLC'

events.shutdown:set(function()
    -- replace "test" key with the new value
    db.test = data
end)
```
[Previouscvar](docs/documentation/variables/cvar.md)[Nextentity](docs/documentation/variables/entity.md)
Last updated 4 years ago
