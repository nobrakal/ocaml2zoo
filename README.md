## Synopsis

`ocaml2zoo` is a tool to translate OCaml programs into [Zoo](https://github.com/clef-men/zoo), a deeply embedded language living inside [Rocq](https://rocq-prover.org/).

To translate the [`dune`](https://dune.build/) project living in the `proj` directory to the `dst` directory (where Rocq files are generated), run:

```
ocaml2zoo proj dst
```

THIS IS AN AUTOMATIC PORT TO THE RELEASED OCAML 5.4.1.
In particular, there is no support of [generative constructors](https://github.com/clef-men/ocaml/tree/generative_constructors).

## Building

First, you need to install [`opam`](https://opam.ocaml.org/) (>= 2.0).

To make sure it is up-to-date, run:

```
opam update --all --repositories
```

Then, create a local switch with OCaml 5.4.1:

```
opam switch create . 5.4.1
eval $(opam env --switch=. --set-switch)
```

Then, install dependencies with:

```
opam install . --deps-only --yes
```

Finally, to compile `ocaml2zoo`, run:

```
make
```
