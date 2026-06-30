# 📂files

## Example available!

## Functions:

### create_folder

`files.create_folder(path: string)`
NameTypeDescription
| **path** | `string` | New folder path |

### read

`files.read(path: string):` `any`
NameTypeDescription
| **path** | `string` | Path to the file |

Returns contents of the specified file.

### write

`files.write(path: string, contents: string[, is_binary: boolean]):` `boolean`
NameTypeDescription
| **path** | `string` | Path to the file |
| **contents** | `any` | Contents the file should be set to |
| **is_binary** | `boolean` | Is `contents` a binary |

Replaces contents of the specified file. Returns `false` on failure.

### get_crc32

`files.get_crc32(path: string):` `number`
NameTypeDescription
| **path** | `string` | Path to the file |

Returns the crc32 checksum of the file.
[Previousevents](docs/documentation/variables/events.md)[Nextglobals](docs/documentation/variables/globals.md)
Last updated 3 years ago
