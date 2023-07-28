Setup OCaml on macOS:

first: `brew install ocaml`, then: `brew install opam`

test installation:

```sh
which ocaml
ocaml --version
which opam
opam --version
```

first program:

- first: create a file named hello.ml, with a line of code such as: print_string "Hello World!\n";;
- then: compile the code using ocamlc: ocamlc -o hello hello.ml
- should generate a file named hello, run it: ./hello

use REPL:

- enter REPL: ocaml
- quit REPL: Ctrl + D
