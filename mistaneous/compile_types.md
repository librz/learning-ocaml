ocaml has two ways of compileing code

- using `ocamlc` will compile code into bytecode (cross-platform but slower than native code)

- using `ocamlopt` will compile code into native machine code (fast but not cross-platform)


real time comparison(calculate the 45th fibonacci number):

- ocamlopt(native machine code): 4 seconds
- javascript(chrome v8): 13 sec
- ocamlc(bytecode): 22 sec
- python3: 150 sec

side note: Dynamic scripting languages are usually painfully slow. But JavaScript is actually shockingly fast because a lot of effort has been put into optimizing it. In other words, too much lipsticks have been put on that ugly pig.

