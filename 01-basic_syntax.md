### values:

- int: 23

- float: 2.3

- bool: ture, false

- string: "hello"

### type annotation

- (23 : int)
- (2.3: float)
- (true: bool)
- (false: bool)
- ("hi": string)
- ([1; 2; 3]: int list)

### expression

- if expression: `if 23 > 12 then "Correct" else "Wrong"`

- let definition: `let x : int = 42`

- let expression: `let x : int = 42 in 2 * x`

### anonymous function(lambda):

- define: `fun x -> x + 1`
- execute: `(fun x -> x + 1) 2`
- multiple parameters: `(fun x y -> x + y) 3 4`

substitution: `(fun x -> x + 1) 2` is semantically equivalent to: `let x = 2 in x + 1`

### named function:

- define: `let inc = fun x -> x + 1`
- syntatic sugar: `let inc x = x + 1`
- multiple parameters: `let sum x y = x + y`

define an inline function & use it: 

- `let f = fun x y -> x + y in f 1 3`
- `let f x y = x + y in f 3 2`

### recursive function (`rec` keyword)

```ocaml
let rec fact n = 
   if n = 0 then 1
   else n * fact (n - 1)

let rec fib x =
  if x = 1 || x = 2 then 1
  else fib (x - 1) + fib (x - 2)
```

### printing

```ocaml
(* print by type *)
print_string "hi";;
print_int 10;;

(* print with newline *)
print_endline "";;
print_endline "hi";;

(* format using Printf.sprintf *)
let str = Printf.sprintf "%s is %i years old" "Patrick" 27;;
print_endline str;;
```
