# Names

My common naming practices.

## Variables

###### Single Letter

- ` i `     index
- ` j `     secondary index
- ` _ `     discarded value
- ` x `     argument, variable
- ` f, F `  function
- ` T `     type
- ` N `     number (integer)
- ` C `     constant, coefficient
- ` Q, Z `  effectiveness, goal

###### Several Letters

- ` id `    index
- ` no `    error object
- ` ok `    success object
- ` i, rq ` request object
- ` o, rs ` response object

## Entities

- ` file-name.ext `           file name (kebab-case)
- ` items/1 `                 REST resource (plural)
- ` /fonts/ `                 folder name (plural)
- ` CONST_NAME `              constant (UPPERCASE)
- ` A Title `                 title (Title Case)
- ` MyClass `                 class, module (PascalCase)
- ` someFunc() `              function (camelCase)
- ` _field, __field `         protected, private (i don't like this)
- ` IName `                   interface (only methods, multiple inheritance)
- ` BaseName `                abstract (partial definition signatures, single inheritance)
- ` watchEvent `              register an event listener
- ` isFlag `                  bool, checker function
- ` onEvent `                 event handler
- ` objRef `                  object reference
- ` imgUrl `                  image url
- ` event$ `                  Event, Observable, Subject (JavaScript)

## Placeholders (docs, especially for command line tools)

- ` <N> ` number
- ` <I> ` index, integer
- ` <A> ` alphabetical, character, symbol
- ` <S> ` string
- ` <T> ` type
- ` <?> ` bool
- ` <@> ` url/file/reference
- ` <*> ` all
- ` [...] ` optional
- ` <[T]> ` list of type `T`
- ` <{S:N}> ` dictionary with string keys and number values
- ` <name> ` variable (specified via `monospace` style in the descriptive text if is not obvious)


## To-Do Lists

- ` + task `  done
- ` - task `  to do
- ` % task `  blocked
- ` * task `  special: incomplete or demands attention (the more asterisks, the more important)
- ` ? task `  needs discussion
- ` ! task `  proposal, idea
