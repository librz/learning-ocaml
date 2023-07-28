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

- if expression: if 23 > 12 then "Correct" else "Wrong";;

- let definition: let x : int = 42;;

- let expression: let x : int = 42 in 2 * x;

### anonymous function(lambda):

- fun x -> x + 1;;
- (fun x -> x + 1) 2;;
- (fun x y -> x + y) 3 4;;

`(fun x -> x + 1) 2` is semantically equivalent to: `let x = 2 in x + 1`

### named function:

- let inc = fun x -> x + 1;;
- let inc x = x + 1;;
- let sum x y = x + y;;

define an inline function & use it: 

- let f x y = x + y in f 3 2;;
- let f = fun x y -> x + y in f 1 3;;

### recursive function (`rec` keyword)

```ocaml
let rec fact n = 
   if n = 0 then 1
   else n * fact (n - 1)

let rec fib x =
  if x = 1 || x = 2 then 1
  else fib (x - 1) + fib (x - 2)
```
