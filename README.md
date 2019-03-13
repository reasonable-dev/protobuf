# @reasonable-dev/protobuf

Gathering protobuf fragments into singular solution.

## Goal

The goal of this project is to have a single install that:
* Provides an entire runtime for code generated by `ocaml-protoc`
* Supports (the latest) BuckleScript
* (Future) Has a nice ReasonML interface
* (Future) Exposes the `ocaml-protoc` CLI for code generation

## Code Generation

Code can be generated with the `ocaml-protoc` library.

Install and build it with `esy`:
```bash
esy add @opam/ocaml-protoc
esy build
```

You can check your install with:
```bash
esy ls-libs
```

To generate code that works with the BinaryRuntime:
```bash
esy x ocaml-protoc -binary -ml_out src src/messages.proto
```

To generate code that works with the JsonRuntime:
```bash
esy x ocaml-protoc -bs -ml_out src src/messages.proto
```

## Acknowledgements

This project pulls together parts from:
* https://github.com/ocaml-ppx/ppx_deriving_protobuf
* https://github.com/mransan/bs-ocaml-protoc-json
* https://github.com/mransan/ocaml-protoc

These projects haven't been updated in a long time and some don't work with newer BuckleScript versions.
They also depended upon each other, but were maintained by different people so keeping everything in sync was a nightmare.
