# Transduction

Transduction is a composition of reducers.

```js
function add1(v) {
  return v + 1;
}
function isOdd(v) {
  return v % 2 == 1;
}
function sum(total, v) {
  return total + v;
}

var list = [1, 2, 3, 4, 5, 6, 7];

list.map(add1).filter(isOdd).reduce(sum);
```

```js
function add1(v) {
  return v + 1;
}
function isOdd(v) {
  return v % 2 == 1;
}
function sum(total, v) {
  return total + v;
}

var list = [1, 2, 3, 4, 5, 6, 7];

list.map(add1).filter(isOdd).reduce(sum);
```

Trying to manualy compose all of the functions is a bad idea. This would be an imperative code.

```js
list.reduce(function allAtOnce(total, v) {
  v = add1(v);
  if (isOdd(v)) {
    total = sum(total, v);

    return total;
  }
}, 0);
```

Instead you can use utilities that transform map or filter shapes into transducer (composable higher order reducers).

Transducers are inputs into utilities like `transduce`, that takes a reducer, initial value and a list or `into` which does not take the reducer and determines on initial value the type of reducer needed.

```js
var transducer = compose(mapReducer(add1), filterReducer(isOdd));

transduce(transducer, sum, 0, list);

into(transducer, 0, list);
```

Transduction can be derived from these steps:

- rewrite map and filter as reduce methods
- extract reduce
- extract combiner (method that modifies data structure) and parameterize it
- curry the function - to specialize it so it only needs combiner
- reducers are the value that travels in composed transducers
- pass reducers into transducers
