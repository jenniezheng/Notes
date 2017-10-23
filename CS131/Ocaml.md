
## OCaml

##### Language Traits:
- functional language
- static typing (like C)
- type inference (like Python)
- no pointers nor objects
- includes garbage collection
- higher order functions

##### Currying
A method of creating high order functions
```ocaml
let badcon (x, y) = x :: y;;
badcon (1,[2;3])

let goodcon x y = x :: y;;
let goodconpart2 = goodcon 1;;
goodconpart2 [2;3]
```

##### Matching
Uses pattern matching. Below are common matches...

- 0 with Number zero

- head::tail with Non-empty list 

- [] with Empty List 

- var_x with Anything      

- _ with Anything, trash variable 

##### Fun vs Function
fun is for currying
`fun x y -> x + y`
Function is for implicit matching
`function 0 -> True | 1 -> False`

##### Defining Types
Predefined type option
```ocaml
type 'a option =
| Some of 'a
| None
```
Creating discriminated union
```ocaml
type custom_type =
| Foo of int
| Bar of int
| Baz of string * int
```
Creating value of type
```ocaml
Bar 12;;
Baz("abc", 19);;
```
