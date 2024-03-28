# test out clippy

- [tutorial](https://zhauniarovich.com/post/2021/2021-09-pedantic-clippy/)

1) init dummy project

```bash
set -e
mkdir rust_clippy && cd $_
cargo init .
cargo build
cargo run
mkdir examples
cp ./src/main.rs examples/
sed -i 's/world/example/' ./examples/main.rs
cargo run --example main
cargo check
cargo clippy --no-deps --fix --
cargo clippy --no-deps --fix --examples --
```

```rust

```
