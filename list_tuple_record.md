### list syntax:

all elments in a list must have the same type

- `[]` is the empty list (pronounced "nil")
- `e :: l` prepends element e to list l (:: is pronounced "cons")
- `[e; l]` is sugar for `e :: l :: []`

### list type:

- `[]: 'a list` 
- `[e; l]` -> if e is of type "t", then l must be of type "t" as well, the whole expression is of byte "t list" 

### tuple syntax:

tuple is just a bundle of elments(can be of different type) gruoped together and allow access by position

- `()` is the empty tuple (also known as "unit")
- `let pair = (1, "two")`
- with type annotation: `let pair: int * string = (1, "two")`
- detuple: `let (first, second) = pair`
- get first value in a pair: `fst pair`
- get second value in a pair: `snd pair`
- both `fst` & `snd` can be only used on tuple with exactly two elements

fun fact, functions in OCaml can have at most one argument:

e.g. `let sum a b = a + b`, it may seem sum has 2 arguments but its true argument is a tuple with 2 elements. It's equivalent to `let sum (a, b) = a +b`

```ocaml
(* ref: https://www.cs.cornell.edu/courses/cs3110/2014sp/recitations/2/tuples_records_data.html *)
let pair = (1, 2);;
let sum (a, b) =  a + b;;
print_int (sum pair);;
```

### record syntax

records is a compound type with named fields (order of fields is irrelevant)

```ocaml
(* define record type *)
type student = {
    name : string;
    year : int; (* grad year *)
}

(* define record instance *)
let ruth = {
    name = "Ruth Bader",
    year = 1954
};;

print_string ruth.name; print_string " graduated in "; print_int ruth.year; print_endline "";;
```

### how to choose between list, tuple & record?

```ocaml
if length is bounded then use list
else if access by name then use record
else if access by position then use tuple
else use other data type
```

