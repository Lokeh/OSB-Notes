# Zero to Haskell

[Plug for snowdrift.coop]

Most languages are strict and imperative. Haskell is neither.

## From the Beginning

Algebra is the study of mathematical symbols and the rules for manipulating them.

### What's a symbol?

Variables, a symbol referring to a *particular* value. It's a placeholder for a value.

### What's a value

Data. Number, string, or some structure building up bigger pieces of data.


### Defining a structure

Example 1:

```haskell
data Alice = A Int String
```

`data` is a keyword defining a new datatype

`Alice` is a our new datastructure

`A` is a tag for our `Alice` structure that we can refer to to create new `Alice` values

`Int` and `String` are basic types that our `Alice` is composed of (e.g. a struct in C)

Example 2:

```haskell
data Color = Blue | Red
```

`Blue` is a tag and `Red` is a tag, and both are `Color`s.

Example 3:

```haskell
data Nonsense = Foo Int | Bar | Baz Int String
```

This is an algebraic datatype

`data` and `|` are keywords

`Nonsense` is the name of our structure

`Foo`, `Bar`, `Baz` are tags.


Product types: e.g. `data Alice = A Int String`
Sum types: e.g. `data Color = Blue | Red`

## Functions

A math function: `f = y(x) = x + 2`

A Haskell function:
```haskell
y x = x + 2
f = y
```

SIDEBAR: comments in haskell are `__ My comment` and `{- My comment -}`

Multivariable functions:

```haskell
englishFullName first last = first ++ " " ++ last
```

`++` is string concatenation

SIDEBAR: Types and tags must always start with an uppercase. Functions and values must always start with a lowercase.

## More datatypes

```haskell
data Foo = F Int
__ Foo = F(Int)
```

```haskell
data MaybeInt = Null | Just Int
data Maybe a = Nothing | Just a
```


