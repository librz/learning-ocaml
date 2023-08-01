### values:

- int: 23

- float: 2.3

- bool: ture, false

- char: 'a', 'b', 'c'...

- string: "hi", "hello", ...

### type annotation

- (23 : int)
- (2.3: float)
- (true: bool)
- (false: bool)
- ('h': char)
- ("hi": string)
- ([1; 2; 3]: int list)

### expression

- simple value as expression: 42, 1.5, 'a', "hi", true, false, not true, not false, 2 + 3

- if expression: `if 23 > 12 then "Correct" else "Wrong"`

- let definition: `let x : int = 42`

- let expression: `let x : int = 42 in 2 * x`

### printing

```ocaml
(* print by type *)
print_string "hi";;
print_int 10;;

(* concat string & print *)
print_string "hi" ^ " " ^ "there";;

(* print with newline *)
print_newline ();;
print_endline "";;
Printf.printf "\n";;
print_endline "hi";;

(* format using Printf.printf *)
Printf.printf "%s is %i years old\n" "Patrick" 27;;
```
