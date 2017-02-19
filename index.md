# Rust notes

## Links

* http://doc.crates.io/guide.html
* https://doc.rust-lang.org/book/
* https://play.rust-lang.org/
* [Rust standard library documentation](https://doc.rust-lang.org/std/)


## Basics

	fn main() {

	}

* 4 spaces to indent, not tabs.
* `!` is macro, e.g. `println!()`
* When no return type is specified, it is assumed to be `()`, an empty tuple.


## Comments

* line comments: `//` until end of line.
* doc comments: `///`. Supports Markdown.
* `//!`, for commenting on items containing the comment, like crates, modules
  or functions. Commonly used inside crates root (lib.rs) or modules root
  (mod.rs).
* Can use macros like `assert_eq!` and `assert!` in doc comments, like Python
  doctests.
* The rustdoc tool can be used to generate HTML documentation from doc
  comments, and to run the code examples as tests.


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
