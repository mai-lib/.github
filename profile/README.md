## mai

**mai** is a compiled language for statistical computing. It reads like R,
but an optimising compiler and a fast virtual machine make ordinary
loop-heavy code run quickly.

The language, compiler and VM are the work of Brendan McArdle, described in
his 2018 University of Auckland PhD thesis,
[*A Compiled Language for Statistical Computing*](https://researchspace.auckland.ac.nz/items/9dd448b6-5736-40f8-b9c8-e2aedff3d385).
"mai" stands for McArdle And Ihaka, after the author and Ross Ihaka. It is
also a nod to `par("mai")`, and to te reo M&#257;ori *mai*, "towards".

### Repositories

| Repository | What it is | Docs |
| --- | --- | --- |
| [mai](https://github.com/mai-lib/mai) | The language: compiler, VM, runtime, tests and worked examples. Also `libmai` for embedding and the `pymai` Python package with a `%%mai` Jupyter magic | [mai-lib.github.io/mai](https://mai-lib.github.io/mai/) |
| [rmai](https://github.com/mai-lib/rmai) | R package: run mai from R, pass data both ways, `{mai}` chunks in R Markdown and Quarto | [mai-lib.github.io/rmai](https://mai-lib.github.io/rmai/) |

### Quick start

```sh
git clone https://github.com/mai-lib/mai
cd mai
make build CTUNE=     # Linux; needs a C compiler, bison, m4, readline, valgrind headers
build/main examples/01-basics.mai
```

From R:

```r
remotes::install_github("mai-lib/rmai")
rmai::mai_install()
rmai::mai_run("print(sum(1:100))")
```

### Status

mai builds and is tested on x86-64 Linux, with arm64 Linux in CI. macOS
does not build yet. Source is GPL-2, as in the thesis. Issues and pull
requests are welcome. Every pull request that touches the docs gets a
rendered preview.
