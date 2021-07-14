# Redux

One state tree - store - that can only be modified with actions. 

Is smarter than Context with its rerenders for now.

Easy to test.

Debugging with Redux is nice.

## Lifecycle

- Input calls action creator.
- Action creator creates an action.
- Dispatch dispatches actions to Redux.
- Redux calls root reducer with action and current state.
- Reducer modifies state and returns it.
- Redux and React render view again with new state.

## Thunk

Thunk is a function returned from another function.

## Reducers

Reducers manage state. Take events(actions), create new state based on action and sents the new state to store

## Store

Stores state and informs subscribers when state updates.

## Slices

Storecan have multiple slices that have own reducers and actions.

## Selectors

Take pieces of state to use inside components.

## Sagas

Handles asynchronous actions, returns actions that are then sent to reducers.

## Actions

Pitfalls of writing good actions:

- reusing actions
- generic actions
- subtyping of actions

Be careful with these. Specific actions are preferable. 

## When not to use Redux

- as a replacement for prop drilling
- when local component state is enough

## When to use Redux

- shared state
- state with lifetime longer than components
- the more event producers there are
- when you need to dynamically activate event subscribers
- when one event yields racing events