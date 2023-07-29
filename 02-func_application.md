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

### reverse application oprator(aka pipeline: |>):

syntax: `x |> f = f x`

```ocaml
let square x = x * x
succ (square (succ 5));; (* this works but too many parenthesis *)
5 |> succ |> square |> succ;; (* using pipeline operator is much clearly *)
```

