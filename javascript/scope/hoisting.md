# Hoisting

A term for the fact that because of compilation declaration statements are "pulled" up to the top of their scope. In fact they are just found on the compilation passthrough.

- `var` is initialized with `undefined`
- `const` and `let` throw error if they are accessed without initialization
- but yeah don't declare `var` under assignment even if it works
