# 🔢math

## Functions:

### abs

`math.abs(x: number):` `number`
NameTypeDescription
| **x** | `number` | Number |

Returns the absolute value of x.

### acos

`math.acos(x: number):` `number`
NameTypeDescription
| **x** | `number` | Number |

Returns the arc cosine of x (in radians).

### asin

`math.asin(x: number):` `number`
NameTypeDescription
| **x** | `number` | Number |

Returns the arc sine of x (in radians).

### atan

`math.atan(x: number):` `number`
NameTypeDescription
| **x** | `number` | Number |

Returns the arc tangent of x (in radians).

### atan2

`math.atan2(x: number, y: number):` `number`
NameTypeDescription
| **x** | `number` | Number |
| **y** | `number` | Number |

Returns the arc tangent of y/x (in radians), but uses the signs of both parameters to find the quadrant of the result. (It also handles correctly the case of x being zero.)

### ceil

`math.ceil(x: number):` `number`
NameTypeDescription
| **x** | `number` | Number |

Returns the smallest integer larger than or equal to x.

### clamp

`math.clamp(value: number[, min: number, max: number]):` `number`
NameTypeDescription
| **value** | `number` | The value to clamp |
| **min** | `number` | The minimum value |
| **max** | `number` | The maximum value |

Returns the clamped value.

### cos

`math.cos(x: number):` `number`
NameTypeDescription
| **x** | `number` | Number |

Returns the cosine of x (assumed to be in radians).

### cosh

`math.cosh(x: number):` `number`
NameTypeDescription
| **x** | `number` | Number |

Returns the hyperbolic cosine of x.

### deg

`math.deg(x: number):` `number`
NameTypeDescription
| **x** | `number` | Number |

Returns the angle x (given in radians) in degrees.

### exp

`math.exp(x: number):` `number`
NameTypeDescription
| **x** | `number` | Number |

Returns the value e power x.

### floor

`math.floor(x: number):` `number`
NameTypeDescription
| **x** | `number` | Number |

Returns the largest integer smaller than or equal to x.

### fmod

`math.fmod(x: number, y: number):` `number`
NameTypeDescription
| **x** | `number` | Number |
| **y** | `number` | Number |

Returns the remainder of the division of x by y that rounds the quotient towards zero.

### frexp

`math.frexp(x: number):` `number`, `number`
NameTypeDescription
| **x** | `number` | Number |
x=m2ex = m2^ex=m2e
Returns `m` and `e` such that `x = m2e`, `e` is an integer and the absolute value of `m` is in the range `[0.5, 1)` (or zero when `x` is zero).

### huge

`math.huge` `:` `number`

The value HUGE_VAL, a value larger than or equal to any other numerical value.

### ldexp

`math.ldexp(x: number, e: number):` `number`
NameTypeDescription
| **x** | `number` | Number |
| **e** | `number` | Number |
output=m2eoutput = m2^eoutput=m2e
Returns `m2e` (e should be an integer).

### log

`math.log(x: number):` `number`
NameTypeDescription
| **x** | `number` | Number |

Returns the natural logarithm of x.

### log10

`math.log10(x: number):` `number`
NameTypeDescription
| **x** | `number` | Number |

Returns the base-10 logarithm of x.

### map

`math.map(value: number, in_from: number, in_to: number, out_from: number, out_to: number[, should_clamp: boolean]):` `number`
NameTypeDescription
| **value** | `number` | The value to map |
| **in_from** | `number` | In minimum value |
| **in_to** | `number` | In maximum value |
| **out_from** | `number` | Out minimum value |
| **out_to** | `number` | Out maximum value |
| **should_clamp** | `boolean` | Clamp `In` range |

Linearly maps two number ranges and returns the mapped value.

### max

`math.max(x: number[, ...]):` `number`
NameTypeDescription
| **x** | `number` | Number |
| **...** |  | Comma-separated numbers to concatenate with `x` |

Returns the maximum value among its arguments.

### min

`math.min(x: number[, ...]):` `number`
NameTypeDescription
| **x** | `number` | Number |
| **...** |  | Comma-separated numbers to concatenate with `x` |

Returns the minimum value among its arguments.

### modf

`math.modf(x: number):` `number`
NameTypeDescription
| **x** | `number` | Number |

Returns two numbers, the integral part of x and the fractional part of x.

### normalize_yaw

`math.normalize_yaw(x: number):` `number`
NameTypeDescription
| **x** | `number` | Number |

Returns the normalized yaw angle value.

### pi

`math.pi` `:` `number`

The value of pi.

### pow

`math.pow(x: number, y: number):` `number`
NameTypeDescription
| **x** | `number` | Number |
| **y** | `number` | Number |

Returns x^y. (You can also use the expression x^y to compute this value.)

### rad

`math.rad(x: number):` `number`
NameTypeDescription
| **x** | `number` | Number |

Returns the angle x (given in degrees) in radians.

### random

`math.random([m [, n]]):` `number`
NameTypeDescription
| **m** | `number` | Number |
| **n** | `number` | Number |

This function is an interface to the simple pseudo-random generator function rand provided by ANSI C.When called without arguments, returns a uniform pseudo-random real number in the range [0,1). When called with an integer number m, math.random returns a uniform pseudo-random integer in the range [1, m]. When called with two integer numbers m and n, math.random returns a uniform pseudo-random integer in the range [m, n].

### randomseed

`math.randomseed(x: number):` `number`
NameTypeDescription
| **x** | `number` | Number |

Sets x as the "seed" for the pseudo-random generator: equal seeds produce equal sequences of numbers.

### sin

`math.sin(x: number):` `number`
NameTypeDescription
| **x** | `number` | Number |

Returns the sine of x (assumed to be in radians).

### sinh

`math.sinh(x: number):` `number`
NameTypeDescription
| **x** | `number` | Number |

Returns the hyperbolic sine of x.

### sqrt

`math.sqrt(x: number):` `number`
NameTypeDescription
| **x** | `number` | Number |

Returns the square root of x. (You can also use the expression x^0.5 to compute this value.)

### tan

`math.tan(x: number):` `number`
NameTypeDescription
| **x** | `number` | Number |

Returns the tangent of x (assumed to be in radians).

### tanh

`math.tanh(x: number):` `number`
NameTypeDescription
| **x** | `number` | Number |

Returns the hyperbolic tangent of x.
[Previousmaterials](docs/documentation/variables/materials.md)[Nextui](docs/documentation/variables/ui.md)
Last updated 4 years ago
