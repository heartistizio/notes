# Components

Reusable piece of UI code that can be put anywhere into the application.

## Function components

Pure by default, can manage state with [hooks](./hooks).

## Class components

They extend `React.Component`, have the `render` and lifecycle methods.

### Lifecycle methods

- shouldComponentUpdate
- componentDidUpdate
- ...more

### defaultProps 

Static method allowing to add default values for props.

### Error Boundaries
Only class components can use Error Boundaries.

```jsx
export class ErrorBoundary extends Component {
  state = { hasError: false };

  static getDerivedStateFromError() {
    return { hasError: true };
  }

  componentDidCatch(error, info) {
    // log error for debugging
  }

  render() {
    return this.state.hasError ? (
        // render user facing error
    ) : (
      this.props.children
    );
  }
}

```