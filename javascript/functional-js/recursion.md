# Recursion

Always needs base condition. Could avoid additional call by putting the base condition in different place.

## Recursion patterns

### Iterative subproblem

Reduce problem to a smaller subset.

### Divide and conquer

Tackle half of a problem recursively.

## Stack Overflow Exceeded uwu

Functions calling functions an area in memory gets reserved for the calling function. It's called stack frame. With recursion the stack is growing.

Stack frames have local variables, program counter.

### Tail Calls

_Note_: not supported yet

Whenever function call happens at the end of execution logic, then the existing stack frame is no longer needed and can be thrown away.

It might go slower, memory optimization.

#### PTC (Proper Tail Calls)

- Function call must be at the end of function.
- Must be after `return` keyword.
- Must not call any function that is not in PTC

### Continuation-Passing Style

Prolly never write lul.

```js
function identity(v) {
  return v;
}

function countVowels(str, cont = identity) {
  var first = isVowel(str[0]) ? 1 : 0;
  if (str.length <= 1) return cont(first);
  return countVowels(str.slice(1), function f(v) {
    return cont(first + v);
  });
}
```

Function with passed continuation function defaulted to identity function(one that returns whatever is passed in). They defer the recursive code until the end of the algorithm. It still grows the memory. More of a cheat than solution in JS.

Usually converted to this code from some other code.

### Trampolines

Function calls function, returns another function, call that one, return another etc..

```js
function trampoline(fn) {
  return function trampolined(...args) {
    var result = fn(...args);

    while (typeof result == "function") {
      result = result();
    }

    return result;
  };
}
```

Stack frame nor heap never runs out.
