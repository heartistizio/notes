# Types

## Primitive types

- `undefined`
- `null`
- `boolean`
- `string`
- `symbol`
- `number`
- `bigint`

### Object type and subtypes

- `object`
- `function`
- `array`

### Typeof

`typeof` operator returns a string from following values:

| type                                 | typeof                                      |
| ------------------------------------ | ------------------------------------------- |
| `undefined`                          | `"undefined"`                               |
| `null`                               | <code style="color:#dd6008">"object"</code> |
| `boolean`                            | `boolean"`                                  |
| `number`                             | `"number"`                                  |
| `bigint`                             | `"bigint"`                                  |
| `string`                             | `"string"`                                  |
| `symbol`                             | `"symbol"`                                  |
| `function`                           | `"function"`                                |
| `any other object(indlucing arrays)` | `"object"`                                  |

### Special cases

#### NaN

- invalid number
- not equal to itself
- use `Number.isNaN` or `Object.is` for comparison

#### Negative Zero

- a 0 with a sign bit
- equal to 0, is not less nor greater
- stringifies to a `"0"`
- use `Object.is` for comparison

## Fundamental objects

### Used for explicit coersion or in boxing.

- `String()`
- `Number()`
- `Boolean()`

### Following are used with `new` keyword.

- `Object()`
- `Array()`
- `Function()`
- `Date()`
- `RegExp()`
- `Error()`

## Boxing

Javascript automatically `boxes` primitive values into their respective object representation once you try accessing methods on these values.
