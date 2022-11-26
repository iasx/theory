# Types

A list of types used to model real world phenomena, represent abstract concepts, describe systems and relations between them.


### Type
- ***Generalization of Concept***
- Denotes abstract entity/process with specific features and/or behavior.
- Some operations can be performed on types: union `A | B`, specification `A<B>`, etc.
- Types can be extended/inherited with other types.
- Type names are unique within their scope.
- `Any` type is a union of all types.


### Value
> *entity, object, instance (if of specific type or class)*
- ***Generalization of Exsistance/Singularity***
- Something that exsists and is treated as a separate entity.


### Symbol
```
Foo
```
> *identifier, variable, key, name*
- ***Generalization of Naming***
- Entity that refers to a certain concept or denotes specific value.
- Symbols are unique within their scope.


### Assignment
```
a = 1 or a := 1 or a ← 1 or a: 1 (context-dependent assignment)
```
> *definition, declaration, initialization, alias*
- Specifies correspondance between a symbol and an object (value).
- If same variable is defined twice, it's reassigned (updated) with the latest value.


### Null
> *nil, none, nothing, void*
- ***Generalization of Absence***
- Used to denote that something does not exsist.


### Bool
```
True
```
> *boolean, bit, flag*
- ***Generalization of Duality***
- Binary logical value.
- May take `True` or `False` values, which are sometimes also represented as `1` & `0` respectively.
- May be used to represent presence/absence of something, or as a flag to denote some state.


### Number
```
42 or -3.14e+10 or -123+i345
```
- ***Generalization of Measure***
> *measure, scale, scalar, dimension, quantity, amount*
- Denotes a numeric value.
- May represent a 1-dimensional entity or a point in 1-dimensional space.
- Numbers can be represented as integers, floats, complex numbers, etc.
- Numbers can be added, subtracted, multiplied, divided, etc.
- Numbers are ordinal, can be compared and ordered.


### Char
```
'A'
```
> *character, sign, rune*
- Image of a letter, number or any other character.
- Encoding is collection of correspondings between symbols and natural numbers, which are used to represent them (`Number → Character` pairs).


### Collection
```
a, b, c..
```
> *group*
- ***Generalization of Plurality***
- Entities considered together and referred to as one entity.
- Denotes not objects it's made up, but rather that something is considered in the context of multiplicity, as there can be an empty collection or collection of everything - universum.


### Sequence
```
[a, b, c..]
```
- ***Generalization of Order***
> *series, row*
- Ordered collection.
- Has index, which is a number that denotes the position of an element in the collection `Sequence[1] → a`.
- Infinite sequences are possible. They can be defined via expression or ellipsis `..` when the pattern is obvious, and are equivalent to functions.
- Sequences can be sliced, iterated, etc.


### Array
```
[a, b, c]
```
> *list, vector, tuple*
- Finite sequence of elements of one type.
- May represent a N-dimensional entity or a point in N-dimensional space.


### Tensor
```
┌     ┐
│ a b │
│ c d │
└     ┘
```
- N-dimensional array of single type elements.
- Has shape, which is a N-tuple of numbers `[1,2,3..N]` that denote the size of respective dimension.
- May represent a transformation between spaces.
- Tensors can be multiplied, transposed, inverted, etc.
- 0-dimensional tensor is a scalar. 1-dimensional tensor is a vector. 2-dimensional tensor is a matrix.


### String
```
"lorem ipsum dolor sit amet.."
```
> *text*
- 1-dimensional array of characters.
- Text search and manipulation operations can be performed on strings.


### Map
```
a → b or a ⇨ b
```
> *arrow, morphism, transformation, correspondance, projection, relation, conversion, link*
- ***Generalization of Relation***
- Denotes the relation of one entiy/process to another.
- Maps can be composed, inverted, etc.


### Function
```
x → x² or (x, y) ⇨ x²+y² or (args..) = args[1]² + args[2]² + args[3]²
```
> *method, procedure*
- Denotes a transformation rule, by which a group of input values (arguments) is mapped to output value (result).
- Functions can be applied, broadcasted, etc.


### Predicate
a ≠ b
> *condition*
- Function that returns bool value depending on combination of it's arguments and inner logic `(a ≠ b){a: 1, b: 1} → False`.
- May be used to filter collections, define a type, relation, etc.


### Set
```
{a, b, c}
```
- Unordered collection without repetitions.
- Certain operations can be performed on sets (set arithmetics).
- Similarly to collections, there can be empty set `∅ → {}` and Universum `U → {*}`.


### Object
```
{a: [1], b: {2, 3}, 42: (x) → x²}
```
> *dictionary, record, structure, document*
- ***Generalization of Structure***
- Set of `Symbol → Value` pairs.
- Symbol is usually referred to as key, index or field.


### Bag
```
{a: 1, b: 2, c: 3}
```
- Set with repetitions.
- Set of `Key → Number` pairs.
- Value represents the number of repetitions of the key-element.


### Class
```
Class{a: Number, b: String, c: List<Bool>}
```
> *schema, template*
- Combination of set of `Key → Type` pairs and a type of the same name.
- Similarly to types, classes can extend other types/classes, which means that they inherit all the properties of the parent type, modifying it's content or behavior.
- Class has a special feature - constructor, which is a function with a name of the class, that returns an object of type of the class `Class(1,"42", [True]) → Class{a: 1, b: "42", c: [True]}`. This transformation is called instantiation. Constructors may be defined explicitly in order to describe complex instantiation behavior.


### Table
```
  │ A │ B │ C │
──┼───┼───┼───┤
1 │ a │ d │ g │
2 │ b │ e │ i │
3 │ c │ f │ j │
```
> *grid, frame, dataframe*
- Structure of rows and columns, combining features of both arrays and objects.
- Table has schema - base class that describes it's structure, and data - array that contains instances of the schema.
- Row `Table[2] → {A: b, B: e, C: i}` is the specific instance of schema.
- Column `Table[A] → [a,d,g]` is the array of all values of a specific field.


# Graph
```
┌───┐
│ A │
└───┘
  │
  │
  ▼
┌───┐
│ B │
└───┘
  │
  │
  ▼
┌───┐
│ C │
└───┘
```
> *system, network*
- ***Generalization of System***
- Represents a set of objects (nodes) and relations between them (edges).
- Edges can have direction, represent flow of data, transformation or other process.
- Nodes can have properties (attributes) and behavior (methods).
- Graphs can be directed or undirected, weighted or unweighted, cyclic or acyclic, connected or disconnected, etc.
