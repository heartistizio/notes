 # Immutability

 The idea that things don't change unexpectedly. Concept of controling mutation.

 ## Assignment Immutability
 
 Idea that assigning something to a variable or property, you can't change its value.
 
 Generally not a big deal if writing well scoped code with little blocks. 

 ## Value Immutability

Idea that values should stay immutable. Primitive values already are, only a problem with non primitives. Can be done by making values read-only. Functional programming aims to minimize assignments. `const` only really makes sense for primitive immutable types.

### Object.freeze

Freezes first level of an object. Use as a way of making it clear to uses "this value" will not be mutated.

### Copy of values

Copy values inside functions that need to mutate.

## Immutable Data Structures

If values don't need to ever change they can be read-only. If they need to then Immutable Data Structure should be used.

Immutable Data Structure has an API which prevents unexpected changes to happen to the underlying data structure. It can't be modified, you can only create IDS with the change being applied.

Designed with optimization in mind. They store diffs to the data structure.

### Libraries

- immutable-js
- Mori
