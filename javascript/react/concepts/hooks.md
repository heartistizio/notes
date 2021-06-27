# Hooks

API for management of state inside React components. 

## Rules of Hooks

1. Hooks need to be always called in the same order. 

## useState

Hooks that allows adding state to components that is kept across component rerenders.

```js
const [type, setType] = useState("");
```

Takes default value.

## useEffect

Hook used for managing side effect inside the application.

```js
useEffect(function, depedencyArray);
```

Takes a callback and a dependency array. Whenever one of the value in the dependency array updates it reruns the hook.

Returns a cleanup callback that runs on unmount.

## useRef

Ref is a container for state that needs to survive past render cycles.
