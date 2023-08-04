### Basic Syntax

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

### With Guards

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

### Match Compound Data Type

```ocaml
(* match list *)
let rec getlen l =
  match l with
  | [] -> 0 (* must include this, put correctness aside, the compiler will complain if pattern matching is not exhaustive *)
  | head :: tail -> 1 + getlen tail;;

Printf.printf "%i\n" (getlen [13;45;78]);;

(* match record *)
type student = {
  name: string;
  age: int;
}

let stringify_student (s: student) =
  match s with
  | {name; age;} -> name ^ " " ^ string_of_int age;;

let lisa: student = { name = "Lisa"; age = 10 }

print_endline (stringify_student lisa);;

(* match variants *)
type primary_color = Red | Green | Blue;;

let r = Red;;

type point = float * float;;

let print_point (p: point) =
  match p with
  | (x, y) -> Printf.printf "(%f, %f)\n" x y;;

type shape =
    | Circle of { center : point; radius : float }
    | Rectangle of { lower_left : point; upper_right : point }

let center (s: shape): point =
    match s with
    | Circle c -> c.center
    | Rectangle { lower_left; upper_right } ->
        let (urx, ury)  = upper_right in
        let (llx, lly) = lower_left in (
          llx +. ((urx -. llx) /. 2.),
          lly +. ((ury -. lly) /. 2.)
        );;

let c1 = Circle { center = (0., 0.); radius = 1. };;

let r1 = Rectangle {
    lower_left = (-1., -1.);
    upper_right = (1., 1.)
};;

let coc1 = center c1;;

let cor1 = center r1;;

print_point coc1;;

print_point cor1;;
```

### Pattern Matching with Let

The let syntax `let v = e1 in e2` is actually a special case of the full syntax that OCaml permits. The left-hand side of the binding may in fact be a pattern, not just an identifier. For example:

```ocaml
type student = {
  name: string;
  age: int;
}

let lisa: student = { name = "Lisa"; age = 10 };;

let { name; age } = lisa;;

Printf.printf "%s is %i years old.\n" name age;;
```

### The "function" Keyword

Because pattern matching is so often used in function body, OCaml provides `function` keyword as a syntactic sugar for pattern matching inside function:

```ocaml
let rec getlen l =
    match l with
    | [] -> 0
    | head :: tail -> 1 + (getlen tail);;
(* using function keyword, notice you don't need to specify parameter as well *)
let rec getlen = function
    | [] -> 0
    | head :: tail -> 1 + (getlen tail);;

print_int @@ getlen [1;2;3]; print_newline ();;
```

