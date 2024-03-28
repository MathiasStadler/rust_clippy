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
# init first git repo
echo "target" > .gitignore
echo "**/target/**" >> .gitignore
echo "*/target/**" >> .gitignore
echo "/target/**" >> .gitignore
echo "/target/.*" >> .gitignore
echo "target/**" >> .gitignore
echo "target/**" >> .gitignore
echo "target/**" >> .gitignore
echo "target/.*" >> .gitignore
echo "**/target" >> .gitignore
echo "**/target" >> .gitignore
echo "**/target" >> .gitignore
echo "**/target/.*" >> .gitignore
echo "**/.*" >>.gitignore
export PS1='\w$(__git_ps1 " (%s)")\$ '
git add -f *
git add -f .gitignore
git commit -m "init commit"
cargo check
git add -f *
git commit -m "cargo check"
cargo clippy --no-deps --fix --
git add -f *
git commit -m "clippy fix"
cargo clippy --no-deps --fix --examples --
git add -f *
git commit -m "clippy fix examples"
```

- HINT box ??
-- git ls-tree --full-tree -r --name-only HEAD

```rust

```

** next step
.gitignore subfolder of target
rustfmt
cargo fmt # format
