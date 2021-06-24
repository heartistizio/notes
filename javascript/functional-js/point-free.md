# Point Free

A way of making function by creating it with other functions. It moves to the declarative style, points are imperative.

By using fixed point functions, [composition](./concepts.md#composition) and equational reasoning we can create a point free function.

## Equational Reasoning

When two things have the same shape they are interchable.

## Fixed point functions

If you have more than one input, you can fix one of the inputs to a certain value.

`f(x,y,z) = ...` 

`g(x, y) = f(x,y,5)`

## Point free functions

Function with listed explicitly listed point (person).
```js
getPerson(function onPerson(person) {
    return renderPerson(person);
})
```

Function without needing to list a point.

```js
getPerson(renderPerson)
```


## Defining relationship between functions

With point free functions we can make the relationship between function more obvious.