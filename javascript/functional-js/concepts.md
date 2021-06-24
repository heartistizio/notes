# Concepts

## Why write functional code?

### It's more declarative

- [Imperative vs Declarative](../../coding/clean-code.md)

### It's provable

Functional programming is math. That mean that the code you write is provable. That means that we can be certain what code will do.

## Composition

Output of one function immediately becomes an input of another.

```js
function compose(fn2, fn1) {
    return function composed(v) {
        return fn2(fn1(v));
    }
}
```

## Closure

[Fundamentals Closure](../fundamentals/scope/closure.md)

```
Closure is when a function "remembers" the variables around it even when that function is executed elsewhere.
```

Closure is not necessarily functionally pure. 