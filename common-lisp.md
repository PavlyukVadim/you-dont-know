## Table of Contents

  1. [Predicates](#predicates)
  
## Predicates
Predicates are functions that test their arguments for some specific conditions and returns nil if the condition is false, or some non-nil value is the condition is true.

Predicate | Description
--- | --- 
`atom`| It takes one argument and returns `T` if the argument is an atom or `NIL` if otherwise.
`equal`| It takes two arguments and returns `T` if they are structurally equal or `NIL` otherwise
`eq`| It takes two arguments and returns `T` if they are same identical objects, sharing the same memory location or `NIL` otherwise
`eql`|It takes two arguments and returns `T` if the arguments are eq, or if they are numbers of the same type with the same value, or if they are character objects that represent the same character, or `NIL` otherwise
`evenp`|It takes one numeric argument and returns `T` if the argument is even number or `NIL` if otherwise.
`oddp`|It takes one numeric argument and returns `T` if the argument is odd number or `NIL` if otherwise.
`null`|It takes one argument and returns `T` if the argument evaluates to nil, otherwise it returns `NIL`.
`numberp`|It takes one argument and returns `T` if the argument is a number() or `NIL` if otherwise.
`arrayp`|It takes one argument and returns `T` if the argument is an array object otherwise it returns `NIL`.
There are other functions for checking type of argument: 
* `symbolp`
* `integerp`
* `floatp`
* `characterp`
* `stringp`
**[⬆ back to top](#table-of-contents)**


