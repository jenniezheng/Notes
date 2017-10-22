# OCaml

###### Language Traits:
- functional language
- compile-time type checking (like C, Java)
- no need to manually specify types (like Python)
- garbage collection
- higher order functions

##### Currying
A method of creating high order functions
```
let badcon (x, y) = x :: y;;
badcon (1,[2;3])

let goodcon x y = x :: y;;
let goodconpart2 = goodcon 1;;
goodconpart2 [2;3]
```

##### Matching
Uses patterns
| Pattern | Matches |
| ------------- |:-------------:|
| 0 | The number zero |
| head::tail | Non-empty list |
| [] |Empty List |
| var_x      | Anything      |
| _ | Anything, trash variable |

##### Fun vs Function
fun is for currying
`fun x y -> x + y`
Function is for implicit matching
`function 0 -> True | 1 -> False`

##### Defining Types
Predefined type option
```
type 'a option =
| Some of 'a
| None
```
Creating discriminated union
```
type custom_type =
| Foo of int
| Bar of int
| Baz of string * int
```
Creating value of type
```
Creating value
Bar 12;;
Baz("abc", 19);;
```