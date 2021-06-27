# Javascript - Asynchronity

- [JavaScript](../README.md)
- [Communicating Sequential Processes](./csp.md)
- [Observables](./observables.md)
- [Promises}](./promises.md)

## Parallel  vs Asynchronicity

Parallelism is usually expressed through threads. At any given moment one core can be doing one operation and another could be doing the same. OS have virtual threads and schedule them. It's about optimization.

Asynchronicity runs on a single thread. Event loop allows scheduling of micro tasks so that some tasks do not block the execution.

_Note_: web workers try to bridge the gap, spin a thread, but it's a browser thing. They have to communicate in single threaded fashion anyway.

# Concurrency

Two higher level tasks happening within the same timeframe. 

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
