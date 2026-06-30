# 📍vector

## Example available!
[⚙️Vector](docs/useful_information/script_examples/vector.md)
## Functions:

### :angles

`vec_object:angles(pitch: number, yaw: number):` `vector`
NameTypeDescription
| **pitch** | `number` | Pitch component of the angle |
| **yaw** | `number` | Yaw component of the angle |



Converts the angle into a forward vector overwriting the vector's coordinates. Returns itself.

`vec_object:angles(vector: angle):` `vector`
NameTypeDescription
| **angle** | `vector` | Angle vector component |



Converts the angle into a forward vector overwriting the vector's coordinates. Returns itself.

`vec_object:angles():` `vector`



Returns the angle vector representing the normal of the vector.

### :ceil

`vec_object:ceil():` `vector`

Ceils & overwrites the x, y, and z coordinates of a vector. Returns itself.

### :clone

`vec_object:clone():` `vector`

Creates and returns a copy of the vector.

### :closest_ray_point

`vec_object:closest_ray_point(ray_start: vector, ray_end: vector):` `vector`
NameTypeDescription
| **ray_start** | `vector` | Ray start position |
| **ray_end** | `vector` | Ray end position |

Returns the vector of the closest point along a ray.

### :cross

`vec_object:cross(other: vector):` `vector`
NameTypeDescription
| **other** | `vector` | The vector to calculate the cross product with |

Returns the cross product of two given vectors.

### :dist

`vec_object:dist(other: vector):` `number`
NameTypeDescription
| **other** | `vector` | The vector to get the distance to |

Returns the Euclidean distance between the two given vectors.

### :dist2d

`vec_object:dist2d(other: vector):` `number`
NameTypeDescription
| **other** | `vector` | The vector to get the distance to |

Returns the 2D distance to another vector.

### :dist2dsqr

`vec_object:dist2dsqr(other: vector):` `number`
NameTypeDescription
| **other** | `vector` | The vector to get the squared distance to |

Returns the squared 2D distance to another vector.

### :distsqr

`vec_object:distsqr(other: vector):` `number`
NameTypeDescription
| **other** | `vector` | The vector to get the squared distance to |

Returns the squared Euclidean distance to another vector.

### :dist_to_ray

`vec_object:dist_to_ray(ray_start: vector, ray_direction: vector):` `number`
NameTypeDescription
| **ray_start** | `vector` | Ray start position |
| **ray_direction** | `vector` | Ray direction |

Returns the distance to a ray.

### :dot

`vec_object:dot(other: vector):` `number`
NameTypeDescription
| **other** | `vector` | The vector to calculate the dot product with |

Returns the dot product of the two given vectors.

### :floor

`vec_object:floor():` `vector`

Rounds the x, y, and z coordinates of the vector down to the largest integer that is less than or equal. Returns itself.

### :in_range

`vec_object:in_range(other: vector, range: number):` `boolean`
NameTypeDescription
| **other** | `vector` | The vector to calculate the distance to |
| **range** | `number` | The distance |

Returns true if the vector is within the given distance to another vector.

### :init

`vec_object:init(x: number, y: number, z: number):` `vector`
NameTypeDescription
| **x** | `number` | New X coordinate |
| **y** | `number` | New Y coordinate |
| **z** | `number` | New Z coordinate |

Overwrites the vector's coordinates. Returns itself.

### :length

`vec_object:length():` `number`

Returns the Euclidean length of the vector.

### :length2d

`vec_object:length2d():` `number`

Returns the length of the vector in two dimensions, without the Z axis.

### :length2dsqr

`vec_object:length2dsqr():` `number`

Returns the squared length of the vectors x and y value.

### :lengthsqr

`vec_object:lengthsqr():` `number`

Returns the squared length of the vector.

### :lerp

`vec_object:lerp(other: vector, weight: number):` `vector`
NameTypeDescription
| **other** | `vector` | The vector to interpolate to |
| **weight** | `number` | A value between 0 and 1 that indicates the weight of **other** |

Returns the linearly interpolated vector between two vectors by the specified weight.

### :normalize

`vec_object:normalize():` `number`

Normalizes the vector and returns the length of the vector.

### :normalized

`vec_object:normalized():` `vector`

Returns a vector with the same direction as the specified vector, but with a length of one.

### :scale

`vec_object:scale(scalar: number):` `vector`
NameTypeDescription
| **scalar** | number | The scalar value |

Multiplies the vector by the specified scalar.

### :scaled

`vec_object:scaled(scalar: number):` `vector`
NameTypeDescription
| **scalar** | number | The scalar value. |

Returns a copy of the vector multiplied by the specified scalar.

### :to

`vec_object:to(other: vector):` `vector`
NameTypeDescription
| **other** | `vector` | The vector to get the direction to. |

Returns the forward vector from itself to another vector.

### :to_screen

`vec_object:to_screen():` `vector`

Returns a vector containing the coordinates where the specified position vector appears on the screen.

### :unpack

`vec_object:unpack():` `number`, `number`, `number`

Returns the x, y, and z coordinates of the vector. Note that these fields can be accessed by indexing x, y, and z.

### :vectors

`vec_object:vectors():` `vector`, `vector`

Returns the right and up vector of a forward vector.
[Previousutils](docs/documentation/variables/utils.md)
Last updated 2 years ago
