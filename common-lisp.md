## Table of Contents

  1. [Lists](#lists)
  1. [Predicates](#predicates)


## Lists

<a name="manipulating--functions"></a><a name="1.1"></a>
  - [1.1](#manipulating--functions) **List Manipulating Functions**. The following table provides some commonly used list manipulating functions:

Function|Description
--|--
`car`|It takes a list as argument, and returns its first element.
`cdr`|It takes a list as argument, and returns a list without the first element.
`cons`|It takes two arguments, an element and a list and returns a list with the element inserted at the first place.
`list`|It takes any number of arguments and returns a list with the arguments as member elements of the list.
`append`|It merges two or more list into one.
`last`|It takes a list and returns a list containing the last element.
`member`|It takes two arguments of which the second must be a list, if the first argument is a member of the second argument, and then it returns the remainder of the list beginning with the first argument.
`reverse`|It takes a list and returns a list with the top elements in reverse order.

**[⬆ back to top](#table-of-contents)**

  
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
