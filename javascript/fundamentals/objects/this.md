# `this` keyword

- references the execution context of function call
- determined by how the fuction was called

## Ways of invoking `this` aware function

### Implicit binding

```js
var obj = {
  func() {},
};

object.func();
```

Calls `func` with `obj` as context for the call.

### Explicit binding

#### call or apply

```js
function addPerson(name, surname) {
  this.name = name;
  this.surname = surname;
}

var person = {};

addPerson.call(person, arg1, arg2);
addPerson.apply(person, [arg1, arg2]);
```

Calls `function` with explicit `context` binding of the `this` keyword.

_Note_: Apply allows you to list arguments in array. With ES6 you can use spread operator to make them effectively the same.

#### bind

```js
(function).bind(context)
```

Returns a copy of `(function)` with explicit `context` binding of the `this` keyword. This copy cannot have the `this` overridden.

### `new` keyword

- create an empty object
- links this object to prototype of the calling function
- call the function with `this` assigned to the created object
- return `this` if function does not return otherwise

### Default Binding

- in strict mode `undefined`
- otherwise `global`

## Binding precedence

1. Is a function called by `new`
2. Is a function called by `call` or `apply`
3. Is a function called on a context object?
4. Fallback to default.

## Arrow functions

- does not define `this`, `super` or `new.target`
- resolves `this` lexically
- thats means that arrow function defined directly on the object does not have `this`
- use arrow function when you need lexical this
