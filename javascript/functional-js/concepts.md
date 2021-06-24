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

## Eager vs Lazy

Lazy, or deferred, execution. Worth using if we're not sure that the function is gonna be called. Downside: the work is being done every single time. 

```js
function repeater(count) {

    return function allTheAs() {
        return "".padStart(count, "A");
    }
}
```

Eager does the work once immediately. Worth using if function is often called. Downside: does the work even if it's not used.

```js
function repeater(count) {
    var str = "".padStart(count, "A");

    return function allTheAs() {
        return str;
    }
}
```

## Memoization

Memoization enables to do the work only once, but only do the work when called for. 

Takes a lazy function and wraps in a code that checks if inputs are the same as one of the previous calls. If yes then it returns the stored already computed value, if not it computes it, stores it and returns.

Cost of memoization is in memory. Not every function benefits form memoization. It's mostly worth if a function will be called a lot of times with the same input.

## Generalized to Specialized

Going from generalized function to a specialized allows for a more semantic code. Doing the specialization manually clutters up a code. Solution for that problem can be found in partial application and currying.

### Partial application

Utility that allows to preset an input to a function and produces a function that expects only rest of the inputs.

### Currying

Curried functions only accept one parameter per call, allowing for a step by step specialization. Only calls the function once all of the arguments are provided.

#### Loose currying

There can be multiple arguments provided at the time.

### Currying vs Partial application

Partial application take some of the input now, rest at the call.

Currying takes no immediate input, takes input one at the time.

