# Closure

A function remembers its lexical scope even a after it is executed outside of it

So when it's returned or passed into a callback it has a link to its original scope.

_Note:_ Functions remember variables not values!

```js
for (var i = 1; i <= 3; i++) {
  setTimeout(function () {
    console.log(`i :${i}`);
  }, i * 100);
}
// i: 4
// i: 4
// i: 4
```

_Fix:_ Using `let` inside of the block scope or now `for (let i = 1; i <= 3; i++)` means that different variables will be closed over.
