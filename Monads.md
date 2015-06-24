# Monads Made Semi-Understandable

## Quick overview of Functional Programming

No (global) mutable state; no side effects
Functions always return a value; no methods. Even exception, returns a value
"Referential transparency": always evaluates to the same value
Monads are a pattern that arise in FP

## Definition of monads

### Why do we care? 
- To factor out common patterns in FP
- To signal some effect, e.g. state or I/O
- Encapsulate the logic for dealing with values within a "context", e.g. empty or null

## Monad requirements
Two functions:
- flatMap (or bind)
- apply (or unit, or return)

## Examples
In Scala:
- Option[A] ([A] is some type e.g. `Option[Int]`
- List[A]
- Try[A]

#### Option[A] in Scala
```scala
train Option[A]
case class Some[A](value: A) extends Option[A]
case class None extends Option[Nothing]
```
Could be something, could be nothing

__Handling potential null values__




## Monad in action

## Re-definition

