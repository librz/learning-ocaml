### basic syntax

```ocaml 
(* simple pattern matching *)

Printf.printf "%s\n" (match true with
    | true -> "Yep"
    | false -> "Nope");;

Printf.printf "%i\n" (match "foo" with
    | "bar" -> 0
    | _ -> 1);; (* _ means matches any other cases, aka wildcard *)

let rec fib x =
    match x with
    | 1 | 2 -> 1 (* merge 1 and 2 as one match condition *)
    | x -> fib (x - 1) + fib (x - 2);;

Printf.printf "%i\n" (fib 5);;k
```

### with guards

```ocaml
(* pattern matching with guards *)

let exam_result grade =
    match grade with
    | x when x < 60 -> "D" (* when keyword is a guard *)
    | x when x < 70 -> "C"
    | x when x < 80 -> "B"
    | x when x < 90 -> "A"
    | _ -> "S";; 

let exam_grade = Random.int 100;;

Printf.printf "exam grade is %i, " exam_grade;;

Printf.printf "exam result is %s\n" (exam_result exam_grade);;
```

### match compound data type

```ocaml
(* list pattern matching *)
let rec getlen l =
  match l with
  | [] -> 0
  | head :: tail -> 1 + getlen tail;;

Printf.printf "%i\n" (getlen [13;45;78]);;

(* record pattern matching *)
type student = {
  name: string;
  age: int;
}

let stringify_student (s: student) =
  match s with
  | {name; age;} -> name ^ " " ^ string_of_int age;;

print_endline (stringify_student { name = "Lisa"; age = 10 });;
```

