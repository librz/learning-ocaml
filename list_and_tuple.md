
### list syntax:

all elments in a list must have the same type

- `[]` is the empty list (pronounced "nil")
- `e :: l` prepends element e to list l (:: is pronounced "cons")
- `[e; l]` is sugar for `e :: l :: []`

### list type:

- `[]: 'a list` 
- `[e; l]` -> if e is of type "t", then l must be of type "t" as well, the whole expression is of byte "t list" 

### tuple syntax:

- `()` is the empty tuple (also known as "unit")
- `let pair = (1, "two")`
- with type annotation: `let pair: int * string = (1, "two")`
- detuple: `let (first, second) = pair`

fun fact, functions in OCaml can have at most one argument:

e.g. `let sum a b = a + b`, it may seem sum has 2 arguments but its true argument is a tuple with 2 elements. It's equivalent to `let sum (a, b) = a +b`

```ocaml
(* ref: https://www.cs.cornell.edu/courses/cs3110/2014sp/recitations/2/tuples_records_data.html *)
let pair = (1, 2);;
let sum (a, b) =  a + b;;
print_int (sum pair);;
```
