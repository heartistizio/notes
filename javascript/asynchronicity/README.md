# Javascript - Asynchronity

- [JavaScript](../README.md)
- [Concurrency](./concurrency.md)
- [Observables](./observables.md)
- [Promises}](./promises.md)


## Problems with `async` and `await`

- `await` only handles native promises, can't await custom promises nor thunks
- Scheduling promises to micro task queue can cause starvation of event loop
- Promises cannot be cancelled
- It's only pulling

## Pull and Push

Pull operation is where you "pull" a value out of something. Push operation is where you "push" a variable somewhere.

## Async Generators

Generators only push, async function only pull. Async generators combine the two. They are meant for lazy asynchronous iteration.

`async* .. yield await`

```js
async function* fetchURLs(urls) {
  for (let url of urls) {
    let resp = await fetch(url);
    if (resp.status == 200) {
      let text = await resp.text();
      yield text.toUpperCase();
    } else {
      yield undefined;
    }
  }
}
```

To iterate over async generators use [`for await (.. of ..)`](../es/es2018#asynchronous-iteration) syntax.
