### Adapters

Sometimes shapes have to be adapted, few adapters:

```js
function unary(fn) {
    return function one(arg) {
        return fn(arg);
    }
}
```

```js
function binary(fn) {
    return function two(arg1, arg2) {
        return fn(arg1, arg2);
    }
}
```

```js
function flip(fn) {
    return function flipped(arg1, arg2, ...args) {
        return fn(arg2, arg1, ...args);
    }
}
```

```js
function reverseArgs(fn) {
    return function reversed(...args) {
        return fn(...args.reverse());
    }
}
```

```js
// equivalent with .apply()
function spreadArgs(fn) {
    return function spread(args) {
        return fn(...args);
    }
}
```

```js
function gatherArgs(fn) {
    return function gathered(...args) {
        return fn(args);
    }
}
```

```js
function not(fn) {
    return function negated(...args){
        return !fn(...args);
    }
}
```

```js
function when(fn){
	return function (predicate){
		return function (...args){
			if(predicate(...args)){
				return fn(...args)
			}
		}
	}
}
```

```js
function mod(y) {
    return function forX(x) {
        return x % y;
    };
}
```

```js
function eq(y) {
    return function forX(x) {
        return x === y;
    };
}
```