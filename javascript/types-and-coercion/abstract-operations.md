# Abstract operations

## ToString

- For non primitives calls ToPrimitive with a hint `string`.
- Otherwise gives representation in string form.

| value       | string representation                  |
| ----------- | -------------------------------------- |
| `undefined` | `"undefined"`                          |
| `null`      | `"null"`                               |
| `true`      | `"true"`                               |
| `false`     | `"false"`                              |
| `5`         | `"5"`                                  |
| `0`         | `"0"`                                  |
| `-0`        | <code style="color:#dd6008">"0"</code> |

## ToNumber

- For non primitives calls ToPrimitive with a hint `number`.
- Otherwise gives representation in number form.

| value       | string representation                |
| ----------- | ------------------------------------ |
| `""`        | <code style="color:#dd6008">0</code> |
| `"0"`       | `0`                                  |
| `"-0"`      | `-0`                                 |
| `" 009 `    | `"9"`                                |
| `"3.14"`    | `3.14`                               |
| `0.`        | `0`                                  |
| `.0`        | `0`                                  |
| `.`         | `NaN`                                |
| `0xaf`      | `175`                                |
| `false`     | `0`                                  |
| `true`      | `1`                                  |
| `null`      | <code style="color:#dd6008">0</code> |
| `undefined` | `NaN`                                |

## ToBoolean

- check if value is `falsy` if yes return `false`, else return `true`

| falsy values |
| ------------ |
| `""`         |
| `"0"`        |
| `"-0"`       |
| `null`       |
| `NaN`        |
| `false`      |
| `undefined`  |

## ToPrimitive

- turns non primitive into primitive
- called with a hint (`string | number`)
- on non primitive values there can exist `valueOf` and `toString` functions

| hint = "number" | hint = "string" |
| --------------- | --------------- |
| `valueOf()`     | `toString()`    |
| `toString()`    | `valueOf()`     |

`ToPrimitive` tries to call the first function, if it gives primitive values - returns it, if not calls the second function. This algorithm is recursive.

### **Array toString()**

| value                | string representation                  |
| -------------------- | -------------------------------------- |
| `[]`                 | `""`                                   |
| `[1,2,3]`            | `"1,2,3"`                              |
| `[null,undefined]`   | <code style="color:#dd6008">","</code> |
| `[[[], [], []], []]` | `",,,"`                                |
| `[,,,,]`             | `",,,"`                                |

### **Object toString()**

| value                          | string representation |
| ------------------------------ | --------------------- |
| `{}`                           | `[object Object]`     |
| `{a: 2}`                       | `[object Object]`     |
| `{toString() { return "X"; }}` | `"X"`                 |

### **Array and Object valueOf()**

- Default method is `valueOf() { return this; }`, thus default behaviour always defaults to `toString`.
- So objects and arrays provide numerical coercion of stringification of themselves

| value                        | string representation                |
| ---------------------------- | ------------------------------------ |
| `[]`                         | <code style="color:#dd6008">0</code> |
| `["0"]`                      | `0`                                  |
| `["-0"]`                     | `-0`                                 |
| `[null]`                     | <code style="color:#dd6008">0</code> |
| `[undefined]`                | <code style="color:#dd6008">0</code> |
| `[1,2,3]`                    | `NaN`                                |
| `[[[[]]]]`                   | <code style="color:#dd6008">0</code> |
| `{ ... }`                    | `NaN`                                |
| `{ valueOf() { return 3; }}` | `3`                                  |

### **Object toString()**

| value                           | string representation |
| ------------------------------- | --------------------- |
| `{}`                            | `[object Object]`     |
| `{a: 2}`                        | `[object Object]`     |
| `{ toString() { return "X"; }}` | `"X"`                 |
