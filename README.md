## Synopsis

`ocaml2zoo` is a tool to translate OCaml programs into [Zoo](https://github.com/clef-men/zoo), a deeply embedded language living inside [Rocq](https://rocq-prover.org/).

To translate the [`dune`](https://dune.build/) project living in the `proj` directory to the `dst` directory (where Rocq files are generated), run:

```
ocaml2zoo proj dst
```

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

Note: with stock OCaml, generative constructors from [this fork](https://github.com/clef-men/ocaml/tree/generative_constructors) are not available, so the corresponding tests (`generative_1`, `generative_2`) cannot pass.

Then, install dependencies with:

```
opam install . --deps-only --yes
```

Finally, to compile `ocaml2zoo`, run:

```
make
```
