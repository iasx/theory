# Methods & Patterns

Approaches commonly used in system design, software development, and problem-solving.


### Map / Mapper / Mapping / Adapter

**Map** is association between two sets of objects from different domains, organized in a key-value manner. The association is surjective, meaning that for `A → B` each element of `B` has to have at least one matching element from `A` (we cannot store a value without its key).

```js
soundOf = {
  cat: "meow",
  dog: "bark",
  bird: "chirp",
};

creature = "cat";

soundOf[creature] // → "meow"
```

### Facade / Interface

### Container / Registry / Pool


**Container** is an environment dedicated to storing and managing multiple entities of a common nature. Apart from providing a way to access and manipulate their elements externally, registries usually also have their special inner logic, which, for example, performs operations when a new entity is registered, manages the lifecycle of the stored objects, etc.

One of the most popular examples of containers in software development is the **Dependency Injection Container**. It is the place where all application service/resource providers are stored. Depending on the dependency's lifecycle, **DIC** is responsible for initializing the service when the application starts (singleton), when a new web session (scoped) or request (transient) is created, etc., after what, the framework's dependency injection mechanism can provide access to ready-to-use service to components / other services that need it.

Another example is **Thread Pool** — a container that simplifies multithreading by holding a number of active threads and evenly distributing registered tasks between them. Once again, the actual complexity of the container is abstracted away from the user, who only needs to register a task and wait for it to finish. All the logic of managing threads and task queues, increasing/decreasing the number of available threads, processing the task results, and so on is hidden inside the thread pool.
