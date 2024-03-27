# Names

Common naming practices.

## Variables

###### Single Letter

- ` i `     index
- ` j `     secondary index
- ` x `     argument, variable
- ` f, F `  function
- ` T `     type
- ` N `     number (integer)
- ` C `     constant, coefficient
- ` Q, Z `  effectiveness, goal

###### Several Letters

- ` id `    index
- ` rg `    regex pattern
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
- ` _field `                  private (but i don't like it)
- ` IName `                   interface (only methods, multiple inheritance)
- ` AName, BaseName `         abstract (only signatures, single inheritance, prefixing is optional)
- ` trackPlay `               register an event listener
- ` isPlay `                  bool, checker function
- ` onPlay `                  event handler
- ` rgMail `                  regex for email validation
- ` objRef `                  object reference
- ` imgUrl `                  image Url
- ` valueChange$, newValue$ ` Event, Observable, Subject (JavaScript)

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
