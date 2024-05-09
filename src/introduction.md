## Motivation

The Rust programming language is a great contender, if you want to:
 
- to build webassembly/JavaScript apps for the web or 
- target some specific module that need speeding, memory safety, or both.


However, most Rust-wasm tutorials, lean heavily on "NPM and webpack", just to get a "hello world".

More on that <a href="./motivation.html" target="_blank">[here]</a>

> The following pages brings under one location all those bits and pieces you want to know in order to understand and build wasm stuff with Rust. 

More specifically the intent is to address these wishes:

- Rust developers should be able to produce WebAssembly packages for use in JavaScript without requiring a Node.js development environment
- JavaScript developers should be able to use WebAssembly without requiring a Rust development environment

source: [Hello wasm-pack!](https://hacks.mozilla.org/2018/04/hello-wasm-pack/){target="_bank"}

## no-bundle Wasm by example

### Objectives

Webassembly is still a moving target and some tools and convenient crates make the experience more appealing.

- Learn how to transform most Rust/wasm tutorials into lean no-bloat rust-wasm with no-bundle.
- Get familliar with the following tools and crates: 
  * [wasm-pack](https://rustwasm.github.io/wasm-pack/installer/){target="_blank"}, (
[docs](https://rustwasm.github.io/docs/wasm-pack/introduction.html){target="_blank"})  
  * [wasm-bindgen](https://github.com/rustwasm/wasm-bindgen){target="_blank"}, 
([docs](https://rustwasm.github.io/docs/wasm-bindgen/){target="_blank"})  
  * [js-sys](https://lib.rs/crates/js-sys){target="_blank"} & [web-sys](https://lib.rs/crates/web-sys){target="_blank"} ([js-sys example](https://rustwasm.github.io/wasm-bindgen/examples/wasm-in-wasm.html){target="_blank"}, 
[web-sys examples](https://rustwasm.github.io/wasm-bindgen/examples/dom.html){target="_blank"} )

<!-- 
[trunkrs.dev](https://trunkrs.dev/){target="_blank"}  
-->

### Let the tutorial begin!

We'll convert each examples from the [wasm-bindgen guide](https://rustwasm.github.io/docs/wasm-bindgen/){target="_blank"} to a no-bundle version.
For each example or demo:

- Part I, will help you get the example running.
- Part II, will expose or highlight aspects of the code related to wasm-bindgen, wasm-pack or Rust.

It is assumed that you have Rust on your machine and cargo ready for use.
(If not get the installer [here: rustup.rs](https://rustup.rs/){target="_blank"}).

#### 0. Get wasm-pack and something to serve our website locally

Let's prepare our workspace, and setup our tools.

##### 0.1 Install wasm-pack

```sh
cargo install wasm-pack
```

wasm-pack helps you build rust-generated WebAssembly packages 
Its a useful convenience that is widely used by the Rust community.

If your interested see [wasm-pack under the hood](./wasm-pack_under_the_hood.html){target="_blank"}

##### 0.2 Install a local tiny static file server

We need something to serve your website so we can test and see what we develop on our local machine.
If you don't have one installed you can use `H`ost `T`hese `T`hings `P`lease - a basic http server 
for hosting a folder fast and simply [http](https://github.com/thecoshman/http){target="_blank"} 

```bash
cargo install https
```

Note: 
    
[trunkrs.dev](https://trunkrs.dev/){target="_blank"} is getting traction in the Rust community 
but its a much more ambitious tool and beyond our needs here.
 
### Formula for Converting examples

#### Seven steps to hello world

1. Set up your file structure
2. Edit Cargo.toml: Set the *crate-type* and add wasm-bindgen as a dependency.
3. Get the lib.rs code for hello_world
4. Specify type module in index.html
5. import with file extension included and Wrap the code in async/await index.js
6. build with wasm-pack
7. Run the web server and open your browser


Let's see that in practice with the first example: [wasm Hello world](./001_hello_world.html)

