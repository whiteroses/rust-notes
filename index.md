# Rust notes

## Links

* http://doc.crates.io/guide.html
* https://doc.rust-lang.org/book/
* https://play.rust-lang.org://play.rust-lang.org/


## Basics

	fn main() {

	}

* 4 spaces to indent, not tabs.
* `!` is macro, e.g. `println!()`


## Building

	rustc code.rs

Or, with Cargo.


## Cargo

To start a new project (--bin for executable application instead of library):

	cargo new hello_world --bin

Also initialises the directory as a git repository.


`cargo build` expects
* source files to live inside a `src` directory.
* A `Cargo.toml` (capital C required), in TOML (Tom's Obvious, Minimal
  Language) format.

Build:

	cargo build

Build and run:

	cargo run

Build with optimisations (more optimised code, but longer to compile):

	cargo build --release


`cargo build` creates a file called `Cargo.lock` to keep track of dependencies.
