# Patterns & Methods

Approaches commonly used in system design, engineering, and problem-solving.


### Map / Mapper / Mapping / Adapter

**Map** is association between two sets of objects from different domains, organized in a key-value manner. The association is surjective, meaning that for `A → B` each element of `B` has to have at least one matching element from `A` (we cannot store a value without its key).

Adapter pattern used to adjust interface of one system to another is based on this concept.

<!-- pattern matching, conditionals -->

```js
soundOf = {
  cat: "meow",
  dog: "bark",
  bird: "chirp",
};

creature = "cat";

soundOf[creature] // → "meow"
```


### Factory / Builder / Constructor / Producer


### Chain / Pipeline


**Chain** is a sequence of operations connected in a way that the previous operation's output is the next's input. At different levels of abstraction, these operations can be simple functions, exception handlers, neural network layers, web servers' request/response middleware, complex algorithms (data preprocessing), whole programs/systems (chaining commands via Bash/PowerShell), and many more. Also, this pattern frequently occurs in real-world processes, like supply chains, _assembly lines_, etc. Even when we plan something, we think in terms of steps connected in a chain: "First, I'll do this. Then, having the outcome of my previous action, I'll do that, and...".

Most common chains are linear, but this concept can be further generalized into a graph of operations, where the pipeline may have many branches, multiple input/output edges for each node, asynchronous execution, loops, and so on.

Flow-based programming approach centered on graphs of operations considers the whole system a network of interconnected components, where each component is responsible for a specific task and can communicate with other components through predefined channels. As a result, each interaction with the system results in a particular pipeline being executed.

examples: middleware, fluent interfaces (LINQ), JQ, Node-RED, etc.
types: chain of responsibility (handlers)

Overall, this pattern helps simplifying complex operations by breaking them down into smaller, more manageable and easy-to-understand parts.

### Facade / Interface

### Container / Registry / Pool


**Container** is an environment dedicated to storing and managing multiple entities of a common nature. Apart from providing a way to access and manipulate their elements externally, registries usually also have their special inner logic, which, for example, performs operations when a new entity is registered, manages the lifecycle of the stored objects, etc.

One of the most popular examples of containers in software development is the **Dependency Injection Container**. It is the place where all application service/resource providers are stored. Depending on the dependency's lifecycle, **DIC** is responsible for initializing the service when the application starts (singleton), when a new web session (scoped) or request (transient) is created, etc., after what, the framework's dependency injection mechanism can provide access to ready-to-use service to components / other services that need it.

Another example is **Thread Pool** — a container that simplifies multithreading by holding a number of active threads and evenly distributing registered tasks between them. Once again, the actual complexity of the container is abstracted away from the user, who only needs to register a task and wait for it to finish. All the logic of managing threads and task queues, increasing/decreasing the number of available threads, processing the task results, and so on is hidden inside the thread pool.


# Techniques


### Recursion


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


