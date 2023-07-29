ocaml has two ways of compileing code

- using `ocamlc` will compile code into bytecode (cross-platform but slower than native code)

- using `ocamlopt` will compile code into native machine code (fast but not cross-platform)


real time comparison(calculate fib 45):

- ocamlc(bytecode): 22 sec
- ocamlopt(native machine code): 4 seconds
- javascript(chrome v8): 13 sec

