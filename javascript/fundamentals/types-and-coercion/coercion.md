# Coercion

Coercion is invoked whenever Javascript needs to switch types of values. Some examples include:

- using values in string literals
- string concatenation
- using non boolean values in logical statement

Coercion works by using [abstract methods](./abstract-methods.md).

## Corner cases

| operation             | result                               | operation                       | result                                  |
| --------------------- | ------------------------------------ | ------------------------------- | --------------------------------------- |
| `Number("")`          | <code style="color:#dd6008">0</code> | `String(-0)`                    | <code style="color:#dd6008">"0"</code>  |
| `Number(" \t\n")`     | <code style="color:#dd6008">0</code> | `String(null)`                  | `"null"`                                |
| `Number(null)`        | <code style="color:#dd6008">0</code> | `String(undefined)`             | `"undefined"`                           |
| `Number(undefined)`   | `NaN`                                | `String([null])`                | <code style="color:#dd6008">""</code>   |
| `Number([])`          | <code style="color:#dd6008">0</code> | `String([undefined])`           | <code style="color:#dd6008">""</code>   |
| `Number([1,2,3])`     | `NaN`                                | `Boolean( new Boolean(false) )` | <code style="color:#dd6008">true</code> |
| `Number([null])`      | <code style="color:#dd6008">0</code> |                                 |                                         |
| `Number([undefined])` | <code style="color:#dd6008">0</code> |                                 |                                         |
| `Number({})`          | `NaN`                                |                                 |                                         |

- because boolean coersion to numerical results in either `0` or `1` statements like `3 > 2 > 1` do not work as `3 > 2` will result in `true`, which will end up as `1 > 1`.

## Equality algorithm

For values `x` and `y`.

1. If `x` and `y` types match, return result of `x === y`
2. If `x` is `null` and `y` is `undefined`, return `true`
3. If `x` is `undefined` and `y` is `null`, return `true`
4. If `x` is a `number` and `y` is a `string`, return `x == ToNumber(y)`
5. If `x` is a `string` and `y` is a `number`, return `ToNumber(x) == y`
6. If `x` is a `boolean` , return `ToNumber(x) == y`
7. If `y` is a `boolean` , return `x == ToNumber(y)`
8. If `x` is an `object` and `y` is `string | number | symbol`, return `x == ToPrimitive(y)`
9. If `x` is an `string | number | symbol` and `y` is `object`, return `ToPrimitive(x) == y`
10. Return `false`

## How to avoid equality corner cases?

- `===` with 0 or `""` (and empty space strings)
- `===` with non-primitives
- `===` with `true` or `false`
