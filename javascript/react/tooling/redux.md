# Redux

One state tree - store - that can only be modified with actions. 

Is smarter than Context with its rerenders for now.

Easy to test. 

Debugging with Redux is nice.

## Lifecycle

- Input calls action creator.
- Action creator creates an action.
- Dispatch dispatches actions to Redux.
- Redux calls route reducer with action and current state.
- Reducer modifies state and returns it.
- Redux and React render view again with new state.

## Thunk

Thunk is a function returned from another function.
