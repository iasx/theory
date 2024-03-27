# Techniques


### Caching / Memorization

Caching lets you avoid the unnecessary repeated execution of the same operation by memoizing its results for each unique set of arguments. This is especially useful for computationally expensive tasks or problems that can be split into overlapping sub-problems (see [Dynamic Programming](https://en.wikipedia.org/wiki/Dynamic_programming#Computer_science)).

This technique is applicable at many levels of abstraction, from memoizing the results of low-level operations to caching the responses of whole servers to speed up request processing and reduce the system's load.

The example below demonstrates a simple memoization wrapper function that stores the computed results of a given function for each unique set of arguments.

```ts
function memoized(target: Function): Function {
  const cache = new Map();

  return (...args) => {
    const key = JSON.stringify(args);

    if (cache[key]) return cache[key];

    const result = target(...args);

    cache[key] = result;

    return result;
  };
}
```

### Chains / Pipelines

### Recursion

