+++
title = "Intro to Rust Lang"
slug = "intro-to-rust-lang"
template = "page.html"
draft = true
[taxonomies]
tags = []
+++

**Rust** is a memory-safe, multi-paradigm statically-typed systems programming language that features:
- zero-cost abstractions
- ownership semantics
- trait-based generics
- pattern matching (functional)
- syntactic macros

## syntactic macros
---
**macros** are functions that work over syntax - macros take syntax as input and produces a new syntax as output. Instead of making function call, macros are expanded into source code. Macros enable metaprogramming in Rust.

Syntax: `<macro_name>!`

Use cases:
- When you want to DRY the source code
- To implement DSL
- To implement *varadic interfaces*. A variadic interface takes an arbitrary number of arguments.

Rust macros are expanded to ASTs rather than string pre-processing like in C, C++.

(ref)[https://www.youtube.com/watch?v=VGk95NXaafs]

```rust
// declaration
macro_rules! x_and_y {
    // The arguments are prefixed by $ inside macros and type annotated by a 'designator'
    // Ex: 'expr' is a designator - meaning this variable $e can be any expression - virtually anything in Rust - Rust is an expression based language
    (x => $e:expr) => println!("X: {}", $e);
    (y => $e:expr) => println!("Y: {}", $e);
    () => {
        println!("This is a macro.");
    }
}
// invocation
fn main() {
    x_and_y!();
    x_and_y!(x => 10);
    x_and_y!(y => 20 + 20);
}
```

Example: `println!("")`, `vec![]`

```rust
fn one_even(a: i32, b: i32) -> bool {
    or!(even(a), even(b));
}
```

`or!` is a macro that takes a input syntax and produces a new program as output syntax

```rust
fn one_even(a: i32, b: i32) -> bool {
    if even(a) {
        true
    } else {
        even(b)
    }
}
```

