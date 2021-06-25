# Data Structure Operations

## Functors

Value that can be mapped over.

## Map

Transform operation.

## Filter

Inclusion or exclusion operation.

## Fusion

Long mapping chains while good for readability, are bad for performance. Performance can be improved by composing map functions together. That's called fusion. It is only applicable for map. Performance optimization with methods that have incompatible shapes, such as map, filter and reduce, can be done with transudction.

## [Transduction](./transduction.md)

## Monad

Pattern for pairing data with set of predictable behaviours that let it interact with other monads.

- Monad is a way of creating a functional friendly data structure.
- It's a wrapper around a value with a set of behaviours that makes that value easier to interoperate with.
- It turns the value into a functor.

### Core Methods

#### **map**

Transform into a different monad of the same type.

#### **chain, bind, flatMap**

Returns whatever passed function returns when value is passed into it. The function passed should return a Monad.

#### **ap**

Takes in another Monad. Calls its map function with value. Value needs to be a mapping function.
A way to take one value out of a Monad, put it into a closure and use it as a mapper for next Monad.

### Nothing

Only returns Nothing from all methods. Represents no-op.

### Maybe

Maybe creates Nothing Monad if value is `nullable` or Just Monad otherwise.

### Either

### IO
