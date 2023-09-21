# wasm-life

This is a Wasm test with Rust and Svelte following the tutorial https://blog.logrocket.com/integrating-svelte-app-rust-webassembly/

## Clonning this

```git
git remote add origin https://github.com/ricardodarocha/wasm-life.git
git branch -M main
git push -u origin main

```

## How it was made

At an empty folder, made a new lib project

```rust
cargo new --lib wasm-life
cd wasm-test
cargo add wasm-bindgen --features serde-serialize
cargo add console_error_panic_hook
cargo add serde --features derive
cargo add serde-wasm-bindgen
cargo check
code .
```

Put all game of life code together and run `wasm-pack build` It was generated the pkg folder

## Putting it into a Web Page

To take our wasm-game-of-life package and use it in a Web page, we use the create-wasm-app JavaScript project template.

Run this command within the wasm-game-of-life directory:

```js
npm init wasm-app www
```

Here's what our new wasm-game-of-life/www subdirectory contains:

wasm-life/www/  
├── bootstrap.js  
├── index.html  
├── index.js  
├── LICENSE-APACHE  
├── LICENSE-MIT  
├── package.json  
├── README.md  
└── webpack.config.js  

The index.js imports the entire module

```js
import * as crab from "../pkg";
```

```js
cd www
npm i
npm run start
```

