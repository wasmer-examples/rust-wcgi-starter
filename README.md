This is a template project for creating a [WCGI](https://docs.wasmer.io/runtime/runners/wcgi) package that can be
published to the Wasmer Registry.

## Getting Started

Next, make sure you have Rust and its `wasm32-wasi` target installed.

```console
rustup target add wasm32-wasi
```

Now, you can compile the project to WebAssembly.

```console
$ cargo build --target=wasm32-wasi --release
    Finished release [optimized] target(s) in 0.00s
$ ls target/wasm32-wasi/release
build  deps  examples  incremental  wcgi-rust-template.d  wcgi-rust-template.wasm
```

You can also use `wasmer run` to test things locally.

```console
$ wasmer run . --net
INFO run: wasmer_wasix::runners::wcgi::runner: Starting the server address=127.0.0.1:8000 command_name="server"
```


> [!NOTE]
> You will need to have Wasmer installed (check out [the docs to install the Wasmer CLI](https://docs.wasmer.io/install)!). 
> The `--net` flag is required to enable networking support in Wasmer.

## Deploy on Wasmer Edge

The easiest way to deploy your WCGI Rust app is to use the [Wasmer Edge](https://wasmer.io/products/edge).
You can see a live demo of this website deployed on Wasmer Edge: http://wcgi-rust-starter.wasmer.app/

```console
wasmer deploy
```

> [!NOTE]
> You will need to change the namespace in `wasmer.toml` to your own namespace and app name in `app.yaml` to your own app name.



[api-docs]: https://wasmerio.github.io/wcgi-rust-template
[crev]: https://github.com/crev-dev/cargo-crev
[install]: https://docs.wasmer.io/ecosystem/wasmer/getting-started
