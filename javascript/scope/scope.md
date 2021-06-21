# Scope

- js has lexical scope - that is one determined at compile time
- scope is where you look for variables
- it's nested and javascript will look in higher scopes for variables that weren't found
- there is functional and block scope
- `var` has functional scope, `const`, `let` have block
- `var` is initialized with `undefined`, `const` and `let` are not

## Nesting

In this piece of code:

```js
var name = "Aleksander";

function takeNotes() {
  var name = "Lazy";

  function complain(complaint) {
    console.log(complaint, name);
  }

  complain("Why should I?");
}
```

Variable declared with `var name = "Aleksander";` belongs to the `global` scope, , while the `var name = "Lazy";` belongs to the scope of `takeNotes` function. `complaint` is a variable that belongs to the `complain` function.

Result of `takeNotes` call would be that `"Why should I? Lazy"` is logged out.

## Scope and Compilation

Scopes are determined at compilation time. Javascripts at compile time determines which scope does each declared variable belong to.

## Strict Mode and Dynamic Global Variables

If Javascripts find undeclared variable it will initialize it in global scope. To avoid this behaviour we can turn on a strict mode by using `"use strict"`. It's usually done automatically by transpilation tools.

## Temporary scopes

Temporary scopes can be useful to protect our code from naming conflicts and accidental access or mutation.

### IIFE

**Immediately Invodek Function Expression** are functions that are not meant to be reused, instead they are immediately invodek and discarded.

```js
var name = "Aleksander";

(function sayShorterName() {
  var name = "Alek";
  console.log(name); // "Alek"
});

console.log(name); // "Aleksander"
```

### Block scoping

Using block scoping we can create temporary variables that are immediately discarded after doing the work inside the scope.

```js
var name = "Aleksander";

{
  let name = "Alek";
}

console.log(name); // "Alek"
```
