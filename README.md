# xxfunc

## Demo

terminal 1 (server)

```
RUST_LOG=info cargo run -p server
```

terminal 2 (user)

build -> deploy -> start

```
cargo xxfunc build
cargo xxfunc deploy --url http://0.0.0.0:3000 --wasm-path ./wasm_output/output.wasm
cargo xxfunc start --url http://0.0.0.0:3000 --module-name output.wasm
```

terminal 3 (reth + scheduler)

```
ETHERSCAN_API_KEY={ETHERSCAN_API_KEY} cargo run -p xxfunc-exex -- node --debug.etherscan --chain holesky --http 
```

## Build and Run wasm module

- install `cargo-xxfunc` subcommand
- build wasm module with `cargo xxfunc build`
- run wasm module with runtime test

```console
./scripts/build_run_module.sh
```

## TODO:

- [ ] add status of functions in the module db. (eg started or stopped)
- [ ] xxfunclib include a handle to the reth datadir and can be called from the main function
