### anonymous function(lambda):

```ocaml
(* define *)
fun x -> x + 1

(* IIFE *)
(fun x -> x + 1) 2

(* no argument *)
(fun () -> print_endline "Hi") ()

(* multiple arguments *)
(fun x y -> x + y) 3 4
```

substitution: `(fun x -> x + 1) 2` is semantically equivalent to: `let x = 2 in x + 1`

### named function:

```ocaml
(* define *)
let inc = fun x -> x + 1

(* syntatic sugar *)
let inc x = x + 1

(* define a function that do not need argument *)
let hau () = print_endline "How are you?"

(* define a function that needs multiple arguments *)
let sum x y = x + y
```

define an inline function & use it:

```ocaml
let f = fun x y -> x + y in f 1 3
let f x y = x + y in f 3 2
```

### recursive function (`rec` keyword)

```ocaml
let rec fact n =
   if n = 0 then 1
   else n * fact (n - 1)

let rec fib x =
  if x = 1 || x = 2 then 1
  else fib (x - 1) + fib (x - 2)
```

### partial application

fact: multi-argument functions do not exist in OCaml

`fun x y -> e` is syntactic sugar for: `fun x -> (fun y -> e)`

example: 

```ocaml
let sum x y = x + y;;
let add2 = sum 2;;
print_int (add2 3);;
```

### parametric polymorphism

poly = many, morph = form

write function that works for many arguments regardless of their type (you may recognize this as generics in programming langs such as Java & TypeScript)

example: `let id x = x`, `x` can be of any type

### prefix operator as function:

```ocaml
( + ) 1 2;;
( * ) 2 3;;
let add = ( + );;
```

### application operator(@@)

syntax: `f @@ x = f x`

```ocaml
succ 2 * 10;;  (* this won't work *)
succ (2 * 10);; (* need grouping *)
(* or we could use the application operator *)
succ @@ 2 * 10;;
```

### reverse application operator(aka pipeline: |>):

syntax: `x |> f = f x`

```ocaml
let square x = x * x
succ (square (succ 5));; (* this works but too many parenthesis *)
5 |> succ |> square |> succ;; (* using pipeline operator is much clearly *)
```

