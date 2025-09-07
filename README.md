# Rust
Using rust to build for mac, linux and windows in gitpod

curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y
source $HOME/.cargo/env

cargo install cross

rustc --version
cross --version

cargo init

rustup target add x86_64-pc-windows-gnu
rustup target add x86_64-apple-darwin
rustup target add aarch64-apple-darwin

sudo apt-get update && sudo apt-get install -y mingw-w64

cargo build --target x86_64-pc-windows-gnu --release
ls target/x86_64-pc-windows-gnu/release/rust.exe

sudo apt-get update && sudo apt-get install -y clang llvm-dev libxml2-dev uuid-dev zlib1g-dev libssl-dev

cross build --target x86_64-apple-darwin --release
cross build --target aarch64-apple-darwin --release
