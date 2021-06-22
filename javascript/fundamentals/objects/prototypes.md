# Prototypes

## Prototype Chain

At the top of the chain stays `Object` linked to `Object.prototype`. It is linked to `Object` by `constructor` property

All functions have a `prototype` object , which links to `Object.prototype` with `__proto__` property. This `prototype` always points back to the function with `constructor property`

Defining functions on `prototype` means that all objects linked to the prototype have access to them.

## Shadowing Prototypes

- trying to shadow may cause a infinite recursion "explicit pseudo polymorphism"

## Object.create

```js
function objectCreatePolyfill(o) {
  function F() {}
  F.prototype = o;

  return new F();
}
```

- creates new object
- links it to the provided prototype

## Classical Inheritance vs Behavior Delegation(Prototypal Inheritance)

- classical inheritance is a copy mechanism
- delegation is a linkage - no copy
- delegation replaces parent-child relationship of code with peer-2-peer

## OLOO(Objects Linked to Other Objects)

```js
var Person = {
  setName(name) {
    this.name = name;
  },
  speak(sentence) {
    console.log(`${this.name}: ${sentence}`);
  },
};

var LoudPerson = Object.assign(Object.create(Person), {
  speakLoud(sentence) {
    this.speak(sentence.toUpperCase());
  },
});

var person = Object.create(LoudPerson);

person.setName("Mike");
person.speakLoud("arg!"); // Mike: ARG!
```
