# Syntax

System of symbolic expressions for denoting common operations and data structures.


### Operators

- ` !x `        logical negation
- ` -x `        arithmetic negation
- ` +x `        cast to number, NaN if unable
- ` $x `        variable, interpolation, stream
- ` x! `        await asynchronous task
- ` x? `        optional (in type definitions)
- ` 1..n `      range
- ` x.field `   property
- ` ..array `   spread
- ` x ? y : z`  ternary
- ` x | y `     logic OR, short-circuiting
- ` x & y `     logic AND, short-circuiting
- ` x |> F `    pipe
- ` x ?> F `    nullish coalescing (!!x ? x : y)
- ` x *> F `    for each element (entries for objects)
- ` x @> F `    for each key (indices for arrays, keys for objects)
- ` x $> F `    for each value of stream/observable
- ` x !> F `    for result task/stream completion
- ` x .+ y `    mapping operation
- ` x :: T `    type definition
- ` x -> y `    function, mapping, edge, limit


### Brackets

- ` ( x, y, z ) `    group, tuple
- ` ( x: 1, y: 2 ) ` named tuple (function arguments only)
- ` { a: 1, b: 2 } ` dict, map
- ` { 1, 2, 3 } `    set
- ` [ 1, 2, 3 ] `    list
- ` [ 1  2; 3 4 ] `  matrix

- ` F(x) `            function call
- ` F.(x) `           function broadcast
- ` T[] `             array of type `T`
- ` O[k] `            get value by id/key
- ` F<T> `            generic function
- ` O<T> `            generic object
- ` ${T} `            interpolation
- ` Name{T} `         specific structure, construct an instance of class


### Indexing, Slicing, Filtering

- `List[1]`           access element by index
- `List[-1]`          reverse indexing
- `List[1:10]`        slicing
- `List[1:2:10]`      slicing with step
  - `List[1:2:-1]`
  - `List[10:-2:1]`
- `List[func]`    all elements where func(x) == true (Iverson Bracket Notation)
  - `List[!!]`        all true elements

- `Matrix[1, 1:5]`    multiple dimensions
- `Matrix[1, :]`      whole rows/columns

- `List[[1,3,5]]`     new list from specific elements
- `List[[iterable]]`  indexes taken from iterable


### Selection & Projection

For:
```ts
Obj = {
  x: 1
  y: "foo"
  z: false
}

List = [1, NaN, 3]

type Type = {
  x: Number;
  y: String;
}
```

- `Obj = { x: 1, y: "foo", z: false }`
- `Obj.x =       1`
- `Obj[x] =      1`
- `Obj{x} = { x: 1 }`
- `Obj{x, y} = { x: 1, y: "foo" }`
- `Obj{a: x, b: y} = { a: 1, b: "foo" }`
- `Obj{x * 2, y.toUpper() / 2} = { x: 2, y: "f" }`
- `Obj{Type} = { x: 1, y: "foo" }`
- `Obj{Type.x} = { x: 1 }`
- `List{isNaN} = [false, true, false]`


### Relations

> Crow Foot
- `[A] --- [B]`     1 to 1
- `[A] --< [B]`     1 to many
- `[A] >-< [B]`     many to many
- `[A] -|-|< [B]`   1 to 1+ (mandatory)
- `[A] -o-o< [B]`   {0,1} to 0+ (optional)

> Simplified
- `[A] -:* [B]`      {1}  to {0+}
- `[A] ~:+ [B]`     {0,1} to {1+}