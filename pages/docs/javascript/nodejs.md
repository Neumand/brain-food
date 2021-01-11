# Node JS

## Overview

An environment to run JS outside of the browser.

* Open source runtime.
* Built on Chrome's V8 JS engine.
* The ecosystem has vastly improved since it was created. Developers can now build almost anything with only JS. The tooling surrounding Node is incredible and outperforms many other languages.
* While Node is suitable for most web applications/websites today, it's not meant for highly intensive CPU activities (single-threaded with an event loop).

Node is great for creating:
* Tooling - build or automation
* API (REST, real-time)
* CDNs
* Shareable libraries (`npm`)
* Desktop appplications (Electron) with web technologies
* IOT

## Globals
`process`: information about the environment the program is running in

`require`: function to find and use modules in the current module, Node's way of importing

`__dirname`: the current directory path

`module`: information about the current module, methods for making module consumable

`global`: like `window` but for Node, does not provide access to browser APIs

## Modules
Encapsulated JS code. They look like this:

```javascript
const module = (function(exports, require, module, __filename, __dirname) {
  // Your code in a file...
})
```

Node will pass these globals in an IIFE for you to be able to use.

Until Node migrates over to ES6 modules, CommonJS is the only way to share code (without transpiling the code).
### Creating Modules
```javascript
const add = (num, num2) => {
  return num + num2;
}

// Named exports
module.exports = {
  add,
  thing() {},
  value: 1
}

// Default export
module.exports = add;
```

This allows us to separate the actual code and the exports (**revealing module pattern**).

Being explicit about what you're exporting is very important for bundling tools for better performance (i.e. tree-shaking).

### Using Modules
```javascript
// Named exports
const { add } = require("./add");

// Default export
const add = require("./add");
```

`require` needs a relative path when you import a file that *you* created. There are other ways to import using `require` when you import an external module. It's a dependency tree that Node resolves.

### Internal Modules
Modules that come shipped with Node. Some of the frequently used ones include:
* `fs`: fileSystem module for interacting with files on a machine
* `http`: low level-ish module for creating network-based programs like APIs
* `path`: for manipulating path strings and handling differences across Operating Systems
