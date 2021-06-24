# Functions Purity

## Functions

Most "functions" in JS code are just procedures. To be a pure function it needs to:

- have output that is related to the input
- call only other functions
- don't have side effects

It's the function call that matters, not its definition.



## Referential Transparency

If function call adheres to Referential Transparency then it's pure.

```definition
A function call can be replaced with its return value and not return any of the rest of the code.
```

## Side Effects

Main problem with side effects is that is creates uncertainty. Once they appear reader has to start executing the code. Not all side effects are avoidable. 

- I/O
- Database Storage
- Network Calls
- DOM
- Timestamps
- Random Numbers

You can't avoid side effects in program, try to minimaze them, as they pollute functional programming. Try to keep them isolated from pure code. 

Keep the pure functions as a core of program with side effects on the outer shell.

## Pure Function

Pure function is a function in a mathematical sense. Reader cam be certain of how pure function executes. They are isolated from the rest of the program. Because of how JS works it's about calling functions purely and not about how they are defined.

Referencing a thing that doesn't ever change is exactly the same as inlining it - same as saying it's a constant. The key is to make it obvious to a reader that variable used in a function is a constant.

### Reducing Surface Area

Reducing surface area is an effective technique of making it clear to the user that variables will not be reassigned.

### Same Input, Same Output

Pure functions act in isolation, given the same input, they always give the same output.

### Level of Confidence

Heart of functional programming is to shift the codebase to have as many areas as possible that have high level of confidence that pure function calls provide.

## Extracting impurity

Extraction of side effect from impure functions allows us to create a pure function and a procedure handling the side effect. 

## Containing Impurity

### Wrapper

Structuring things that impurity doesn't affect other parts of application. That could be keeping the mutation to the function scope, not the global. If it's not possible to contain impurity with a wrapper it might be needed to use an adapter.

### Adapter

- capture a state
- execute impure code that mutates the state
- capture the changed state
- return the state to its original values
- return changed state

It's ugly, and really hard. But can be used from time to time. But it runs as a pure function call.

## Arguments

Parameters are the labels for arguments - values that are passed in. They should be listed from more general to more specific. Shapes of our functions matter,

### Higher Order Functions

Function that either receives one or more functions as an input OR outputs a one or more functions.

### Shape of functions

Different kind of shapes:

- unary - takes one input, returns one output 

- binary - takes two inputs, returns one output

- n-ary (enary) - function that takes more inputs
