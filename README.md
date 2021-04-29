# A sample react application that can interact with WebAssembly for audio processing

Our application is going to detect and show the current pitch in real time. Audio analysis is being done with Rust WebAssembly module.

The popularity of WebAssembly will surely continue to grow; however, it’s not suitable for all web development. While many programming languages compile to Wasm, I chose Rust for this example. Rust was created by Mozilla in 2010 and is growing in popularity. Rust occupies the top spot for “most-loved language” in the 2020 developer survey from Stack Overflow.

* First and foremost, Rust has a small runtime which means less code is sent to the browser when a user accesses the site, helping keep the website footprint low.
* Rust has excellent Wasm support, supporting high-level interoperability with JavaScript.
* Rust provides near C/C++-level performance, yet has a very safe memory model
* Rust is not garbage-collected. This means that Rust code is fully in control of when memory is allocated and cleaned up, allowing consistent performance—a key requirement in real-time systems.

## Available Scripts

This tutorial assumes you have Node.js installed.

### Get Rust

You can follow these instructions to build the [Rust](https://www.rust-lang.org/tools/install) chain for development.

### Install WebAssembly Components

`wasm-pack` allows you to build, test, and publish Rust-generated WebAssembly components. If you haven’t already, [install wasm-pack](https://rustwasm.github.io/wasm-pack/installer/).

### Build WebAssembly Module

When developing Rust applications, the usual build procedure is to invoke a build using `cargo build`. However, we are generating a Wasm module, so we’ll make use of `wasm-pack`, which provides simpler syntax when targeting Wasm.
```
wasm-pack build --target web
```

If successful, an npm module is created under ./pkg. This is a JavaScript module with its very own auto-generated package.json. This can be published to the npm registry if desired.

To keep things simple for now, we can simply copy and paste this pkg under our folder public/wasm-audio:

```
cp -R ./wasm-audio/pkg ./public/wasm-audio
```

With that, we have created a Rust Wasm module ready to be consumed by the web app!


## Run Application

In the project directory, you can run:

### `yarn`
Install dependencies from package.json

### `yarn start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in the browser.

### `npm run build`

Builds the app for production to the `build` folder.\
It correctly bundles React in production mode and optimizes the build for the best performance.

The build is minified and the filenames include the hashes.\
Your app is ready to be deployed!

See the section about [deployment](https://facebook.github.io/create-react-app/docs/deployment) for more information.

### `npm run eject`

**Note: this is a one-way operation. Once you `eject`, you can’t go back!**

If you aren’t satisfied with the build tool and configuration choices, you can `eject` at any time. This command will remove the single build dependency from your project.

Instead, it will copy all the configuration files and the transitive dependencies (webpack, Babel, ESLint, etc) right into your project so you have full control over them. All of the commands except `eject` will still work, but they will point to the copied scripts so you can tweak them. At this point you’re on your own.

You don’t have to ever use `eject`. The curated feature set is suitable for small and middle deployments, and you shouldn’t feel obligated to use this feature. However we understand that this tool wouldn’t be useful if you couldn’t customize it when you are ready for it.

## Learn More

You can learn more in the [Create React App documentation](https://facebook.github.io/create-react-app/docs/getting-started).
