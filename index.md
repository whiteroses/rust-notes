# Rust notes

## Links

* http://doc.crates.io/guide.html
* https://doc.rust-lang.org/book/
* https://play.rust-lang.org/
* [Rust standard library documentation](https://doc.rust-lang.org/std/)
* https://github.com/kud1ing/awesome-rust


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


## Variable bindings

    let (x, y) = (1, 2);

The left-hand side of a `let` statement is a pattern, not a variable name.

* Statically typed
* Must be initialised with a value before use.
* Have block scope (within `{}`).
* Specifying type:

		let x: i32 = 5;

* Rust has type inference.
* By default, bindings are immutable. This will not compile:

		let x = 5;
		x = 10;

* If we want a binding to be mutable, use `mut`:

		let mut x = 5;
		x = 10;

* But variable bindings can be shadowed:

		let x: i32 = 8;
		{
		    let x = 12;
		    // x is now 12.
		}
		// x is now 8 again.
		let x = 42;
		// x is 42.

	* Shadowing allows us to rebind a name to a value of a different type, or
      change the mutability of a binding.
	* Shadowing does not alter or destroy the value it was bound to; the value
      will continue to exist until it goes out of scope, even if it is no
      longer accessible by any means.

			let mut x: i32 = 1;
			x = 7;
			let x = x; // `x` is now immutable and is bound to `7`.


### Integer types

* `i` for signed integers and `u` for unsigned integers. Possible integer
  sizes: 8, 16, 32, and 64 bits. (e.g. `i32`)


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
