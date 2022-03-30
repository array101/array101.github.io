+++
title = "WebAssembly"
slug = "webassembly"
layout = "page.html"
date = 2022-03-30
draft = true
[taxonomies]
tags = ["wasm"]
+++

# WebAssembly

WebAssembly or `Wasm` is binary instruction format for a stack-based VM.
**Wasm** is designed as a portable target for compilation of high-level
languages like C/C++/Rust, enabling deployment on the web for client and server
applications.

- **Wasm** is basically a VM to prioritize portablity. `*.wasm` files are
  ingested by a runtime (like the browser) that turns this file into actual
  machine code of the actual machine the browser is running on and then execute
  that code.
