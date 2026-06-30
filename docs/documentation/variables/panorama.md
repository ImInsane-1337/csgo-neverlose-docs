# 🌃panorama

## Functions:

### loadstring

`panorama.loadstring(js_code: string[, panel: string]):`** **`any`
NameTypeDescription
| **js_code** | `string` | String containing JavaScript code |
| **panel** | `string` (panorama root panel) | Optional. Panel name |

## Accessing API's

`panorama[api]:` `table`
NameTypeDescription
| **api** | `string` | API name, e.g. GameStateAPI |

`panorama[panel][api]:` `table`
NameTypeDescription
| **panel** | `string` (panorama root panel) | Panel name |
| **api** | `string` | API name, e.g. GameStateAPI |

```
-- Access an API from the default root panel
local MyPersonaAPI = panorama.MyPersonaAPI

print(MyPersonaAPI.GetXuid())

-- Access an API from a specific root panel
local UiToolkitAPI = panorama.CSGOMainMenu.UiToolkitAPI

UiToolkitAPI.CloseAllVisiblePopups()
```
[Previousnetwork](docs/documentation/variables/network.md)[Nextrage](docs/documentation/variables/rage.md)
Last updated 3 years ago
